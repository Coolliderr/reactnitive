## 📌 LINK App 无 Git 打包 APK 流程

1✅、检查node.js
```bash
node -v
npm -v
```

2✅、创建expo项目
```bash
npx create-expo-app@latest link
cd link
```

3✅、安装 Expo Router 相关依赖
```bash
npx expo install expo-router react-native-safe-area-context react-native-screens react-native-gesture-handler react-native-reanimated
npx expo install @expo/vector-icons
npx expo install @react-native-async-storage/async-storage
```

4✅、安装 Web3 钱包依赖
```bash
npm install @walletconnect/react-native-compat
npm install @reown/appkit-react-native @reown/appkit-wagmi-react-native wagmi viem @tanstack/react-query
npm install react-native-get-random-values buffer process
```

5✅、启动开发环境
```bash
npx expo start -c
```
6✅、安装 EAS CLI
```bash
npm install -g eas-cli
```
7✅、登录 Expo
```bash
eas login
```

8✅、初始化 EAS Build 配置
```bash
eas build:configure
```

9✅、检查项目
```bash
npx expo doctor
```

10✅、配置eas.json
```bash
{
  "cli": {
    "version": ">= 12.0.0",
    "appVersionSource": "remote"
  },
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      }
    },
    "production": {
      "android": {
        "buildType": "app-bundle"
      }
    }
  }
}
```

11✅、打包 Android APK
```bash
$env:EAS_NO_VCS=1
eas build --platform android --profile preview
```

12✅、下载 APK
```bash
https://expo.dev/accounts/wangyuane/projects/link/builds/ca1545ea-641b-4c68-a423-46fffe4f9931
```
