---
title: "Voraussetzungen für .NET Core unter Mac"
description: "Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="85300-104">Voraussetzungen für .NET Core unter Mac</span><span class="sxs-lookup"><span data-stu-id="85300-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="85300-105">Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="85300-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="85300-106">Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="85300-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="85300-107">Unterstützte macOS-Versionen</span><span class="sxs-lookup"><span data-stu-id="85300-107">Supported macOS versions</span></span>

<span data-ttu-id="85300-108">.NET Core wird von folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="85300-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="85300-109">macOS 10.12 „Sierra“</span><span class="sxs-lookup"><span data-stu-id="85300-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="85300-110">macOS 10.11 „El Capitan“ (nur .NET Core 1.x)</span><span class="sxs-lookup"><span data-stu-id="85300-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="85300-111">Eine umfassende Liste mit unterstützten Betriebssystemen finden Sie unter [Supported OS Versions (Unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions).</span><span class="sxs-lookup"><span data-stu-id="85300-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="85300-112">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="85300-112">.NET Core dependencies</span></span>

<span data-ttu-id="85300-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="85300-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="85300-114">.NET Core 1.x erfordert unter macOS OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="85300-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="85300-115">Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS.</span><span class="sxs-lookup"><span data-stu-id="85300-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="85300-116">Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):</span><span class="sxs-lookup"><span data-stu-id="85300-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="85300-117">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="85300-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="85300-118">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich die Themen [1.0.0 Known Issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known Issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) an.</span><span class="sxs-lookup"><span data-stu-id="85300-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="85300-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="85300-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="85300-120">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="85300-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="85300-121">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Known issues (Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) an.</span><span class="sxs-lookup"><span data-stu-id="85300-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="85300-122">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="85300-122">Visual Studio for Mac</span></span>

<span data-ttu-id="85300-123">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="85300-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="85300-124">Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="85300-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="85300-125">Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="85300-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="85300-126">Eine unterstützte Version eines macOS-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="85300-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="85300-127">OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)</span><span class="sxs-lookup"><span data-stu-id="85300-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="85300-128">.NET Core SDK für Mac</span><span class="sxs-lookup"><span data-stu-id="85300-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="85300-129">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="85300-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

