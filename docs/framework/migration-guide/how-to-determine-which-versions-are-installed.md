---
title: Bestimmen der installierten .NET Framework-Versionen
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738187"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="78be9-102">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="78be9-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="78be9-103">Benutzer können mehrere Versionen von .NET Framework auf einem Computer [installieren](../install/index.md) und ausführen.</span><span class="sxs-lookup"><span data-stu-id="78be9-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="78be9-104">Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="78be9-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="78be9-105">.NET Framework besteht aus zwei Hauptkomponenten mit separaten Versionen:</span><span class="sxs-lookup"><span data-stu-id="78be9-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="78be9-106">Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78be9-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="78be9-107">.NET Framework und Assemblys verwenden die gleiche Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="78be9-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="78be9-108">Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt.</span><span class="sxs-lookup"><span data-stu-id="78be9-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="78be9-109">Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="78be9-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="78be9-110">Jede neue Version von .NET Framework enthält weiterhin Funktionen aus den früheren Versionen und fügt neue Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="78be9-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="78be9-111">Sie können mehrere Versionen von .NET Framework gleichzeitig auf einen Computer laden. Somit können Sie .NET Framework installieren, ohne vorherige Versionen deinstallieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="78be9-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="78be9-112">Im Allgemeinen sollten Sie keine vorherigen Versionen von .NET Framework deinstallieren, da eine verwendete Anwendung möglicherweise von einer bestimmten Version abhängt und nicht mehr ausgeführt wird, wenn diese Version entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="78be9-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="78be9-113">Zwischen der .NET Framework-Version und der CLR-Version besteht ein Unterschied:</span><span class="sxs-lookup"><span data-stu-id="78be9-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="78be9-114">Die .NET Framework-Version basiert auf den Assemblys, die die .NET Framework-Klassenbibliothek bilden.</span><span class="sxs-lookup"><span data-stu-id="78be9-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="78be9-115">Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="78be9-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="78be9-116">Die CLR-Version basiert auf der Runtime, auf der .NET Framework-Anwendungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78be9-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="78be9-117">Eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="78be9-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="78be9-118">Die CLR-Version 4.0.30319.*xxxxx* unterstützt zum Beispiel die .NET Framework-Versionen 4 bis 4.5.2, wobei *xxxxx* kleiner ist als 42000. Die CLR-Version 4.0.30319.42000 unterstützt .NET Framework-Versionen ab .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="78be9-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="78be9-119">Weitere Informationen zu Versionen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="78be9-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="78be9-120">Die Registrierung enthält eine Liste der auf einem Computer installierten .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="78be9-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="78be9-121">Sie können die Registrierung entweder mit dem Registrierungs-Editor anzeigen oder mit Code abfragen:</span><span class="sxs-lookup"><span data-stu-id="78be9-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="78be9-122">Suchen von neueren .NET Framework-Versionen (4.5 und höher):</span><span class="sxs-lookup"><span data-stu-id="78be9-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="78be9-123">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="78be9-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="78be9-124">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="78be9-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="78be9-125">Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt</span><span class="sxs-lookup"><span data-stu-id="78be9-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="78be9-126">Suchen nach älteren .NET Framework-Versionen (1 bis 4):</span><span class="sxs-lookup"><span data-stu-id="78be9-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="78be9-127">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="78be9-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="78be9-128">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="78be9-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="78be9-129">Verwenden Sie ein Tool oder Code, um eine Liste der auf einem Computer installierten CLR-Versionen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="78be9-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="78be9-130">Suchen der aktuellen CLR-Version mit „Clrver.exe“</span><span class="sxs-lookup"><span data-stu-id="78be9-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="78be9-131">Suchen der aktuellen CLR-Version mit der Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="78be9-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="78be9-132">Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="78be9-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="78be9-133">Suchen von neueren .NET Framework-Versionen (4.5 und höher)</span><span class="sxs-lookup"><span data-stu-id="78be9-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="78be9-134">Sie können den Registrierungs-Editor verwenden, um Versionsinformationen in der Registrierung zu finden, oder Sie können die Registrierung programmgesteuert abfragen.</span><span class="sxs-lookup"><span data-stu-id="78be9-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="78be9-135">Verwenden des Registrierungs-Editors</span><span class="sxs-lookup"><span data-stu-id="78be9-135">Use Registry Editor</span></span>

