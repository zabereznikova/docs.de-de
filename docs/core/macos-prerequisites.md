---
title: Voraussetzungen für .NET Core unter Mac
description: Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: b1f4d3b49be7ba5349197187d6576b78db58798c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219078"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Erforderliche Komponenten für .NET Core unter macOS

Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen. Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Unterstützte macOS-Versionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x wird von folgenden macOS-Versionen unterstützt:

* macOS 10.12 „Sierra“ und höher

Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x wird von folgenden macOS-Versionen unterstützt:

* macOS 10.12 „Sierra“
* macOS 10.11 „El Capitan“

Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

---

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Known issues (Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) an.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.x**

.NET Core 1.x erfordert unter macOS OpenSSL. Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS. Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich die Themen [1.0.0 Known Issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known Issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) an.

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a>Erhöhen des Limits für die maximale Anzahl von geöffneten Dateien (.NET Core Versionen vor .NET Core SDK 2.0.2) 

In früheren Versionen von .NET Core (vor .NET Core SDK 2.0.2) ist das Standardlimit für geöffnete Dateien unter macOS für einige .NET Core-Workloads möglicherweise nicht ausreichend, z.B. für das Wiederherstellen von Projekten oder das Ausführen von Komponententests.

Sie können dieses Limit erhöhen, indem Sie diese Schritte befolgen:

1. Erstellen Sie mithilfe eines Text-Editors die neue Datei _/Library/LaunchDaemons/limit.maxfiles.plist_, und speichern Sie die Datei mit diesem Inhalt:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. Führen Sie in einem Terminalfenster folgenden Befehl aus:

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. Starten Sie Ihren Mac neu, um diese Einstellungen zu übernehmen.

## <a name="visual-studio-for-mac"></a>Visual Studio für Mac

Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/) verwenden. 

Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:

* Eine unterstützte Version eines macOS-Betriebssystems
* OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)
* .NET Core SDK für Mac
* [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/)
