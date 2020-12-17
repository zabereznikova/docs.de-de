---
title: Bestimmen der installierten .NET Framework-Versionen
description: Verwenden von Code, regedit.exe oder PowerShell, um über eine Abfrage der Windows-Registrierung zu ermitteln, welche .NET Framework-Versionen auf einem Computer installiert sind
ms.date: 12/04/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining installed versions
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: a219514fafdcb17db259e089afa8318dbab24811
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851828"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="a06e4-103">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="a06e4-103">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="a06e4-104">Benutzer können mehrere Versionen des .NET Frameworks auf einem Computer [installieren](../install/index.md) und ausführen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-104">Users can [install](../install/index.md) and run multiple versions of .NET Framework on their computers.</span></span> <span data-ttu-id="a06e4-105">Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen des .NET Frameworks auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a06e4-105">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user's computer.</span></span> <span data-ttu-id="a06e4-106">Die Registrierung enthält eine Liste der auf einem Computer installierten .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-106">The registry contains a list of the versions of .NET Framework installed on the computer.</span></span>

> [!NOTE]
> <span data-ttu-id="a06e4-107">Dieser Artikel gilt für das .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a06e4-107">This article is specific to .NET Framework.</span></span> <span data-ttu-id="a06e4-108">Informationen dazu, welche SDKs und Runtimes von .NET Core und .NET 5 oder höher installiert sind, finden Sie unter [Überprüfen der Installation von .NET](../../core/install/how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="a06e4-108">To determine which .NET Core and .NET 5+ SDKs and runtimes are installed, see [How to check that .NET is already installed](../../core/install/how-to-detect-installed-versions.md).</span></span>

<span data-ttu-id="a06e4-109">Das .NET Framework besteht aus zwei Hauptkomponenten mit separaten Versionen:</span><span class="sxs-lookup"><span data-stu-id="a06e4-109">.NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="a06e4-110">Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-110">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="a06e4-111">.NET Framework und Assemblys verwenden die gleiche Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="a06e4-111">.NET Framework and the assemblies share the same version number.</span></span> <span data-ttu-id="a06e4-112">Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="a06e4-112">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>

- <span data-ttu-id="a06e4-113">Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-113">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="a06e4-114">Eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-114">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="a06e4-115">Beispiel: Die Version 4.0.30319.*xxxxx* der CLR (wobei *xxxxx* kleiner als 42000 ist) unterstützt die Versionen 4 bis 4.5.2 des .NET Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a06e4-115">For example, CLR version 4.0.30319.*xxxxx* where *xxxxx* is less than 42000, supports .NET Framework versions 4 through 4.5.2.</span></span> <span data-ttu-id="a06e4-116">Ab Version 4.0.30319.42000 unterstützt die CLR Version 4.6 und höher des .NET Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a06e4-116">CLR version greater than or equal to 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>

<span data-ttu-id="a06e4-117">Mithilfe von Tools, die von der Community verwaltet werden, können Sie ermittelt, welche .NET Framework-Versionen installiert sind:</span><span class="sxs-lookup"><span data-stu-id="a06e4-117">Community-maintained tools are available to help detect which .NET Framework versions are installed:</span></span>

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  <span data-ttu-id="a06e4-118">Ein Befehlszeilentool für .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="a06e4-118">A .NET Framework 2.0 command-line tool.</span></span>

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  <span data-ttu-id="a06e4-119">Ein Modul für PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="a06e4-119">A PowerShell 2.0 module.</span></span>

