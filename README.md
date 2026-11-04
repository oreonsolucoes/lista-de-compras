# Lista de Compras

App de lista de compras com várias compras por data, modo **Planejar** (anotar por departamento, com sugestões do histórico) e modo **No mercado** (riscar, digitar preço, progresso, busca e filtro por departamento). Os dados ficam no Firebase Realtime Database e sincronizam entre celular e computador.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O app inteiro |
| `firebase-config.js` | Configuração do seu projeto Firebase (preencher) |
| `database.rules.json` | Regras do Realtime Database (colar no console) |
| `manifest.webmanifest`, `icon*.png`, `icon.svg` | Permite instalar na tela inicial do celular |

## 1. Firebase

1. Crie um projeto em <https://console.firebase.google.com> (ou use um que já tenha).
2. **Authentication › Sign-in method**: ative **E-mail/senha**.
3. **Authentication › Settings › Authorized domains**: adicione `oreonsolucoes.github.io`.
4. **Realtime Database**: crie o banco e, na aba **Regras**, cole o conteúdo de `database.rules.json` e publique.
5. **Configurações do projeto › Seus apps**: crie um app Web e copie o objeto de configuração para `firebase-config.js`.

Os dados ficam em `listaCompras/casa/compras` e `listaCompras/casa/itens`. Todas as contas que entrarem compartilham o mesmo espaço `casa`. Para separar, troque `LISTA_ESPACO` em `firebase-config.js`.

## 2. GitHub Pages

1. Crie o repositório `oreonsolucoes/lista-de-compras`.
2. Envie todos os arquivos desta pasta para a raiz do branch `main`.
3. **Settings › Pages**: Source = *Deploy from a branch*, Branch = `main` / `(root)`.
4. Em alguns minutos o app fica em <https://oreonsolucoes.github.io/lista-de-compras/>.

Pelo terminal:

```bash
git init
git add .
git commit -m "Lista de Compras"
git branch -M main
git remote add origin https://github.com/oreonsolucoes/lista-de-compras.git
git push -u origin main
```

## 3. No celular

Abra o link, entre com sua conta e use **Adicionar à tela inicial** (Chrome: menu ⋮; Safari: Compartilhar). O app abre em tela cheia como um aplicativo.
