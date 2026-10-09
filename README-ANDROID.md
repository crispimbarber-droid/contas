# CONTAS — pacote PWA para Android

Este pacote prepara a instalação do app como aplicativo web (PWA) no Android, com nome, ícones, abertura em tela própria e cache básico para carregar a interface offline.

## Publicar gratuitamente no GitHub Pages
1. Entre no GitHub e crie um repositório chamado `contas` (pode ser público).
2. Envie **todo o conteúdo desta pasta** para a raiz do repositório: `index.html`, `manifest.json`, `sw.js` e a pasta `icons`.
3. No repositório, abra **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**, escolha `main` e `/ (root)` e salve.
5. Aguarde a publicação e abra o endereço HTTPS informado pelo GitHub Pages no Chrome do Android.
6. No Chrome, toque no menu ⋮ e escolha **Instalar app** ou **Adicionar à tela inicial**.

## Importante antes de usar com dados financeiros reais
- O HTML atual salva os dados em `localStorage` no aparelho/navegador. Isso não compartilha automaticamente os dados entre dois celulares e pode ser perdido se os dados do navegador forem apagados.
- A tela de configuração do Supabase atualmente salva URL/chave, mas a função de sincronização encontrada no código apenas mostra uma mensagem simulada; ela **não sincroniza os registros com o banco**.
- Portanto, esta entrega prepara a instalação PWA, mas ainda **não é uma versão pronta para guardar dados financeiros compartilhados na nuvem**. Antes de uso real por duas pessoas, é necessário implementar autenticação, sincronização real, convites e validar as políticas RLS do arquivo `supabase_schema.sql`.
- Nunca coloque uma chave `service_role` no HTML. No cliente, use apenas a chave pública/anon do Supabase com autenticação e políticas RLS corretamente configuradas.
- A instalação PWA não é um APK e não publica o app na Google Play Store. Para Play Store, será necessário empacotar e testar separadamente.

## Arquivos
- `index.html`: interface do aplicativo original selecionada para o pacote.
- `manifest.json`: nome, ícones e configurações de instalação.
- `sw.js`: service worker para cache básico e carregamento offline da interface.
- `icons/`: ícones do aplicativo.
