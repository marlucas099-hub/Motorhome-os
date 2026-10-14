# Motorhome OS — projeto Android para testes

Este é o **código-fonte Android**, não um APK pronto. Usa o protótipo HTML corrigido dentro de um WebView com origem HTTPS local (`WebViewAssetLoader`), funcionando sem rede.

## Gerar APK de testes
1. Instale **Android Studio** no computador.
2. Extraia este ZIP e abra a pasta `MotorhomeOS_Android_Projeto` em **Open**.
3. Aguarde o Gradle sincronizar (requer internet para baixar ferramentas/dependências).
4. No menu, escolha **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. O arquivo de teste estará em `app/build/outputs/apk/debug/app-debug.apk`.
6. Envie-o ao celular Android e permita a instalação desse arquivo somente se confiar na origem.

## Limitações importantes
- **Não existe login de funcionários ainda**. Não publicar na Play Store como se houvesse controle de acesso.
- Dados ficam no armazenamento local do aplicativo, **sem sincronização** entre celulares e PCs. Desinstalar ou limpar os dados do app pode apagá-los.
- Exportação de backup via link `blob:` e impressão via `window.print()` podem não funcionar no WebView; precisam de implementação nativa antes de uso real.
- Fotos/anexos e outras funcionalidades ainda precisam de testes de ponta a ponta.
- Este APK é para testes; para Play Store, criar assinatura de release, gerar **AAB**, atualizar `targetSdk` conforme exigência vigente, preencher Play Console e políticas de privacidade/dados.
- O pacote não inclui `gradlew` nem `gradle-wrapper.jar`; o Android Studio pode solicitar configurar o Gradle instalado. Não foi compilado neste ambiente.

## Próximos passos para produção
1. Autenticação real por funcionário com backend e perfis.
2. Banco central, controle de acesso por oficina, sincronização offline e resolução de conflitos.
3. Impressão/PDF e exportação de backup nativos.
4. Testes em dispositivos, política de privacidade, publicação AAB assinada.
