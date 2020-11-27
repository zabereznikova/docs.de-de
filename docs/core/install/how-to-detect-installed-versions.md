---
title: Überprüfen der Installation von .NET-Versionen unter Windows, Linux und macOS (.NET)
description: Hier erfahren Sie, wie Sie die auf Ihrem Computer installierten .NET-Versionen auflisten. Zu den Versionen zählen die .NET-Runtime und das SDK.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 39020a32cdea9b82dc9d30e62e663ebc4ee39ebb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687441"
---
# <a name="how-to-check-that-net-is-already-installed"></a><span data-ttu-id="23619-104">Überprüfen, ob .NET bereits installiert ist</span><span class="sxs-lookup"><span data-stu-id="23619-104">How to check that .NET is already installed</span></span>

<span data-ttu-id="23619-105">In diesem Artikel erfahren Sie, wie Sie überprüfen, welche Versionen der .NET-Runtime und des SDK auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="23619-105">This article teaches you how to check which versions of the .NET runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="23619-106">.NET wurde möglicherweise bereits installiert, wenn Sie eine integrierte Entwicklungsumgebung wie Visual Studio oder Visual Studio für Mac besitzen.</span><span class="sxs-lookup"><span data-stu-id="23619-106">.NET may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="23619-107">Durch das Installieren eines SDK wird die entsprechende Runtime installiert.</span><span class="sxs-lookup"><span data-stu-id="23619-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="23619-108">Falls ein beliebiger Befehl in diesem Artikel fehlschlägt, haben Sie die Runtime oder den SDK nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="23619-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="23619-109">Weitere Informationen finden Sie in den Installationsartikeln für [Windows](windows.md), [macOS](macos.md) und [Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="23619-109">For more information, see the install articles for [Windows](windows.md), [macOS](macos.md), or [Linux](linux.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="23619-110">Überprüfen der SDK-Versionen</span><span class="sxs-lookup"><span data-stu-id="23619-110">Check SDK versions</span></span>

<span data-ttu-id="23619-111">Sie können sehen, welche Versionen des .NET SDK aktuell mit einem Terminal installiert sind.</span><span class="sxs-lookup"><span data-stu-id="23619-111">You can see which versions of the .NET SDK are currently installed with a terminal.</span></span> <span data-ttu-id="23619-112">Öffnen Sie ein Terminal, und führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="23619-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="23619-113">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="23619-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
5.0.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
5.0.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
5.0.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="23619-114">Überprüfen der Runtime-Versionen</span><span class="sxs-lookup"><span data-stu-id="23619-114">Check runtime versions</span></span>

<span data-ttu-id="23619-115">Mit dem folgenden Befehl können Sie feststellen, welche Versionen der .NET-Runtime derzeit installiert sind.</span><span class="sxs-lookup"><span data-stu-id="23619-115">You can see which versions of the .NET runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="23619-116">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="23619-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 5.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 5.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="23619-117">Überprüfen auf Installationsordner</span><span class="sxs-lookup"><span data-stu-id="23619-117">Check for install folders</span></span>

<span data-ttu-id="23619-118">Es ist möglich, dass .NET installiert ist, für Ihr Betriebssystem oder Benutzerprofil jedoch nicht zur `PATH`-Variable hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="23619-118">It's possible that .NET is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="23619-119">Das Ausführen der Befehle aus den vorherigen Abschnitten funktioniert möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="23619-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="23619-120">Alternativ können Sie überprüfen, ob die .NET-Installationsordner vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="23619-120">As an alternative, you can check that the .NET install folders exist.</span></span>

<span data-ttu-id="23619-121">Wenn Sie .NET über ein Installationsprogramm oder ein Skript installieren, wird es in einem Standardordner installiert.</span><span class="sxs-lookup"><span data-stu-id="23619-121">When you install .NET from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="23619-122">Meistens bietet das Installationsprogramm oder das Skript, das Sie für die Installation von .NET verwenden, die Möglichkeit, in einen anderen Ordner zu installieren.</span><span class="sxs-lookup"><span data-stu-id="23619-122">Much of the time the installer or script you're using to install .NET gives you an option to install to a different folder.</span></span> <span data-ttu-id="23619-123">Wenn Sie in einen anderen Ordner installieren möchten, passen Sie den Anfang des Ordnerpfads an.</span><span class="sxs-lookup"><span data-stu-id="23619-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="23619-124">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="23619-124">**dotnet executable**</span></span>\
<span data-ttu-id="23619-125">_C:\\Programme\\dotnet\\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="23619-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="23619-126">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="23619-126">**.NET SDK**</span></span>\
<span data-ttu-id="23619-127">_C:\\Programme\\dotnet\\sdk\\{Version}\\_</span><span class="sxs-lookup"><span data-stu-id="23619-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="23619-128">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="23619-128">**.NET Runtime**</span></span>\
<span data-ttu-id="23619-129">_C:\\Programme\\dotnet\\shared\\{Laufzeittyp}\\{Version}\\_</span><span class="sxs-lookup"><span data-stu-id="23619-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="23619-130">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="23619-130">**dotnet executable**</span></span>\
<span data-ttu-id="23619-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="23619-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="23619-132">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="23619-132">**.NET SDK**</span></span>\
<span data-ttu-id="23619-133">_/home/user/share/dotnet/sdk/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="23619-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="23619-134">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="23619-134">**.NET Runtime**</span></span>\
<span data-ttu-id="23619-135">_/home/user/share/dotnet/shared/{Laufzeittyp}/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="23619-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="23619-136">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="23619-136">**dotnet executable**</span></span>\
<span data-ttu-id="23619-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="23619-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="23619-138">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="23619-138">**.NET SDK**</span></span>\
<span data-ttu-id="23619-139">_/usr/local/share/dotnet/sdk/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="23619-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="23619-140">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="23619-140">**.NET Runtime**</span></span>\
<span data-ttu-id="23619-141">_/usr/local/share/dotnet/shared/{Laufzeittyp}/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="23619-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="23619-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23619-142">More information</span></span>

<span data-ttu-id="23619-143">Sie können sowohl die SDK-Versionen als auch die Runtime-Versionen mit dem `dotnet --info`-Befehl sehen.</span><span class="sxs-lookup"><span data-stu-id="23619-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="23619-144">Sie erhalten auch umgebungsbezogene Informationen, wie z. B. die Betriebssystemversion und den Laufzeitbezeichner (Runtime Identifier, RID).</span><span class="sxs-lookup"><span data-stu-id="23619-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="23619-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="23619-145">Next steps</span></span>

- <span data-ttu-id="23619-146">[Installieren Sie die .NET-Runtime und das SDK für Windows](windows.md).</span><span class="sxs-lookup"><span data-stu-id="23619-146">[Install the .NET Runtime and SDK for Windows](windows.md).</span></span>
- <span data-ttu-id="23619-147">[Installieren von .NET unter macOS](macos.md)</span><span class="sxs-lookup"><span data-stu-id="23619-147">[Install the .NET Runtime and SDK for macOS](macos.md).</span></span>
- <span data-ttu-id="23619-148">[Installieren Sie die .NET-Runtime und das SDK für Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="23619-148">[Install the .NET Runtime and SDK for Linux](linux.md).</span></span>
