# Estado atual do EstampaPro

## Situação

O EstampaPro está em estágio de **protótipo funcional local**.

A aplicação já permite validar o fluxo operacional principal, incluindo cadastro de pedidos, organização da produção, conferência de peças, anexos, cobrança, recebimento e histórico.

## O que já foi validado

- fluxo principal de pedido até entrega;
- kanban com avanço controlado;
- cadastro e consulta de clientes;
- importação de peças por texto e planilha;
- OCR local de imagens;
- visualização de PDF e seleção de capa;
- pagamentos parciais e alocação financeira;
- tema claro/escuro;
- comportamento responsivo em larguras móveis testadas;
- testes automatizados de regras de domínio e peças.

## Limitações atuais

A versão atual ainda não deve ser considerada uma solução de produção definitiva.

- dados e anexos ficam no navegador atual;
- não existe autenticação;
- não existe isolamento entre contas;
- não existe sincronização entre dispositivos;
- não existe backup automático remoto;
- não existe autorização de servidor;
- não existe gateway de pagamento;
- não existe envio automático de WhatsApp ou e-mail;
- CDR é armazenado para download, sem processamento;
- ajustes financeiros avançados e reversões ainda não estão completos;
- testes end-to-end automatizados ainda fazem parte do roadmap.

## Persistência

O protótipo usa IndexedDB para armazenar dados e arquivos localmente. A aplicação também usa BroadcastChannel para atualizar outras abas abertas na mesma origem.

Esses mecanismos são adequados para demonstração e validação local, mas não substituem uma infraestrutura com backend, banco de dados, políticas de autorização e armazenamento remoto.

## Segurança

Nenhuma credencial de backend é necessária no estado atual. Em uma versão de produção, autenticação, autorização, armazenamento privado e validação das regras críticas deverão ocorrer no servidor.

## Código-fonte

O código-fonte não faz parte deste repositório público. Este espaço documenta apenas o produto e sua evolução.