1. <span data-ttu-id="78be9-136">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78be9-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="78be9-137">Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="78be9-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="78be9-138">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="78be9-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="78be9-139">Wenn der Unterschlüssel **Full** nicht vorhanden ist, wurde .NET Framework 4.5 oder höher nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="78be9-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78be9-140">Der Ordner **NET Framework Setup** in der Registrierung beginnt *nicht* mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="78be9-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="78be9-141">Suchen Sie nach einem DWORD-Eintrag mit dem Namen **Release**.</span><span class="sxs-lookup"><span data-stu-id="78be9-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="78be9-142">Wenn dieser vorhanden ist, haben Sie .NET Framework 4.5 oder höher installiert.</span><span class="sxs-lookup"><span data-stu-id="78be9-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="78be9-143">Der Wert ist ein Releaseschlüssel, der einer bestimmten Version des .NET Framework entspricht.</span><span class="sxs-lookup"><span data-stu-id="78be9-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="78be9-144">In der folgenden Abbildung weist der Eintrag **Release** beispielsweise den Wert 378389 auf, was dem Releaseschlüssel für .NET Framework 4.5 entspricht.</span><span class="sxs-lookup"><span data-stu-id="78be9-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="78be9-145">![Registrierungseintrag für .NET Framework 4.5](./media/clr-installdir.png "Registrierungseintrag für .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="78be9-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="78be9-146">Die folgende Tabelle enthält den Wert des **Release**-DWORD für einzelne Betriebssysteme für .NET Framework 4.5 und höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="78be9-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="78be9-147">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="78be9-147">.NET Framework version</span></span>|<span data-ttu-id="78be9-148">Wert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="78be9-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="78be9-149">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="78be9-149">.NET Framework 4.5</span></span>|<span data-ttu-id="78be9-150">Alle Windows-Betriebssysteme: 378389</span><span class="sxs-lookup"><span data-stu-id="78be9-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="78be9-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="78be9-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="78be9-152">Für Windows 8.1 und Windows Server 2012 R2: 378675</span><span class="sxs-lookup"><span data-stu-id="78be9-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="78be9-153">Für alle anderen Windows-Betriebssysteme: 378758</span><span class="sxs-lookup"><span data-stu-id="78be9-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="78be9-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="78be9-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="78be9-155">Alle Windows-Betriebssysteme: 379893</span><span class="sxs-lookup"><span data-stu-id="78be9-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="78be9-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="78be9-156">.NET Framework 4.6</span></span>|<span data-ttu-id="78be9-157">Für Windows 10: 393295</span><span class="sxs-lookup"><span data-stu-id="78be9-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="78be9-158">Für alle anderen Windows-Betriebssysteme: 393297</span><span class="sxs-lookup"><span data-stu-id="78be9-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="78be9-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="78be9-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="78be9-160">Für Windows 10 November Update-Systeme: 394254</span><span class="sxs-lookup"><span data-stu-id="78be9-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="78be9-161">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10): 394271</span><span class="sxs-lookup"><span data-stu-id="78be9-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="78be9-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="78be9-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="78be9-163">Auf Systemen unter Windows 10 Anniversary Update und Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="78be9-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="78be9-164">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 394806</span><span class="sxs-lookup"><span data-stu-id="78be9-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="78be9-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="78be9-165">.NET Framework 4.7</span></span>|<span data-ttu-id="78be9-166">Für Windows 10 Creators Update: 460798</span><span class="sxs-lookup"><span data-stu-id="78be9-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="78be9-167">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 460805</span><span class="sxs-lookup"><span data-stu-id="78be9-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="78be9-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="78be9-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="78be9-169">Für Windows 10 Fall Creators Update und Windows Server Version 1709: 461308</span><span class="sxs-lookup"><span data-stu-id="78be9-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="78be9-170">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 461310</span><span class="sxs-lookup"><span data-stu-id="78be9-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="78be9-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="78be9-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="78be9-172">Für Windows 10 April 2018 Update und Windows Server Version 1803: 461808</span><span class="sxs-lookup"><span data-stu-id="78be9-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="78be9-173">Für alle anderen Betriebssysteme als Windows 10 April 2018 Update und Windows Server Version 1803: 461814</span><span class="sxs-lookup"><span data-stu-id="78be9-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="78be9-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="78be9-174">.NET Framework 4.8</span></span>|<span data-ttu-id="78be9-175">Unter Windows 10 Update aus Mai 2019 und Windows 10 Update aus November 2019: 528040</span><span class="sxs-lookup"><span data-stu-id="78be9-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="78be9-176">Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 528049</span><span class="sxs-lookup"><span data-stu-id="78be9-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="78be9-177">Bestimmte Version</span><span class="sxs-lookup"><span data-stu-id="78be9-177">Specific version</span></span>

