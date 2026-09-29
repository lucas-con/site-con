# Site institucional da ConCrédito

Código-fonte da versão Gold aprovada em 8 de setembro de 2026.

## Requisitos

- Node.js 22.13 ou superior
- npm
- Linux no ambiente de integração e produção

## Instalação e validação

```bash
npm ci
npm run typecheck
npm test
```

O projeto usa Next.js 16, React 19, Vinext e Cloudflare Workers. O build gera o Worker em `dist/server/index.js` e os arquivos públicos em `dist/client`.

## Variáveis de produção

Copie `.env.example` para o gerenciador de variáveis do ambiente. Não publique arquivos `.env` nem segredos no GitHub.

- `NEXT_PUBLIC_SITE_URL`: domínio oficial completo, sem barra final.
- `NEXT_PUBLIC_INDEXING_ENABLED`: use `false` durante homologação e `true` somente no domínio oficial.
- `NEXT_PUBLIC_OPENAI_ADS_PIXEL_ID`: identificador de mensuração, quando aprovado.
- `NEXT_PUBLIC_ADS_PRIVACY_VERIFIED`: mantenha `false` até validação do fluxo de consentimento e privacidade.

## Publicação

1. Crie um repositório privado na organização da ConCrédito.
2. Envie todos os arquivos deste pacote para a branch `main`.
3. Proteja a branch e exija a execução de typecheck e testes antes do merge.
4. Conecte o repositório ao projeto da ConCrédito na Cloudflare.
5. Cadastre as variáveis do ambiente de produção.
6. Configure o domínio oficial e os redirecionamentos HTTPS.
7. Faça um último teste em iPhone, Android e desktop antes de ativar a indexação.

## Canais que devem ser preservados

- Simulação/WhatsApp comercial: `(51) 9788-5348`
- Suporte: `(54) 9978-0786`

## Antes do domínio oficial

O jurídico e o DPO devem validar a política de privacidade, o encaminhamento para o WhatsApp, o conteúdo atualizado sobre INSS, a identificação dos canais dos parceiros e a comprovação operacional das alegações de comparação de ofertas.

O arquivo `.openai/hosting.json` pertence à homologação no ChatGPT Sites e não contém credenciais. O time pode mantê-lo durante a transição; a infraestrutura definitiva deve ser controlada pela ConCrédito.
