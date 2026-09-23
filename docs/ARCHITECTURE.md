# Arquitetura do EstampaPro

## Visão geral

O EstampaPro foi construído como um protótipo funcional local, priorizando validação de fluxo e regras de negócio antes da adoção de infraestrutura remota.

```mermaid
flowchart TD
    UI[React UI] --> DOMAIN[Regras de domínio]
    UI --> FILES[Arquivos / PDF / OCR]
    DOMAIN --> DATA[Camada de dados]
    FILES --> DATA
    DATA --> IDB[(IndexedDB)]
    DATA --> SYNC[BroadcastChannel]
```

## Interface

A interface é organizada por áreas funcionais: dashboard, pedidos, clientes, financeiro, histórico, arquivos e configurações.

## Domínio

As regras de negócio controlam pontos como:

- elegibilidade para avanço de etapa;
- aprovação;
- conferência de peças;
- cobrança;
- recebimento;
- alocação de pagamentos;
- encerramento e reabertura de pedidos.

## Persistência atual

O protótipo usa IndexedDB para registros e arquivos locais. Isso permite uma experiência funcional sem backend, mas não substitui uma arquitetura de produção.

A sincronização entre abas ocorre via `BroadcastChannel`.

## Processamento local

PDF, OCR e leitura de planilhas são tratados no navegador. Isso reduz dependência externa durante a fase de protótipo e mantém os arquivos no ambiente local do usuário.

## Arquitetura planejada para produção

```mermaid
flowchart TD
    CLIENT[Frontend] --> API[Backend / API]
    API --> AUTH[Autenticação]
    API --> DB[(PostgreSQL)]
    API --> STORAGE[Storage privado]
    API --> RULES[Validações críticas]
```

A evolução para produção deve incluir autenticação, autorização, banco de dados remoto, armazenamento privado, backup e validação de regras críticas no servidor.

## Observação sobre este repositório

A documentação pública descreve decisões e componentes em nível de produto. A implementação e a organização interna detalhada permanecem privadas.
