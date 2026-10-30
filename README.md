# Arquivo de Casos

Controle da coleção de escape rooms e mystery games. Site estático (GitHub Pages) com dados compartilhados em tempo real no Firebase.

## Arquivos

- `index.html` — o app inteiro.
- `firebase-config.js` — a configuração do seu projeto Firebase (preencher uma vez).
- `firestore.rules` — regras de segurança para colar no Firebase.

Sem o `firebase-config.js` preenchido, o site abre em **modo demonstração** (dados só no navegador).

## Passo a passo

### 1. Firebase (banco de dados)
1. Entre em https://console.firebase.google.com com sua conta Google → **Adicionar projeto** → nome `arquivo-de-casos` (pode desligar o Google Analytics).
2. Menu **Build → Firestore Database → Criar banco de dados** → escolha a região `southamerica-east1 (São Paulo)` → modo **produção**.
3. Na aba **Regras** do Firestore, apague tudo, cole o conteúdo de `firestore.rules` e clique **Publicar**.
4. Menu **Build → Authentication → Vamos começar → Método de login → Anônimo → Ativar → Salvar**.
5. Engrenagem ⚙️ → **Configurações do projeto** → em "Seus apps", clique no ícone **`</>`** (Web) → apelido `site` → **Registrar app**. Copie os valores do objeto `firebaseConfig` que aparecem.
6. Cole esses valores no arquivo `firebase-config.js`.

### 2. GitHub Pages (o site)
1. Crie conta em https://github.com (se ainda não tiver).
2. **New repository** → nome `arquivo-de-casos` → **Public** → Create.
3. **Add file → Upload files** → arraste `index.html`, `firebase-config.js`, `firestore.rules` e `README.md` → **Commit changes**.
4. **Settings → Pages** → Source: **Deploy from a branch** → Branch `main` / `(root)` → **Save**.
5. Em 1–2 minutos o site fica em `https://SEU-USUARIO.github.io/arquivo-de-casos/`.

### 3. Trazer os dados
Abra o site → aparece "Arquivo vazio" → **Importar backup** → escolha o JSON exportado do app antigo. Pronto: todos que abrirem o link veem e editam os mesmos dados, ao vivo.

## No dia a dia
- Mudanças aparecem na hora para todo mundo com o site aberto.
- Funciona offline: as alterações ficam guardadas no aparelho e sobem quando a internet voltar.
- **Menu ⋯ → Exportar backup** de vez em quando, já que qualquer pessoa com o link pode editar.
- No celular: compartilhar → **Adicionar à tela de início** para abrir como app.
- Plano gratuito do Firebase: 50 mil leituras/dia. Cada abertura "do zero" lê ~430 itens (≈ 100 aberturas novas por dia); reabrir em menos de ~30 min quase não gasta leituras (usa o cache do aparelho).
