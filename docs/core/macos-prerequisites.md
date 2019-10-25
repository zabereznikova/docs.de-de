---
title: Voraussetzungen für .NET Core unter Mac
description: Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.
author: thraka
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 10/11/2019
ms.openlocfilehash: 2d4fc0b37be08988440325db8b507124c36bf053
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318321"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Erforderliche Komponenten für .NET Core unter macOS

Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen. Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

## <a name="downloads-and-dependencies"></a>Downloads und Abhängigkeiten

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 wird unter **macOS High Sierra (Version 10.13)** und höher unterstützt. Hierzu ist eine **x64**-CPU-Architektur erforderlich.

Laden Sie das .NET Core SDK von der Seite [.NET Core 3.0-Downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) herunter, und installieren Sie es. Unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 3.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Eine Liste mit bekannten Probleme finden Sie unter [Bekannte Probleme bei .NET Core](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md).

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 wird unter **macOS Sierra (Version 10.12)** und höher unterstützt. Hierzu ist eine **x64**-CPU-Architektur erforderlich.

Laden Sie das .NET Core SDK von der Seite [.NET Core 2.2-Downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2) herunter, und installieren Sie es. Unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.2 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Eine Liste mit bekannten Probleme finden Sie unter [Bekannte Probleme bei .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 wird unter **macOS Sierra (Version 10.12)** und höher unterstützt. Hierzu ist eine **x64**-CPU-Architektur erforderlich.

Laden Sie das .NET Core SDK von der Seite [.NET Core 2.1-Downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1) herunter, und installieren Sie es. Unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Eine Liste mit bekannten Probleme finden Sie unter [Bekannte Probleme bei .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md).

---

## <a name="libgdiplus"></a>libgdiplus

Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.

Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS. Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):

```console
brew update
brew install libgdiplus
```

## <a name="visual-studio-for-mac"></a>Visual Studio für Mac

Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) verwenden.