<span data-ttu-id="a06e4-120">Informationen zum Ermitteln der installierten Updates für jede Version des .NET Frameworks finden Sie unter [Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="a06e4-120">For information about detecting the installed updates for each version of .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="determine-which-net-implementation-and-version-an-app-is-running-on"></a><span data-ttu-id="a06e4-121">Ermitteln der .NET-Implementierung und -Version einer App</span><span class="sxs-lookup"><span data-stu-id="a06e4-121">Determine which .NET implementation and version an app is running on</span></span>

<span data-ttu-id="a06e4-122">Sie können die <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>-Eigenschaft verwenden, um abzufragen, welche .NET-Implementierung und -Version Ihre App nutzt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-122">You can use the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property to query for which .NET implementation and version your app is running on.</span></span> <span data-ttu-id="a06e4-123">Wenn die App auf dem .NET Framework ausgeführt wird, sieht die Ausgabe in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="a06e4-123">If the app is running on .NET Framework, the output will be similar to:</span></span>

```output
.NET Framework 4.8.4250.0
```

<span data-ttu-id="a06e4-124">Im Vergleich dazu, sieht die Ausgabe wie folgt aus, wenn die App mit .NET Core oder .NET 5 oder höher ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a06e4-124">By comparison, if the app is running on .NET Core or .NET 5+, the output will be similar to:</span></span>

```output
.NET Core 3.1.9
.NET 5.0.0
```

## <a name="detect-net-framework-45-and-later-versions"></a><span data-ttu-id="a06e4-125">Erkennen von .NET Framework 4.5 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="a06e4-125">Detect .NET Framework 4.5 and later versions</span></span>

<span data-ttu-id="a06e4-126">Die Version des .NET Frameworks (4.5 und höher), die auf einem Computer installiert ist, wird in der Registrierung unter **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\NET Framework Setup\\NDP\\V4\\Full** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-126">The version of .NET Framework (4.5 and later) installed on a machine is listed in the registry at **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.</span></span> <span data-ttu-id="a06e4-127">Wenn der Unterschlüssel **Full** fehlt, ist weder .NET Framework 4.5 noch eine höhere Version installiert.</span><span class="sxs-lookup"><span data-stu-id="a06e4-127">If the **Full** subkey is missing, then .NET Framework 4.5 or above isn't installed.</span></span>

> [!NOTE]
> <span data-ttu-id="a06e4-128">Der Unterschlüssel **NET Framework Setup** im Registrierungspfad beginnt *nicht* mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-128">The **NET Framework Setup** subkey in the registry path does *not* begin with a period.</span></span>

<span data-ttu-id="a06e4-129">Der **Release**-Wert REG_DWORD in der Registrierung steht für die installierte .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="a06e4-129">The **Release** REG_DWORD value in the registry represents the version of .NET Framework installed.</span></span>

<a name="version_table"></a>

| <span data-ttu-id="a06e4-130">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="a06e4-130">.NET Framework version</span></span> | <span data-ttu-id="a06e4-131">**Release**-Wert</span><span class="sxs-lookup"><span data-stu-id="a06e4-131">Value of **Release**</span></span> |
| ---------------------- | -------------------------- |
| <span data-ttu-id="a06e4-132">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a06e4-132">.NET Framework 4.5</span></span>     | <span data-ttu-id="a06e4-133">Alle Windows-Betriebssysteme: 378389</span><span class="sxs-lookup"><span data-stu-id="a06e4-133">All Windows operating systems: 378389</span></span> |
| <span data-ttu-id="a06e4-134">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-134">.NET Framework 4.5.1</span></span>   | <span data-ttu-id="a06e4-135">Für Windows 8.1 und Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="a06e4-135">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="a06e4-136">Für alle anderen Windows-Betriebssysteme: 378758</span><span class="sxs-lookup"><span data-stu-id="a06e4-136">On all other Windows operating systems: 378758</span></span> |
| <span data-ttu-id="a06e4-137">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-137">.NET Framework 4.5.2</span></span>   | <span data-ttu-id="a06e4-138">Alle Windows-Betriebssysteme: 379893</span><span class="sxs-lookup"><span data-stu-id="a06e4-138">All Windows operating systems: 379893</span></span> |
| <span data-ttu-id="a06e4-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="a06e4-139">.NET Framework 4.6</span></span>     | <span data-ttu-id="a06e4-140">Für Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="a06e4-140">On Windows 10: 393295</span></span><br /><span data-ttu-id="a06e4-141">Für alle anderen Windows-Betriebssysteme: 393297</span><span class="sxs-lookup"><span data-stu-id="a06e4-141">On all other Windows operating systems: 393297</span></span> |
| <span data-ttu-id="a06e4-142">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-142">.NET Framework 4.6.1</span></span>   | <span data-ttu-id="a06e4-143">Für Windows 10 November Update-Systeme: 394254</span><span class="sxs-lookup"><span data-stu-id="a06e4-143">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="a06e4-144">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="a06e4-144">On all other Windows operating systems (including Windows 10): 394271</span></span> |
| <span data-ttu-id="a06e4-145">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-145">.NET Framework 4.6.2</span></span>   | <span data-ttu-id="a06e4-146">Auf Systemen unter Windows 10 Anniversary Update und Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="a06e4-146">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="a06e4-147">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 394806</span><span class="sxs-lookup"><span data-stu-id="a06e4-147">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span> |
| <span data-ttu-id="a06e4-148">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a06e4-148">.NET Framework 4.7</span></span>     | <span data-ttu-id="a06e4-149">Für Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="a06e4-149">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="a06e4-150">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 460805</span><span class="sxs-lookup"><span data-stu-id="a06e4-150">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span> |
| <span data-ttu-id="a06e4-151">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-151">.NET Framework 4.7.1</span></span>   | <span data-ttu-id="a06e4-152">Für Windows 10 Fall Creators Update und Windows Server Version 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="a06e4-152">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="a06e4-153">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 461310</span><span class="sxs-lookup"><span data-stu-id="a06e4-153">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span> |
| <span data-ttu-id="a06e4-154">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-154">.NET Framework 4.7.2</span></span>   | <span data-ttu-id="a06e4-155">Für Windows 10 April 2018 Update und Windows Server Version 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="a06e4-155">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="a06e4-156">Für alle anderen Betriebssysteme als Windows 10 April 2018 Update und Windows Server Version 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="a06e4-156">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span> |
| <span data-ttu-id="a06e4-157">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="a06e4-157">.NET Framework 4.8</span></span>     | <span data-ttu-id="a06e4-158">Unter Windows 10 Update aus Mai 2019 und Windows 10 Update aus November 2019: 528040</span><span class="sxs-lookup"><span data-stu-id="a06e4-158">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="a06e4-159">Unter Windows 10 Update von Mai 2020 und Windows 10 Update von Oktober 2020: 528372</span><span class="sxs-lookup"><span data-stu-id="a06e4-159">On Windows 10 May 2020 Update and Windows 10 October 2020 Update: 528372</span></span><br/><span data-ttu-id="a06e4-160">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 528049</span><span class="sxs-lookup"><span data-stu-id="a06e4-160">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span> |

### <a name="minimum-version"></a><span data-ttu-id="a06e4-161">Mindestversion</span><span class="sxs-lookup"><span data-stu-id="a06e4-161">Minimum version</span></span>

<span data-ttu-id="a06e4-162">Wenn Sie bestimmen möchten, ob eine *Mindestversion* des .NET Framework vorhanden ist, suchen Sie nach einem REG_DWORD-Wert des **Release**, der höher oder gleich dem entsprechenden in der folgenden Tabelle aufgeführten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-162">To determine whether a *minimum* version of .NET Framework is present, check for a **Release** REG_DWORD value that's greater than or equal to the corresponding value listed in the following table.</span></span> <span data-ttu-id="a06e4-163">Wenn Ihre Anwendung beispielsweise unter .NET Framework 4.8 oder einer höheren Version ausgeführt wird, testen Sie, ob der **Releasewert** für REG_DWORD *größer oder gleich* 528040 ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-163">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **Release** REG_DWORD value that's *greater than or equal to* 528040.</span></span>

| <span data-ttu-id="a06e4-164">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="a06e4-164">.NET Framework version</span></span> | <span data-ttu-id="a06e4-165">Minimalwert</span><span class="sxs-lookup"><span data-stu-id="a06e4-165">Minimum value</span></span> |
| ---------------------- | ------------- |
| <span data-ttu-id="a06e4-166">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a06e4-166">.NET Framework 4.5</span></span>     | <span data-ttu-id="a06e4-167">378389</span><span class="sxs-lookup"><span data-stu-id="a06e4-167">378389</span></span> |
| <span data-ttu-id="a06e4-168">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-168">.NET Framework 4.5.1</span></span>   | <span data-ttu-id="a06e4-169">378675</span><span class="sxs-lookup"><span data-stu-id="a06e4-169">378675</span></span> |
| <span data-ttu-id="a06e4-170">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-170">.NET Framework 4.5.2</span></span>   | <span data-ttu-id="a06e4-171">379893</span><span class="sxs-lookup"><span data-stu-id="a06e4-171">379893</span></span> |
| <span data-ttu-id="a06e4-172">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="a06e4-172">.NET Framework 4.6</span></span>     | <span data-ttu-id="a06e4-173">393295</span><span class="sxs-lookup"><span data-stu-id="a06e4-173">393295</span></span> |
| <span data-ttu-id="a06e4-174">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-174">.NET Framework 4.6.1</span></span>   | <span data-ttu-id="a06e4-175">394254</span><span class="sxs-lookup"><span data-stu-id="a06e4-175">394254</span></span> |
| <span data-ttu-id="a06e4-176">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-176">.NET Framework 4.6.2</span></span>   | <span data-ttu-id="a06e4-177">394802</span><span class="sxs-lookup"><span data-stu-id="a06e4-177">394802</span></span> |
| <span data-ttu-id="a06e4-178">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="a06e4-178">.NET Framework 4.7</span></span>     | <span data-ttu-id="a06e4-179">460798</span><span class="sxs-lookup"><span data-stu-id="a06e4-179">460798</span></span> |
| <span data-ttu-id="a06e4-180">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-180">.NET Framework 4.7.1</span></span>   | <span data-ttu-id="a06e4-181">461308</span><span class="sxs-lookup"><span data-stu-id="a06e4-181">461308</span></span> |
| <span data-ttu-id="a06e4-182">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="a06e4-182">.NET Framework 4.7.2</span></span>   | <span data-ttu-id="a06e4-183">461808</span><span class="sxs-lookup"><span data-stu-id="a06e4-183">461808</span></span> |
| <span data-ttu-id="a06e4-184">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="a06e4-184">.NET Framework 4.8</span></span>     | <span data-ttu-id="a06e4-185">528040</span><span class="sxs-lookup"><span data-stu-id="a06e4-185">528040</span></span> |

### <a name="use-registry-editor"></a><span data-ttu-id="a06e4-186">Verwenden des Registrierungs-Editors</span><span class="sxs-lookup"><span data-stu-id="a06e4-186">Use Registry Editor</span></span>

1. <span data-ttu-id="a06e4-187">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

   <span data-ttu-id="a06e4-188">(Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.)</span><span class="sxs-lookup"><span data-stu-id="a06e4-188">(You must have administrative credentials to run regedit.)</span></span>

1. <span data-ttu-id="a06e4-189">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.</span></span> <span data-ttu-id="a06e4-190">Wenn der Unterschlüssel **Full** nicht vorhanden ist, wurde .NET Framework 4.5 oder höher nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="a06e4-190">If the **Full** subkey isn't present, then you don't have .NET Framework 4.5 or later installed.</span></span>

1. <span data-ttu-id="a06e4-191">Suchen Sie nach einem REG_DWORD-Eintrag mit dem Namen **Release**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-191">Check for a REG_DWORD entry named **Release**.</span></span> <span data-ttu-id="a06e4-192">Wenn dieser vorhanden ist, haben Sie .NET Framework 4.5 oder höher installiert.</span><span class="sxs-lookup"><span data-stu-id="a06e4-192">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="a06e4-193">Der zugehörige Wert entspricht einer bestimmten Version des .NET Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a06e4-193">Its value corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="a06e4-194">In der folgenden Abbildung weist der Eintrag **Release** beispielsweise den Wert 528040 auf, was dem Releaseschlüssel für .NET Framework 4.8 entspricht.</span><span class="sxs-lookup"><span data-stu-id="a06e4-194">In the following figure, for example, the value of the **Release** entry is 528040, which is the release key for .NET Framework 4.8.</span></span>

   ![Registrierungseintrag für .NET Framework 4.5](./media/clr-installdir.png )

### <a name="use-powershell-to-check-for-a-minimum-version"></a><span data-ttu-id="a06e4-196">Verwenden von PowerShell zum Prüfen auf eine Mindestversion</span><span class="sxs-lookup"><span data-stu-id="a06e4-196">Use PowerShell to check for a minimum version</span></span>

<span data-ttu-id="a06e4-197">Verwenden Sie PowerShell-Befehle, um den Wert des Eintrags **Release** des Unterschlüssels **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-197">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** subkey.</span></span>

<span data-ttu-id="a06e4-198">In den folgenden Beispielen wird der Wert des Eintrags **Release** überprüft, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-198">The following examples check the value of the **Release** entry to determine whether .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="a06e4-199">Dieser Code gibt `True` zurück, wenn es installiert ist, und andernfalls `False`.</span><span class="sxs-lookup"><span data-stu-id="a06e4-199">This code returns `True` if it's installed and `False` otherwise.</span></span>

```powershell
(Get-ItemProperty "HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a><span data-ttu-id="a06e4-200">Abfragen der Registrierung mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="a06e4-200">Query the registry using code</span></span>

01. <span data-ttu-id="a06e4-201">Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>, um auf den Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-201">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** subkey in the Windows registry.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a06e4-202">Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="a06e4-202">If the app you're running is 32-bit and running in 64-bit Windows, the registry paths will be different than previously listed.</span></span> <span data-ttu-id="a06e4-203">Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a06e4-203">The 64-bit registry is available in the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** subkey.</span></span> <span data-ttu-id="a06e4-204">Der Registrierungsunterschlüssel für .NET Framework 4.5 ist beispielsweise **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-204">For example, the registry subkey for .NET Framework 4.5 is **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.</span></span>

01. <span data-ttu-id="a06e4-205">Überprüfen Sie den **Release**-Wert für REG_DWORD, um die installierte Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-205">Check the **Release** REG_DWORD value to determine the installed version.</span></span> <span data-ttu-id="a06e4-206">Suchen Sie einen Wert größer als oder gleich dem Wert, der in der [.NET Framework-Versionstabelle](#version_table) aufgeführt ist, um die Aufwärtskompatibilität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-206">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="a06e4-207">Im folgenden Beispiel wird der Wert des Eintrags **Release** in der Registrierung überprüft, um die installierten Versionen von .NET Framework 4.5–4.8 und höher zu suchen:</span><span class="sxs-lookup"><span data-stu-id="a06e4-207">The following example checks the value of the **Release** entry in the registry to find the versions of .NET Framework 4.5-4.8 that are installed:</span></span>

:::code language="csharp" source="snippets/csharp/versions-installed.cs" id="2":::

:::code language="vb" source="snippets/visual-basic/versions-installed.vb" id="2":::

<span data-ttu-id="a06e4-208">In diesem Beispiel wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a06e4-208">The example displays output like the following:</span></span>

```output
.NET Framework Version: 4.6.1
```

<span data-ttu-id="a06e4-209">In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:</span><span class="sxs-lookup"><span data-stu-id="a06e4-209">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="a06e4-210">Es wird überprüft, ob der Wert des Eintrags \**Release\*\*\*größer als der oder gleich dem* Wert der bekannten Releaseschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-210">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>
- <span data-ttu-id="a06e4-211">Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.</span><span class="sxs-lookup"><span data-stu-id="a06e4-211">It checks in order from most recent version to earliest version.</span></span>

## <a name="detect-net-framework-10-through-40"></a><span data-ttu-id="a06e4-212">Erkennen der Versionen 1.0 bis 4.0 des .NET Frameworks</span><span class="sxs-lookup"><span data-stu-id="a06e4-212">Detect .NET Framework 1.0 through 4.0</span></span>

<span data-ttu-id="a06e4-213">Jede Version von .NET Framework zwischen den Versionen 1.1 und 4.0 wird unter **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** als Unterschlüssel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-213">Each version of .NET Framework from 1.1 to 4.0 is listed as a subkey at **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP**.</span></span> <span data-ttu-id="a06e4-214">In der folgenden Tabelle wird der Pfad zu den einzelnen .NET Framework-Versionen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a06e4-214">The following table lists the path to each .NET Framework version.</span></span> <span data-ttu-id="a06e4-215">Für die meisten Versionen gibt es einen **Install**-Wert für REG_DWORD von `1`, der angibt, dass die jeweilige Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-215">For most versions, there's an **Install** REG_DWORD value of `1` to indicate this version is installed.</span></span> <span data-ttu-id="a06e4-216">In diesen Unterschlüsseln gibt es auch einen **Version**-Wert für REG_SZ, der eine Versionszeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="a06e4-216">In these subkeys, there's also a **Version** REG_SZ value that contains a version string.</span></span>

> [!NOTE]
> <span data-ttu-id="a06e4-217">Der Unterschlüssel **NET Framework Setup** im Registrierungspfad beginnt *nicht* mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-217">The **NET Framework Setup** subkey in the registry path does *not* begin with a period.</span></span>

| <span data-ttu-id="a06e4-218">Framework-Version</span><span class="sxs-lookup"><span data-stu-id="a06e4-218">Framework Version</span></span>  | <span data-ttu-id="a06e4-219">Registrierungsunterschlüssel</span><span class="sxs-lookup"><span data-stu-id="a06e4-219">Registry Subkey</span></span> | <span data-ttu-id="a06e4-220">Wert</span><span class="sxs-lookup"><span data-stu-id="a06e4-220">Value</span></span> |
| ------------------ | --------------- | ----- |
| <span data-ttu-id="a06e4-221">1.0</span><span class="sxs-lookup"><span data-stu-id="a06e4-221">1.0</span></span>                | <span data-ttu-id="a06e4-222">**HKLM\\Software\\Microsoft\\.NETFramework\\Policy\\v1.0\\3705**</span><span class="sxs-lookup"><span data-stu-id="a06e4-222">**HKLM\\Software\\Microsoft\\.NETFramework\\Policy\\v1.0\\3705**</span></span>     | <span data-ttu-id="a06e4-223">**Install**-Wert für REG_SZ entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-223">**Install** REG_SZ equals `1`</span></span> |
| <span data-ttu-id="a06e4-224">1.1</span><span class="sxs-lookup"><span data-stu-id="a06e4-224">1.1</span></span>                | <span data-ttu-id="a06e4-225">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v1.1.4322**</span><span class="sxs-lookup"><span data-stu-id="a06e4-225">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v1.1.4322**</span></span>   | <span data-ttu-id="a06e4-226">**Install**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-226">**Install** REG_DWORD equals `1`</span></span> |
| <span data-ttu-id="a06e4-227">2.0</span><span class="sxs-lookup"><span data-stu-id="a06e4-227">2.0</span></span>                | <span data-ttu-id="a06e4-228">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v2.0.50727**</span><span class="sxs-lookup"><span data-stu-id="a06e4-228">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v2.0.50727**</span></span>  | <span data-ttu-id="a06e4-229">**Install**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-229">**Install** REG_DWORD equals `1`</span></span> |
| <span data-ttu-id="a06e4-230">3.0</span><span class="sxs-lookup"><span data-stu-id="a06e4-230">3.0</span></span>                | <span data-ttu-id="a06e4-231">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.0\\Setup**</span><span class="sxs-lookup"><span data-stu-id="a06e4-231">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.0\\Setup**</span></span> | <span data-ttu-id="a06e4-232">**InstallSuccess**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-232">**InstallSuccess** REG_DWORD equals `1`</span></span> |
| <span data-ttu-id="a06e4-233">3.5</span><span class="sxs-lookup"><span data-stu-id="a06e4-233">3.5</span></span>                | <span data-ttu-id="a06e4-234">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.5**</span><span class="sxs-lookup"><span data-stu-id="a06e4-234">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.5**</span></span>        | <span data-ttu-id="a06e4-235">**Install**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-235">**Install** REG_DWORD equals `1`</span></span> |
| <span data-ttu-id="a06e4-236">4.0, Clientprofil</span><span class="sxs-lookup"><span data-stu-id="a06e4-236">4.0 Client Profile</span></span> | <span data-ttu-id="a06e4-237">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Client**</span><span class="sxs-lookup"><span data-stu-id="a06e4-237">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Client**</span></span>  | <span data-ttu-id="a06e4-238">**Install**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-238">**Install** REG_DWORD equals `1`</span></span> |
| <span data-ttu-id="a06e4-239">4.0, vollständiges Profil</span><span class="sxs-lookup"><span data-stu-id="a06e4-239">4.0 Full Profile</span></span>   | <span data-ttu-id="a06e4-240">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**</span><span class="sxs-lookup"><span data-stu-id="a06e4-240">**HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**</span></span>    | <span data-ttu-id="a06e4-241">**Install**-Wert für REG_DWORD entspricht `1`</span><span class="sxs-lookup"><span data-stu-id="a06e4-241">**Install** REG_DWORD equals `1`</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="a06e4-242">Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="a06e4-242">If the app you're running is 32-bit and running in 64-bit Windows, the registry paths will be different than previously listed.</span></span> <span data-ttu-id="a06e4-243">Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a06e4-243">The 64-bit registry is available in the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** subkey.</span></span> <span data-ttu-id="a06e4-244">Beispielsweise lautet der Registrierungsunterschlüssel für .NET Framework 3.5 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-244">For example, the registry subkey for .NET Framework 3.5 is **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.</span></span>

<span data-ttu-id="a06e4-245">Hinweis: Der Registrierungspfad für den Unterschlüssel für .NET Framework 1.0 unterscheidet sich von dem anderer Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a06e4-245">Notice that the registry path to the .NET Framework 1.0 subkey is different from the others.</span></span>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="a06e4-246">Verwenden des Registrierungs-Editors (ältere Frameworkversionen)</span><span class="sxs-lookup"><span data-stu-id="a06e4-246">Use Registry Editor (older framework versions)</span></span>

01. <span data-ttu-id="a06e4-247">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-247">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="a06e4-248">Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a06e4-248">You must have administrative credentials to run regedit.</span></span>

01. <span data-ttu-id="a06e4-249">Öffnen Sie den Unterschlüssel, der der Version entspricht, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="a06e4-249">Open the subkey that matches the version you want to check.</span></span> <span data-ttu-id="a06e4-250">Verwenden Sie die Tabelle im Abschnitt [Erkennen der Versionen 1.0 bis 4.0 des .NET Frameworks](#detect-net-framework-10-through-40).</span><span class="sxs-lookup"><span data-stu-id="a06e4-250">Use the table in the [Detect .NET Framework 1.0 through 4.0](#detect-net-framework-10-through-40) section.</span></span>

    <span data-ttu-id="a06e4-251">Die folgende Abbildung zeigt den Unterschlüssel und dessen **Version**-Wert für .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="a06e4-251">The following figure shows the subkey and its **Version** value for .NET Framework 3.5.</span></span>

    <span data-ttu-id="a06e4-252">![Der Registrierungseintrag für .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 und frühere Versionen")</span><span class="sxs-lookup"><span data-stu-id="a06e4-252">![The registry entry for .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="a06e4-253">Abfragen der Registrierung mithilfe von Code (ältere Frameworkversionen)</span><span class="sxs-lookup"><span data-stu-id="a06e4-253">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="a06e4-254">Verwenden Sie die Klasse <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, um in der Windows-Registrierung auf den Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-254">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** subkey in the Windows registry.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a06e4-255">Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="a06e4-255">If the app you're running is 32-bit and running in 64-bit Windows, the registry paths will be different than previously listed.</span></span> <span data-ttu-id="a06e4-256">Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a06e4-256">The 64-bit registry is available in the **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** subkey.</span></span> <span data-ttu-id="a06e4-257">Beispielsweise lautet der Registrierungsunterschlüssel für .NET Framework 3.5 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="a06e4-257">For example, the registry subkey for .NET Framework 3.5 is **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.</span></span>

<span data-ttu-id="a06e4-258">Im folgenden Beispiel werden die installierten .NET Framework-Versionen 1–4 ermittelt:</span><span class="sxs-lookup"><span data-stu-id="a06e4-258">The following example finds the versions of .NET Framework 1-4 that are installed:</span></span>

:::code language="csharp" source="snippets/csharp/versions-installed.cs" id="1":::

:::code language="vb" source="snippets/visual-basic/versions-installed.vb" id="1":::

<span data-ttu-id="a06e4-259">Die Konsole zeigt eine Ausgabe an, die der folgenden in etwa entspricht:</span><span class="sxs-lookup"><span data-stu-id="a06e4-259">The example displays output similar to the following:</span></span>

```output
v2.0.50727  2.0.50727.4927  SP2
v3.0  3.0.30729.4926  SP2
v3.5  3.5.30729.4926  SP1
v4.0
  Client  4.0.0.0
```

## <a name="find-clr-versions"></a><span data-ttu-id="a06e4-260">Suchen von CLR-Versionen</span><span class="sxs-lookup"><span data-stu-id="a06e4-260">Find CLR versions</span></span>

<span data-ttu-id="a06e4-261">Die mit dem für .NET Framework installierte CLR-Version wird separat bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-261">The .NET Framework CLR installed with .NET Framework is versioned separately.</span></span> <span data-ttu-id="a06e4-262">Es gibt zwei Möglichkeiten, die Version der .NET Framework-CLR zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="a06e4-262">There are two ways to detect the version of the .NET Framework CLR:</span></span>

- <span data-ttu-id="a06e4-263">**Das Tool Clrver.exe**</span><span class="sxs-lookup"><span data-stu-id="a06e4-263">**The Clrver.exe tool**</span></span>

  <span data-ttu-id="a06e4-264">Verwenden Sie das [CLR-Versionstool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md), um zu ermitteln, welche Versionen der CLR auf einem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a06e4-264">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer.</span></span> <span data-ttu-id="a06e4-265">Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md), und geben Sie `clrver` ein.</span><span class="sxs-lookup"><span data-stu-id="a06e4-265">Open the [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md) and enter `clrver`.</span></span>

  <span data-ttu-id="a06e4-266">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="a06e4-266">Sample output:</span></span>

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- <span data-ttu-id="a06e4-267">**Die Klasse `Environment`**</span><span class="sxs-lookup"><span data-stu-id="a06e4-267">**The `Environment` class**</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="a06e4-268">Für .NET Framework 4.5 und höhere Versionen sollten Sie zum Ermitteln der CLR-Version nicht die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="a06e4-268">For .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="a06e4-269">Fragen Sie stattdessen wie im Abschnitt [Erkennen von .NET Framework 4.5 und höheren Versionen](#detect-net-framework-45-and-later-versions) beschrieben die Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="a06e4-269">Instead, query the registry as described in [Detect .NET Framework 4.5 and later versions](#detect-net-framework-45-and-later-versions).</span></span>

  1. <span data-ttu-id="a06e4-270">Fragen Sie die Eigenschaft <xref:System.Environment.Version?displayProperty=nameWithType> ab, um ein <xref:System.Version>-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a06e4-270">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

     <span data-ttu-id="a06e4-271">Das zurückgegebene `System.Version`-Objekt identifiziert die Version der Runtime, die gerade den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-271">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="a06e4-272">Es gibt keine Assemblyversionen oder andere Versionen der Runtime zurück, die möglicherweise auf dem Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a06e4-272">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="a06e4-273">Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 hat die Zeichenfolgendarstellung des zurückgegebenen <xref:System.Version>-Objekts das Format 4.0.30319.*xxxxx*, wobei *xxxxx* kleiner als 42000 ist.</span><span class="sxs-lookup"><span data-stu-id="a06e4-273">For .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="a06e4-274">Bei .NET Framework 4.6 und höheren Versionen weist es das Format 4.0.30319.42000 auf.</span><span class="sxs-lookup"><span data-stu-id="a06e4-274">For .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

  1. <span data-ttu-id="a06e4-275">Fragen Sie das erhaltene **Version**-Objekt wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="a06e4-275">After you have the **Version** object, query it as follows:</span></span>

     - <span data-ttu-id="a06e4-276">Verwenden Sie für den Hauptversionsbezeichner (zum Beispiel *4* für Version 4.0) die Eigenschaft <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a06e4-276">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

     - <span data-ttu-id="a06e4-277">Verwenden Sie für den Nebenversionsbezeichner (zum Beispiel *0* für Version 4.0) die Eigenschaft <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a06e4-277">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

     - <span data-ttu-id="a06e4-278">Verwenden Sie für die gesamte Versionszeichenfolge (zum Beispiel *4.0.30319.18010*) die Methode <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a06e4-278">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a06e4-279">Diese Methode gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="a06e4-279">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="a06e4-280">Sie gibt keine Assemblyversionen oder andere Runtimeversionen zurück, die möglicherweise auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a06e4-280">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

  <span data-ttu-id="a06e4-281">Im folgenden Beispiel wird die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwendet, um CLR-Versionsinformationen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="a06e4-281">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

  ```csharp
  Console.WriteLine($"Version: {Environment.Version}");
  ```

  ```vb
  Console.WriteLine($"Version: {Environment.Version}")
  ```

  <span data-ttu-id="a06e4-282">Die Konsole zeigt eine Ausgabe an, die der folgenden in etwa entspricht:</span><span class="sxs-lookup"><span data-stu-id="a06e4-282">The example displays output similar to the following:</span></span>

  ```output
  Version: 4.0.30319.18010
  ```

## <a name="see-also"></a><span data-ttu-id="a06e4-283">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a06e4-283">See also</span></span>

- [<span data-ttu-id="a06e4-284">How to: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes</span><span class="sxs-lookup"><span data-stu-id="a06e4-284">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="a06e4-285">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="a06e4-285">Install .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="a06e4-286">.NET Framework-Versionen und -Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="a06e4-286">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
