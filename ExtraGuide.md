## Guide

### Create Project

```bash
yarn create react-native-app -t with-workbox
```

### Create app.json and build the content like below

```json
{
    "expo": {
        "name": "expo-react-native-pwa",
        "slug": "expo-react-native-pwa",
        "version": "1.0.0",
        "orientation": "portrait",
        "icon": "./assets/images/icon.png",
        "scheme": "myapp",
        "userInterfaceStyle": "automatic",
        "splash": {
          "image": "./assets/images/splash.png",
          "resizeMode": "contain",
          "backgroundColor": "#ffffff"
        },
        "updates": {
          "fallbackToCacheTimeout": 0
        },
        "assetBundlePatterns": [
          "**/*"
        ],
        "ios": {
          "supportsTablet": true
        },
        "android": {
          "adaptiveIcon": {
            "foregroundImage": "./assets/images/adaptive-icon.png",
            "backgroundColor": "#ffffff"
          },
          "package": "com.anonymous.expopwa"
        },
        "web": {
          "favicon": "./assets/images/favicon.png",
          "themeColor": "#ffffff"
        }
    }
}
```

### Build web

```bash
npx expo export:web
```

### Update manifest(Need to add below code to solve maskable icon in pwa)

```manifest.json
    {
      "src": "\\pwa\\chrome-icon\\chrome-icon-512.png",
      "sizes": "512x512",
      "type": "image/png",
      "purpose": "maskable"
    }
```

### Expo commands

```bash
npm i -g expo/cli
npm i -g sharp-cli@^2.1.0
npm i -g expo-pwa
```

```bash
npx expo export:web
npx expo prebuild
npx expo-pwa manifest (Not used in this project)
```
