# Meu Aplicador

App de pesquisa de ações da B3: busca por nome ou ticker, histórico de preços, proventos, indicadores com mediana do setor e comparação com Ibovespa, CDI e IPCA.

## Testar no navegador

Abra `www/index.html` no navegador (ou o arquivo `index.html` avulso, que já traz tudo dentro).
Sem chave, funcionam as ações de teste PETR4, VALE3, ITUB4 e MGLU3. Para as demais, crie uma chave gratuita em https://brapi.dev e cole em "Chave da API".

## Gerar o APK pelo GitHub (sem instalar nada)

1. Crie um repositório no GitHub e envie esta pasta inteira (incluindo a pasta `.github`).
2. Abra a aba **Actions** do repositório. O fluxo "Gerar APK" roda sozinho a cada envio para `main` (ou clique em "Run workflow").
3. Ao terminar (cerca de 5 minutos), abra a execução e baixe o arquivo `meu-aplicador-apk` em **Artifacts**. Dentro do .zip está o `app-debug.apk`.

## Gerar o APK no computador

Requer Node 20+, Java 21 e Android Studio (com o Android SDK 35).

```
npm install
npx cap sync android
cd android
./gradlew assembleDebug
```

O APK fica em `android/app/build/outputs/apk/debug/app-debug.apk`.

## Instalar no celular

Copie o APK para o Android, abra o arquivo e permita "instalar apps desconhecidos" quando o sistema pedir.
Este é um APK de teste (debug). Para publicar na Play Store é preciso gerar um pacote assinado (`./gradlew bundleRelease` com uma chave de assinatura).

## Alterar o app

O código está em `www/index.html`. Depois de editar, rode `npx cap sync android` antes de gerar o APK de novo.
