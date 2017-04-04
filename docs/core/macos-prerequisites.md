---
title: "Voraussetzungen für .NET Core unter Mac | Microsoft-Dokumentation"
description: "Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: da75f5fd56b7ce66b2c46ef488e6e26c55a63ee2
ms.lasthandoff: 03/20/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Voraussetzungen für .NET Core unter Mac

Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen. Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code (VS Code)](https://code.visualstudio.com/), und [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Unterstützte macOS-Versionen

.NET Core wird von den folgenden Versionen von macOS unterstützt:

* macOS 10.12 „Sierra“
* macOS 10.11 „El Capitan“

Eine umfassende Liste mit unterstützten Betriebssystemen finden Sie unter [.NET Core Release Notes (Versionshinweise zu .NET Core.)](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

.NET Core erfordert unter macOS OpenSSL. Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](http://brew.sh/)-Paket-Managers für macOS. Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):

```Terminal
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Nach der Installation von OpenSSL, erhalten Sie den offiziellen [.NET Core SDK für Mac-Installer](https://go.microsoft.com/fwlink/?linkid=843444). .NET Core 1.1.1 ist die neueste Version. Langfristig unterstützte Versionen und weitere Downloads finden Sie unter [.NET Downloads: All downloads (.NET Downloads: alle Downloads)](https://www.microsoft.com/net/download/core). Wenn Sie Probleme bei der Installation auf macOS haben, wenden Sie sich an [Known issues & workarounds (Bekannte Probleme & Problemumgehungen)](https://github.com/dotnet/core/blob/master/cli/known-issues.md).

## <a name="visual-studio-for-mac"></a>Visual Studio für Mac

Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:

* Eine unterstützte Version eines macOS-Betriebssystems
* OpenSSL
* .NET Core SDK für Mac
* [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

