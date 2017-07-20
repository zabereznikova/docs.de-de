---
title: "Voraussetzungen für .NET Core unter Mac | Microsoft-Dokumentation"
description: "Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: 2aa685751fae9fa9771fa1cd86d211f742e06932
ms.contentlocale: de-de
ms.lasthandoff: 07/05/2017

---

<a id="prerequisites-for-net-core-on-mac" class="xliff"></a>

# Voraussetzungen für .NET Core unter Mac

Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen. Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

<a id="supported-macos-versions" class="xliff"></a>

## Unterstützte macOS-Versionen

.NET Core wird von den folgenden Versionen von macOS unterstützt:

* macOS 10.12 „Sierra“
* macOS 10.11 „El Capitan“

Eine umfassende Liste mit unterstützten Betriebssystemen finden Sie unter [.NET Core Release Notes (Versionshinweise zu .NET Core.)](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

<a id="net-core-dependencies" class="xliff"></a>

## .NET Core-Abhängigkeiten

**.NET Core 1.x**

.NET Core 1.x erfordert unter macOS OpenSSL. Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS. Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich das Thema [Known issues & workarounds (Bekannte Probleme & Problemumgehungen)](https://github.com/dotnet/core/blob/master/cli/known-issues.md) an.

**.NET Core 2.x**

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich das Thema [Known issues & workarounds (Bekannte Probleme & Problemumgehungen)](https://github.com/dotnet/core/blob/master/cli/known-issues.md) an.

<a id="visual-studio-for-mac" class="xliff"></a>

## Visual Studio für Mac

Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:

* Eine unterstützte Version eines macOS-Betriebssystems
* OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)
* .NET Core SDK für Mac
* [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

