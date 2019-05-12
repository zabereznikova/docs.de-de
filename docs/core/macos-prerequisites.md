---
title: Voraussetzungen für .NET Core unter Mac
description: Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.
author: guardrex
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 12/14/2018
ms.openlocfilehash: 3f5dce25ed03061d690432684975909d15bbad57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64752955"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="7d952-103">Erforderliche Komponenten für .NET Core unter macOS</span><span class="sxs-lookup"><span data-stu-id="7d952-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="7d952-104">Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d952-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="7d952-105">Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="7d952-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="7d952-106">Unterstützte macOS-Versionen</span><span class="sxs-lookup"><span data-stu-id="7d952-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7d952-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7d952-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7d952-108">.NET Core 2.x wird von folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7d952-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="7d952-109">macOS 10.12 „Sierra“ und höher</span><span class="sxs-lookup"><span data-stu-id="7d952-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="7d952-110">Unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) und [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 und .NET Core 2.2 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7d952-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="7d952-111">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 2.2-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) oder [.NET Core 2.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="7d952-111">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7d952-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7d952-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7d952-113">.NET Core 1.x wird von folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7d952-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="7d952-114">macOS 10.12 „Sierra“</span><span class="sxs-lookup"><span data-stu-id="7d952-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="7d952-115">macOS 10.11 „El Capitan“</span><span class="sxs-lookup"><span data-stu-id="7d952-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="7d952-116">Unter [Von .NET Core 1.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) und [Von .NET Core 1.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 1.1 und .NET Core 1.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7d952-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="7d952-117">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 1.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) oder [.NET Core 1.0-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span><span class="sxs-lookup"><span data-stu-id="7d952-117">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="7d952-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7d952-118">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7d952-119">.NET Core 3.0 Vorschauversion 3 wird von folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7d952-119">.NET Core 3.0 Preview 3 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="7d952-120">macOS 10.12 „Sierra“ und höher</span><span class="sxs-lookup"><span data-stu-id="7d952-120">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="7d952-121">Unter [.NET Core 3.0 Supported OS Versions (Von .NET Core 3.0 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 3.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7d952-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="7d952-122">Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 3.0-Downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="7d952-122">For download links and more information, see [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="7d952-123">.NET Core-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7d952-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7d952-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7d952-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7d952-125">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="7d952-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="7d952-126">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Known issues (Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.1) an.</span><span class="sxs-lookup"><span data-stu-id="7d952-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7d952-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7d952-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7d952-128">.NET Core 1.x erfordert unter macOS OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="7d952-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="7d952-129">Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS.</span><span class="sxs-lookup"><span data-stu-id="7d952-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="7d952-130">Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):</span><span class="sxs-lookup"><span data-stu-id="7d952-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="7d952-131">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="7d952-131">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="7d952-132">Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich die Themen [1.0.0 Known Issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known Issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) an.</span><span class="sxs-lookup"><span data-stu-id="7d952-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="7d952-133">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7d952-133">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="7d952-134">Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="7d952-134">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="7d952-135">Wenn Sie Probleme bei der Installation unter macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Anmerkungen zu dieser Version](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) an.</span><span class="sxs-lookup"><span data-stu-id="7d952-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="7d952-136">Erhöhen des Limits für die maximale Anzahl von geöffneten Dateien (.NET Core Versionen vor .NET Core SDK 2.0.2)</span><span class="sxs-lookup"><span data-stu-id="7d952-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span>

<span data-ttu-id="7d952-137">In früheren Versionen von .NET Core (vor .NET Core SDK 2.0.2) ist das Standardlimit für geöffnete Dateien unter macOS für einige .NET Core-Workloads möglicherweise nicht ausreichend, z.B. für das Wiederherstellen von Projekten oder das Ausführen von Komponententests.</span><span class="sxs-lookup"><span data-stu-id="7d952-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="7d952-138">Sie können dieses Limit erhöhen, indem Sie diese Schritte befolgen:</span><span class="sxs-lookup"><span data-stu-id="7d952-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="7d952-139">Erstellen Sie mithilfe eines Text-Editors die neue Datei _/Library/LaunchDaemons/limit.maxfiles.plist_, und speichern Sie die Datei mit diesem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="7d952-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
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

2. <span data-ttu-id="7d952-140">Führen Sie in einem Terminalfenster folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d952-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="7d952-141">Starten Sie Ihren Mac neu, um diese Einstellungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7d952-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="7d952-142">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="7d952-142">Visual Studio for Mac</span></span>

<span data-ttu-id="7d952-143">Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d952-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="7d952-144">Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d952-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

<span data-ttu-id="7d952-145">Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7d952-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="7d952-146">Eine unterstützte Version eines macOS-Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="7d952-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="7d952-147">OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)</span><span class="sxs-lookup"><span data-stu-id="7d952-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="7d952-148">.NET Core SDK für Mac</span><span class="sxs-lookup"><span data-stu-id="7d952-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="7d952-149">Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="7d952-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