<span data-ttu-id="78be9-178">Um festzustellen, ob eine *bestimmte* Version von .NET Framework unter einer bestimmten Version des Windows-Betriebssystems installiert ist, testen Sie, ob der **Release**-DWORD-Wert *gleich* dem in der Tabelle aufgeführten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="78be9-179">Um beispielsweise festzustellen, ob .NET Framework 4.6 auf einem Windows 10-System vorhanden ist, testen Sie, ob der **Release**-Wert *gleich* 393295 ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="78be9-180">Mindestversion</span><span class="sxs-lookup"><span data-stu-id="78be9-180">Minimum version</span></span>

<span data-ttu-id="78be9-181">Um festzustellen, ob eine *Mindestversion* von .NET Framework vorhanden ist, verwenden Sie den kleinsten **RELEASE**-DWORD-Wert für diese Version aus der Tabelle oben.</span><span class="sxs-lookup"><span data-stu-id="78be9-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="78be9-182">(Zur einfacheren Handhabung werden die Mindestwerte in der folgenden Tabelle ebenfalls aufgeführt.)</span><span class="sxs-lookup"><span data-stu-id="78be9-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="78be9-183">Wenn Ihre Anwendung beispielsweise unter .NET Framework 4.8 oder einer höheren Version ausgeführt wird, testen Sie, ob der **RELEASE**-DWORD-Wert *größer oder gleich* 528040 ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="78be9-184">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="78be9-184">.NET Framework version</span></span>|<span data-ttu-id="78be9-185">Minimalwert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="78be9-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="78be9-186">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="78be9-186">.NET Framework 4.5</span></span>|<span data-ttu-id="78be9-187">378389</span><span class="sxs-lookup"><span data-stu-id="78be9-187">378389</span></span>|
|<span data-ttu-id="78be9-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="78be9-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="78be9-189">378675</span><span class="sxs-lookup"><span data-stu-id="78be9-189">378675</span></span>|
|<span data-ttu-id="78be9-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="78be9-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="78be9-191">379893</span><span class="sxs-lookup"><span data-stu-id="78be9-191">379893</span></span>|
|<span data-ttu-id="78be9-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="78be9-192">.NET Framework 4.6</span></span>|<span data-ttu-id="78be9-193">393295</span><span class="sxs-lookup"><span data-stu-id="78be9-193">393295</span></span>|
|<span data-ttu-id="78be9-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="78be9-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="78be9-195">394254</span><span class="sxs-lookup"><span data-stu-id="78be9-195">394254</span></span>|
|<span data-ttu-id="78be9-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="78be9-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="78be9-197">394802</span><span class="sxs-lookup"><span data-stu-id="78be9-197">394802</span></span>|
|<span data-ttu-id="78be9-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="78be9-198">.NET Framework 4.7</span></span>|<span data-ttu-id="78be9-199">460798</span><span class="sxs-lookup"><span data-stu-id="78be9-199">460798</span></span>|
|<span data-ttu-id="78be9-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="78be9-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="78be9-201">461308</span><span class="sxs-lookup"><span data-stu-id="78be9-201">461308</span></span>|
|<span data-ttu-id="78be9-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="78be9-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="78be9-203">461808</span><span class="sxs-lookup"><span data-stu-id="78be9-203">461808</span></span>|
|<span data-ttu-id="78be9-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="78be9-204">.NET Framework 4.8</span></span>|<span data-ttu-id="78be9-205">528040</span><span class="sxs-lookup"><span data-stu-id="78be9-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="78be9-206">Mehrere Versionen</span><span class="sxs-lookup"><span data-stu-id="78be9-206">Multiple versions</span></span>

