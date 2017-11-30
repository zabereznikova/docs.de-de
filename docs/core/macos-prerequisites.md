---
title: "Voraussetzungen für .NET Core unter Mac"
description: "Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 16f3cfd482bddfff1b9ad56e7ffe58ae2aed4980
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="bf41c-104">Voraussetzungen für die .NET Core auf macOS</span><span class="sxs-lookup"><span data-stu-id="bf41c-104">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="bf41c-105">Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bf41c-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="bf41c-106">Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="bf41c-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="bf41c-107">Unterstützte macOS-Versionen</span><span class="sxs-lookup"><span data-stu-id="bf41c-107">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bf41c-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bf41c-108">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="bf41c-109">.NET Core 2.x wird unter den folgenden Versionen von Mac OS unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bf41c-109">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="bf41c-110">MacOS 10.12 "Sierra" und höher</span><span class="sxs-lookup"><span data-stu-id="bf41c-110">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="bf41c-111">Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="bf41c-111">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bf41c-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bf41c-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bf41c-113">.NET Core 1.x wird unter den folgenden Versionen von Mac OS unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bf41c-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="bf41c-114">macOS 10.12 „Sierra“</span><span class="sxs-lookup"><span data-stu-id="bf41c-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="bf41c-115">macOS 10.11 „El Capitan“</span><span class="sxs-lookup"><span data-stu-id="bf41c-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="bf41c-116">Unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die komplette Liste der Betriebssysteme, die von .NET Core 1.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="bf41c-116">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="bf41c-117">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="bf41c-117">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bf41c-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bf41c-118">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="bf41c-119">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="bf41c-119">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="bf41c-120">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Known issues (Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.0) an.</span><span class="sxs-lookup"><span data-stu-id="bf41c-120">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bf41c-121">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bf41c-121">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bf41c-122">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="bf41c-122">**.NET Core 1.x**</span></span>

<span data-ttu-id="bf41c-123">.NET Core 1.x erfordert unter macOS OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="bf41c-123">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="bf41c-124">Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS.</span><span class="sxs-lookup"><span data-stu-id="bf41c-124">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="bf41c-125">Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):</span><span class="sxs-lookup"><span data-stu-id="bf41c-125">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="bf41c-126">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="bf41c-126">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="bf41c-127">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich die Themen [1.0.0 Known Issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known Issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) an.</span><span class="sxs-lookup"><span data-stu-id="bf41c-127">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

---

## <a name="increase-the-maximum-open-file-limit"></a><span data-ttu-id="bf41c-128">Erhöhen Sie die maximale Dateigröße für öffnen</span><span class="sxs-lookup"><span data-stu-id="bf41c-128">Increase the maximum open file limit</span></span>

<span data-ttu-id="bf41c-129">Das Standardlimit für die geöffnete Datei auf MacOS möglicherweise nicht ausreichend, damit einige .NET Core-arbeitsauslastungen, z. B. das Wiederherstellen von Projekten oder Ausführen von Komponententests.</span><span class="sxs-lookup"><span data-stu-id="bf41c-129">The default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="bf41c-130">Sie können diesen Höchstwert vergrößern, indem Sie die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="bf41c-130">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="bf41c-131">Mit einem Texteditor eine neue Datei erstellen _/Library/LaunchDaemons/limit.maxfiles.plist_, und speichern Sie die Datei mit diesem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="bf41c-131">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

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

2. <span data-ttu-id="bf41c-132">Führen Sie in der terminal-Fenster den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="bf41c-132">In a terminal window, run the following command:</span></span>

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. <span data-ttu-id="bf41c-133">Neustart von Ihrem Mac, um diese Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bf41c-133">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="bf41c-134">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="bf41c-134">Visual Studio for Mac</span></span>

<span data-ttu-id="bf41c-135">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf41c-135">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="bf41c-136">Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://www.visualstudio.com/vs/visual-studio-mac/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf41c-136">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="bf41c-137">Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf41c-137">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="bf41c-138">Eine unterstützte Version eines macOS-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="bf41c-138">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="bf41c-139">OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)</span><span class="sxs-lookup"><span data-stu-id="bf41c-139">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="bf41c-140">.NET Core SDK für Mac</span><span class="sxs-lookup"><span data-stu-id="bf41c-140">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="bf41c-141">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="bf41c-141">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)
