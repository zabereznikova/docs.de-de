---
title: Überprüfen der Installation von .NET Core-Versionen unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie, wie Sie auflisten, welche .NET Core-Versionen auf Ihrem Computer installiert sind. Zu den Versionen zählen die .NET Core-Runtime und das .NET Core SDK.
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: b8825dee595c601e8adef0a52e651ac4a4f04831
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416038"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="53c2e-104">Überprüfen, ob .NET Core bereits installiert ist</span><span class="sxs-lookup"><span data-stu-id="53c2e-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="53c2e-105">In diesem Artikel erfahren Sie, wie Sie überprüfen, welche Versionen der .NET Core-Runtime und des .NET Core SDK auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="53c2e-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="53c2e-106">.NET Core wurde möglicherweise bereits installiert, wenn Sie eine integrierte Entwicklungsumgebung wie z. B. Visual Studio oder Visual Studio für Mac besitzen.</span><span class="sxs-lookup"><span data-stu-id="53c2e-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="53c2e-107">Durch das Installieren eines SDK wird die entsprechende Runtime installiert.</span><span class="sxs-lookup"><span data-stu-id="53c2e-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="53c2e-108">Falls ein beliebiger Befehl in diesem Artikel fehlschlägt, haben Sie die Runtime oder den SDK nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="53c2e-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="53c2e-109">Weitere Informationen finden Sie in den Installationsartikeln für [Windows](windows.md), [macOS](macos.md) und [Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="53c2e-109">For more information, see the install articles for [Windows](windows.md), [macOS](macos.md), or [Linux](linux.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="53c2e-110">Überprüfen der SDK-Versionen</span><span class="sxs-lookup"><span data-stu-id="53c2e-110">Check SDK versions</span></span>

<span data-ttu-id="53c2e-111">Sie können sehen, welche Versionen des .NET Core SDK aktuell mit einem Terminal installiert sind.</span><span class="sxs-lookup"><span data-stu-id="53c2e-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="53c2e-112">Öffnen Sie ein Terminal, und führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="53c2e-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="53c2e-113">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="53c2e-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="53c2e-114">Überprüfen der Runtime-Versionen</span><span class="sxs-lookup"><span data-stu-id="53c2e-114">Check runtime versions</span></span>

<span data-ttu-id="53c2e-115">Mit dem folgenden Befehl können Sie feststellen, welche Versionen der .NET Core-Runtime derzeit installiert sind.</span><span class="sxs-lookup"><span data-stu-id="53c2e-115">You can see which versions of the .NET Core runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="53c2e-116">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="53c2e-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="53c2e-117">Überprüfen auf Installationsordner</span><span class="sxs-lookup"><span data-stu-id="53c2e-117">Check for install folders</span></span>

<span data-ttu-id="53c2e-118">Es ist möglich, dass .NET Core installiert ist, für Ihr Betriebssystem oder Benutzerprofil jedoch nicht zur `PATH`-Variable hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="53c2e-118">It's possible that .NET Core is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="53c2e-119">Das Ausführen der Befehle aus den vorherigen Abschnitten funktioniert möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="53c2e-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="53c2e-120">Alternativ können Sie überprüfen, ob die .NET Core-Installationsordner vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="53c2e-120">As an alternative, you can check that the .NET Core install folders exist.</span></span>

<span data-ttu-id="53c2e-121">Wenn Sie .NET Core über einen Installer oder ein Skript installieren, wird es in einem Standardordner installiert.</span><span class="sxs-lookup"><span data-stu-id="53c2e-121">When you install .NET Core from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="53c2e-122">Meistens bietet der Installer oder das Skript, den oder das Sie für die Installation von .NET Core verwenden, die Möglichkeit, in einen anderen Ordner zu installieren.</span><span class="sxs-lookup"><span data-stu-id="53c2e-122">Much of the time the installer or script you're using to install .NET Core gives you an option to install to a different folder.</span></span> <span data-ttu-id="53c2e-123">Wenn Sie in einen anderen Ordner installieren möchten, passen Sie den Anfang des Ordnerpfads an.</span><span class="sxs-lookup"><span data-stu-id="53c2e-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="53c2e-124">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="53c2e-124">**dotnet executable**</span></span>\
<span data-ttu-id="53c2e-125">_C:\\Programme\\dotnet\\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="53c2e-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="53c2e-126">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="53c2e-126">**.NET SDK**</span></span>\
<span data-ttu-id="53c2e-127">_C:\\Programme\\dotnet\\sdk\\{Version}\\_</span><span class="sxs-lookup"><span data-stu-id="53c2e-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="53c2e-128">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="53c2e-128">**.NET Runtime**</span></span>\
<span data-ttu-id="53c2e-129">_C:\\Programme\\dotnet\\shared\\{Laufzeittyp}\\{Version}\\_</span><span class="sxs-lookup"><span data-stu-id="53c2e-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="53c2e-130">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="53c2e-130">**dotnet executable**</span></span>\
<span data-ttu-id="53c2e-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="53c2e-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="53c2e-132">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="53c2e-132">**.NET SDK**</span></span>\
<span data-ttu-id="53c2e-133">_/home/user/share/dotnet/sdk/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="53c2e-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="53c2e-134">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="53c2e-134">**.NET Runtime**</span></span>\
<span data-ttu-id="53c2e-135">_/home/user/share/dotnet/shared/{Laufzeittyp}/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="53c2e-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="53c2e-136">**Ausführbare dotnet-Datei**</span><span class="sxs-lookup"><span data-stu-id="53c2e-136">**dotnet executable**</span></span>\
<span data-ttu-id="53c2e-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="53c2e-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="53c2e-138">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="53c2e-138">**.NET SDK**</span></span>\
<span data-ttu-id="53c2e-139">_/usr/local/share/dotnet/sdk/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="53c2e-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="53c2e-140">**.NET-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="53c2e-140">**.NET Runtime**</span></span>\
<span data-ttu-id="53c2e-141">_/usr/local/share/dotnet/shared/{Laufzeittyp}/{Version}/_</span><span class="sxs-lookup"><span data-stu-id="53c2e-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="53c2e-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53c2e-142">More information</span></span>

<span data-ttu-id="53c2e-143">Sie können sowohl die SDK-Versionen als auch die Runtime-Versionen mit dem `dotnet --info`-Befehl sehen.</span><span class="sxs-lookup"><span data-stu-id="53c2e-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="53c2e-144">Sie erhalten auch umgebungsbezogene Informationen, wie z. B. die Betriebssystemversion und den Laufzeitbezeichner (Runtime Identifier, RID).</span><span class="sxs-lookup"><span data-stu-id="53c2e-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="53c2e-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="53c2e-145">Next steps</span></span>

- <span data-ttu-id="53c2e-146">[Installieren Sie die .NET Core-Runtime und das .NET Core SDK.](windows.md)</span><span class="sxs-lookup"><span data-stu-id="53c2e-146">[Install the .NET Core Runtime and SDK](windows.md).</span></span>