<span data-ttu-id="78be9-207">Um auf mehrere Versionen zu testen, beginnen Sie mit dem Testen auf einen Wert, der *größer oder gleich* dem kleineren DWORD-Wert für die neueste .NET Framework-Version ist, und vergleichen Sie dann den Wert mit dem kleineren DWORD-Wert für jede nachfolgende frühere Version.</span><span class="sxs-lookup"><span data-stu-id="78be9-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="78be9-208">Wenn Ihre Anwendung beispielsweise .NET Framework 4.7 oder höher erfordert und Sie die spezifische vorhandene Version von .NET Framework bestimmen möchten, starten Sie mit dem Testen auf einen **RELEASE**-DWORD-Wert, der *größer oder gleich* 461808 ist (der kleinere DWORD-Wert für .NET Framework 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="78be9-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="78be9-209">Vergleichen Sie dann den **RELEASE**-DWORD-Wert mit dem kleineren Wert für jede spätere .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="78be9-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="78be9-210">Abfragen der Registrierung mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="78be9-210">Query the registry using code</span></span>

1. <span data-ttu-id="78be9-211">Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>, um auf den Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="78be9-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="78be9-212">Wenn der DWORD-Eintrag **Release** im Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** vorhanden ist, bedeutet dies, dass .NET Framework 4.5 oder eine höhere Version auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="78be9-213">Überprüfen Sie den Wert des Eintrags **Release**, um die installierte Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="78be9-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="78be9-214">Suchen Sie einen Wert größer als oder gleich dem Wert, der in der [.NET Framework-Versionstabelle](#version_table) aufgeführt ist, um die Aufwärtskompatibilität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="78be9-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="78be9-215">Im folgenden Beispiel wird der Wert des Eintrags **Release** in der Registrierung überprüft, um die installierten Versionen von .NET Framework 4.5 und höher zu suchen:</span><span class="sxs-lookup"><span data-stu-id="78be9-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="78be9-216">In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:</span><span class="sxs-lookup"><span data-stu-id="78be9-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="78be9-217">Es wird überprüft, ob der Wert des Eintrags **Release** *größer als der oder gleich dem* Wert der bekannten Releaseschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="78be9-218">Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.</span><span class="sxs-lookup"><span data-stu-id="78be9-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="78be9-219">Verwenden von PowerShell zum Prüfen auf eine mindestens erforderliche Version</span><span class="sxs-lookup"><span data-stu-id="78be9-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="78be9-220">Verwenden Sie PowerShell-Befehle, um den Wert des Eintrags **Release** des Unterschlüssels **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="78be9-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="78be9-221">In den folgenden Beispielen wird der Wert des Eintrags **Release** überprüft, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="78be9-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="78be9-222">Dieser Code gibt `True` zurück, wenn es installiert ist, und andernfalls `False`.</span><span class="sxs-lookup"><span data-stu-id="78be9-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="78be9-223">Um nach einer anderen mindestens erforderlichen .NET Framework-Version zu suchen, ersetzen Sie `394802` im Beispiel durch einen Wert aus der [.NET Framework-Versionstabelle](#version_table).</span><span class="sxs-lookup"><span data-stu-id="78be9-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="78be9-224">Verwenden Sie den kleinsten Wert, der für diese Version angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="78be9-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="78be9-225">Suchen nach älteren .NET Framework-Versionen (1 bis 4)</span><span class="sxs-lookup"><span data-stu-id="78be9-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="78be9-226">Verwenden des Registrierungs-Editors (ältere Frameworkversionen)</span><span class="sxs-lookup"><span data-stu-id="78be9-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="78be9-227">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78be9-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="78be9-228">Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="78be9-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="78be9-229">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="78be9-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="78be9-230">Für die .NET Framework-Versionen 1.1 bis 3.5 ist jede installierte Version als Unterschlüssel unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="78be9-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="78be9-231">Beispiel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="78be9-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="78be9-232">Die Versionsnummer ist als Wert im Eintrag **Version** des Unterschlüssels der Version gespeichert.</span><span class="sxs-lookup"><span data-stu-id="78be9-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="78be9-233">Bei .NET Framework 4 befindet sich der Eintrag **Version** unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** oder unter beiden Unterschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="78be9-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78be9-234">Der Ordner **NET Framework Setup** in der Registrierung beginnt nicht mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="78be9-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="78be9-235">Die folgende Abbildung zeigt den Unterschlüssel und dessen **Version**-Eintrag für .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="78be9-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="78be9-236">![Der Registrierungseintrag für .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 und frühere Versionen")</span><span class="sxs-lookup"><span data-stu-id="78be9-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="78be9-237">Abfragen der Registrierung mithilfe von Code (ältere Frameworkversionen)</span><span class="sxs-lookup"><span data-stu-id="78be9-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="78be9-238">Verwenden Sie die Klasse <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, um in der Windows-Registrierung auf den Unterschlüssel **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="78be9-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="78be9-239">Im folgenden Beispiel werden die installierten .NET Framework-Versionen 1 bis 4 ermittelt:</span><span class="sxs-lookup"><span data-stu-id="78be9-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="78be9-240">Suchen von CLR-Versionen</span><span class="sxs-lookup"><span data-stu-id="78be9-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="78be9-241">Verwenden von „Clrver.exe“</span><span class="sxs-lookup"><span data-stu-id="78be9-241">Use Clrver.exe</span></span>

<span data-ttu-id="78be9-242">Verwenden Sie das [CLR-Versionstool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md), um zu bestimmen, welche Versionen der CLR auf einem Computer installiert sind:</span><span class="sxs-lookup"><span data-stu-id="78be9-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="78be9-243">Geben Sie in einer [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md) `clrver` ein.</span><span class="sxs-lookup"><span data-stu-id="78be9-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="78be9-244">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="78be9-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="78be9-245">Verwenden der Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="78be9-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78be9-246">Für .NET Framework 4.5 und höhere Versionen sollten Sie zum Erkennen der CLR-Version nicht die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="78be9-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="78be9-247">Fragen Sie stattdessen die Registrierung ab wie unter [Suchen von .NET Framework-Versionen 4.5 und höher mit Code](#net_d) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78be9-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="78be9-248">Fragen Sie die Eigenschaft <xref:System.Environment.Version?displayProperty=nameWithType> ab, um ein <xref:System.Version>-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="78be9-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="78be9-249">Das zurückgegebene `System.Version`-Objekt identifiziert die Version der Runtime, die gerade den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="78be9-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="78be9-250">Es gibt keine Assemblyversionen oder andere Versionen der Runtime zurück, die möglicherweise auf dem Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="78be9-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="78be9-251">Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 hat die Zeichenfolgendarstellung des zurückgegebenen <xref:System.Version>-Objekts das Format 4.0.30319.*xxxxx*, wobei *xxxxx*n kleiner ist als 42000.</span><span class="sxs-lookup"><span data-stu-id="78be9-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="78be9-252">Bei .NET Framework 4.6 und höheren Versionen weist sie das Format 4.0.30319.42000 auf.</span><span class="sxs-lookup"><span data-stu-id="78be9-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="78be9-253">Fragen Sie das erhaltene `Version`-Objekt wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="78be9-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="78be9-254">Verwenden Sie für den Hauptversionsbezeichner (zum Beispiel *4* für Version 4.0) die Eigenschaft <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78be9-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="78be9-255">Verwenden Sie für den Nebenversionsbezeichner (zum Beispiel *0* für Version 4.0) die Eigenschaft <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78be9-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="78be9-256">Verwenden Sie für die gesamte Versionszeichenfolge (zum Beispiel *4.0.30319.18010*) die Methode <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="78be9-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="78be9-257">Diese Methode gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="78be9-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="78be9-258">Sie gibt keine Assemblyversionen oder andere Runtimeversionen zurück, die möglicherweise auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="78be9-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="78be9-259">Im folgenden Beispiel wird die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwendet, um CLR-Versionsinformationen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="78be9-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="78be9-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78be9-260">See also</span></span>

- [<span data-ttu-id="78be9-261">Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes</span><span class="sxs-lookup"><span data-stu-id="78be9-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="78be9-262">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="78be9-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="78be9-263">.NET Framework-Versionen und -Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78be9-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
