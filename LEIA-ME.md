# Orbi Demo — como gerar o APK

App de demonstração (marca fictícia, dados fictícios). A interface está em `www/index.html`.

## Opção A — sem instalar nada (GitHub Actions)
1. Crie um repositório no GitHub e envie todos os arquivos desta pasta (incluindo `.github`).
2. Vá em Actions > "Build APK" > Run workflow.
3. Ao terminar, baixe o artefato `orbi-demo-apk` (contém `app-debug.apk`).
4. No celular, permita "instalar apps desconhecidos" e abra o APK.

## Opção B — no seu computador (Node 20 + Java 17 + Android Studio)
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
O APK fica em `android/app/build/outputs/apk/debug/app-debug.apk`.

## Observação
A câmera de QR Code pede permissão: depois de `cap add android`, adicione em
`android/app/src/main/AndroidManifest.xml`:
`<uses-permission android:name="android.permission.CAMERA" />`
