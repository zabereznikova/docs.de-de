---
title: 'Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen'
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b7c7704c4f417ef16d3a79fa6d955265e42cf14
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262439"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="67eaa-102">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="67eaa-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="67eaa-103">Benutzer können mehrere Versionen von .NET Framework auf einem Computer [installieren](https://docs.microsoft.com/dotnet/framework/install) und ausführen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="67eaa-104">Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="67eaa-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="67eaa-105">.NET Framework besteht aus zwei Hauptkomponenten mit separaten Versionen:</span><span class="sxs-lookup"><span data-stu-id="67eaa-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="67eaa-106">Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="67eaa-107">.NET Framework und Assemblys verwenden die gleiche Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="67eaa-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="67eaa-108">Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="67eaa-109">Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="67eaa-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="67eaa-110">Jede neue Version von .NET Framework enthält weiterhin Funktionen aus den früheren Versionen und fügt neue Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="67eaa-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="67eaa-111">Sie können mehrere Versionen von .NET Framework gleichzeitig auf einen Computer laden. Somit können Sie .NET Framework installieren, ohne vorherige Versionen deinstallieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="67eaa-112">Im Allgemeinen sollten Sie keine vorherigen Versionen von .NET Framework deinstallieren, da eine verwendete Anwendung möglicherweise von einer bestimmten Version abhängt und nicht mehr ausgeführt wird, wenn diese Version entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="67eaa-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="67eaa-113">Zwischen der .NET Framework-Version und der CLR-Version besteht ein Unterschied:</span><span class="sxs-lookup"><span data-stu-id="67eaa-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="67eaa-114">Die .NET Framework-Version basiert auf den Assemblys, die die .NET Framework-Klassenbibliothek bilden.</span><span class="sxs-lookup"><span data-stu-id="67eaa-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="67eaa-115">Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="67eaa-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="67eaa-116">Die CLR-Version basiert auf der Runtime, auf der .NET Framework-Anwendungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="67eaa-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="67eaa-117">Eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="67eaa-118">Die CLR-Version 4.0.30319.*xxxxx* unterstützt zum Beispiel die .NET Framework-Versionen 4 bis 4.5.2, und die CLR-Version 4.0.30319.42000 unterstützt .NET Framework-Versionen ab .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="67eaa-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="67eaa-119">Weitere Informationen zu Versionen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](versions-and-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="67eaa-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="67eaa-120">Eine Liste der auf einem Computer installierten .NET Framework-Versionen finden Sie in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="67eaa-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="67eaa-121">Sie können die Registrierung entweder mit dem Registrierungs-Editor anzeigen oder mit Code abfragen:</span><span class="sxs-lookup"><span data-stu-id="67eaa-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="67eaa-122">Suchen von neueren .NET Framework-Versionen (4.5 und höher):</span><span class="sxs-lookup"><span data-stu-id="67eaa-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="67eaa-123">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="67eaa-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="67eaa-124">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="67eaa-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="67eaa-125">Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt</span><span class="sxs-lookup"><span data-stu-id="67eaa-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
 - <span data-ttu-id="67eaa-126">Suchen von älteren .NET Framework-Versionen (1&#8211;4):</span><span class="sxs-lookup"><span data-stu-id="67eaa-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="67eaa-127">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="67eaa-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="67eaa-128">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="67eaa-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="67eaa-129">Verwenden Sie ein Tool oder Code, um eine Liste der auf einem Computer installierten CLR-Versionen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="67eaa-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
 - [<span data-ttu-id="67eaa-130">Suchen der aktuellen CLR-Version mit „Clrver.exe“</span><span class="sxs-lookup"><span data-stu-id="67eaa-130">Use the Clrver tool</span></span>](#clr_a)  
 - [<span data-ttu-id="67eaa-131">Suchen der aktuellen CLR-Version mit der Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="67eaa-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="67eaa-132">Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="67eaa-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="67eaa-133">Suchen von neueren .NET Framework-Versionen (4.5 und höher)</span><span class="sxs-lookup"><span data-stu-id="67eaa-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="67eaa-134">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="67eaa-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="67eaa-135">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67eaa-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="67eaa-136">Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="67eaa-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="67eaa-137">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="67eaa-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="67eaa-138">Wenn der Unterschlüssel **Full** nicht vorhanden ist, wurde .NET Framework 4.5 oder höher nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="67eaa-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="67eaa-139">Der Ordner **NET Framework Setup** in der Registrierung beginnt nicht mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="67eaa-140">Suchen Sie nach einem DWORD-Eintrag mit dem Namen **Release**.</span><span class="sxs-lookup"><span data-stu-id="67eaa-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="67eaa-141">Wenn dieser vorhanden ist, haben Sie .NET Framework 4.5 oder höhere Versionen installiert.</span><span class="sxs-lookup"><span data-stu-id="67eaa-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="67eaa-142">Der Wert ist ein Releaseschlüssel, der einer bestimmten Version des .NET Framework entspricht.</span><span class="sxs-lookup"><span data-stu-id="67eaa-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="67eaa-143">In der folgenden Abbildung hat der Eintrag **Release** beispielsweise den Wert *378389*, was dem Releaseschlüssel für .NET Framework 4.5 entspricht.</span><span class="sxs-lookup"><span data-stu-id="67eaa-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="67eaa-144">![Registrierungseintrag für .NET Framework 4.5](media/clr-installdir.png "Registrierungseintrag für .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="67eaa-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="67eaa-145">Die folgende Tabelle listet für jede .NET Framework-Version den Mindestwert für den Eintrag **Release** auf.</span><span class="sxs-lookup"><span data-stu-id="67eaa-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="67eaa-146">Sie können diese Werte wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="67eaa-146">You can use these values as follows:</span></span>

- <span data-ttu-id="67eaa-147">Testen Sie, ob der in der Registrierung gefundene DWORD-Wert **Release** *größer als der oder gleich dem* in der Tabelle aufgeführten Wert ist, um zu bestimmen, ob eine mindestens erforderliche .NET Framework-Version vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="67eaa-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="67eaa-148">Wenn Ihre Anwendung z.B. .NET Framework 4.7 oder höher benötigt, testen Sie, ob der Mindestwert des Releaseschlüssels *460798* beträgt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="67eaa-149">Um zu testen, ob mehrere Versionen vorliegen, beginnen Sie mit der neuesten Version von .NET Framework, und testen Sie dann, ob die einzelnen früheren Versionen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="67eaa-150">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="67eaa-150">.NET Framework version</span></span>|<span data-ttu-id="67eaa-151">Wert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="67eaa-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="67eaa-152">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="67eaa-152">.NET Framework 4.5</span></span>|<span data-ttu-id="67eaa-153">378389</span><span class="sxs-lookup"><span data-stu-id="67eaa-153">378389</span></span>|
|<span data-ttu-id="67eaa-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="67eaa-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="67eaa-155">378675</span><span class="sxs-lookup"><span data-stu-id="67eaa-155">378675</span></span>|
|<span data-ttu-id="67eaa-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="67eaa-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="67eaa-157">379893</span><span class="sxs-lookup"><span data-stu-id="67eaa-157">379893</span></span>|
|<span data-ttu-id="67eaa-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="67eaa-158">.NET Framework 4.6</span></span>|<span data-ttu-id="67eaa-159">393295</span><span class="sxs-lookup"><span data-stu-id="67eaa-159">393295</span></span>|
|<span data-ttu-id="67eaa-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="67eaa-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="67eaa-161">394254</span><span class="sxs-lookup"><span data-stu-id="67eaa-161">394254</span></span>|
|<span data-ttu-id="67eaa-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="67eaa-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="67eaa-163">394802</span><span class="sxs-lookup"><span data-stu-id="67eaa-163">394802</span></span>|
|<span data-ttu-id="67eaa-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="67eaa-164">.NET Framework 4.7</span></span>|<span data-ttu-id="67eaa-165">460798</span><span class="sxs-lookup"><span data-stu-id="67eaa-165">460798</span></span>|
|<span data-ttu-id="67eaa-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="67eaa-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="67eaa-167">461308</span><span class="sxs-lookup"><span data-stu-id="67eaa-167">461308</span></span>|
|<span data-ttu-id="67eaa-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="67eaa-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="67eaa-169">461808</span><span class="sxs-lookup"><span data-stu-id="67eaa-169">461808</span></span>|

<span data-ttu-id="67eaa-170">Eine vollständige Tabelle der Releaseschlüssel für das .NET Framework für bestimmte Versionen des Windows-Betriebssystems finden Sie unter [.NET Framework-Releaseschlüssel und Windows-Betriebssystemversionen](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="67eaa-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="67eaa-171">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="67eaa-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="67eaa-172">Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>, um auf den Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="67eaa-173">Wenn der DWORD-Eintrag **Release** im Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** vorhanden ist, bedeutet dies, dass .NET Framework 4.5 oder eine höhere Version auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="67eaa-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="67eaa-174">Überprüfen Sie den Wert des Eintrags **Release**, um die installierte Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="67eaa-175">Suchen Sie einen Wert größer als oder gleich dem Wert, der in der [.NET Framework-Versionstabelle](#version_table) aufgeführt ist, um die Aufwärtskompatibilität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="67eaa-176">Im folgenden Beispiel wird der Wert des Eintrags **Release** in der Registrierung überprüft, um die installierten Versionen von .NET Framework 4.5 und höher zu suchen:</span><span class="sxs-lookup"><span data-stu-id="67eaa-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="67eaa-177">In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:</span><span class="sxs-lookup"><span data-stu-id="67eaa-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="67eaa-178">Es wird überprüft, ob der Wert des Eintrags **Release** *größer als der oder gleich dem* Wert der bekannten Releaseschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="67eaa-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="67eaa-179">Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.</span><span class="sxs-lookup"><span data-stu-id="67eaa-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="67eaa-180">Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt</span><span class="sxs-lookup"><span data-stu-id="67eaa-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="67eaa-181">Verwenden Sie PowerShell-Befehle, um den Wert des Eintrags **Release** des Unterschlüssels **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="67eaa-182">In den folgenden Beispielen wird der Wert des Eintrags **Release** überprüft, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="67eaa-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="67eaa-183">Dieser Code gibt `True` zurück, wenn es installiert ist, und andernfalls `False`.</span><span class="sxs-lookup"><span data-stu-id="67eaa-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
```

<span data-ttu-id="67eaa-184">Ersetzen Sie in diesen Beispielen *394802* durch einen **Release**-Wert aus der [.NET Framework-Versionstabelle](#version_table), um zu überprüfen, ob eine andere mindestens erforderliche .NET Framework-Version vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="67eaa-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="67eaa-185">Suchen von älteren .NET Framework-Versionen (1&#8211;4)</span><span class="sxs-lookup"><span data-stu-id="67eaa-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="67eaa-186">Suchen der .NET Framework-Versionen 1&#8211;4 in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="67eaa-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="67eaa-187">Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67eaa-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="67eaa-188">Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="67eaa-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="67eaa-189">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="67eaa-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="67eaa-190">Für die .NET Framework-Versionen 1.1 bis 3.5 ist jede installierte Version als Unterschlüssel unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="67eaa-191">Beispiel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span><span class="sxs-lookup"><span data-stu-id="67eaa-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="67eaa-192">Die Versionsnummer ist als Wert im Eintrag **Version** des Unterschlüssels der Version gespeichert.</span><span class="sxs-lookup"><span data-stu-id="67eaa-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="67eaa-193">Bei .NET Framework 4 befindet sich der Eintrag **Version** unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** oder unter beiden Unterschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="67eaa-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="67eaa-194">Der Ordner **NET Framework Setup** in der Registrierung beginnt nicht mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="67eaa-195">Die folgende Abbildung zeigt den Unterschlüssel und dessen **Version**-Eintrag für .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="67eaa-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="67eaa-196">![Der Registrierungseintrag für .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 und frühere Versionen")</span><span class="sxs-lookup"><span data-stu-id="67eaa-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="67eaa-197">Suchen der .NET Framework-Versionen 1&#8211;4 mit Code</span><span class="sxs-lookup"><span data-stu-id="67eaa-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="67eaa-198">Verwenden Sie die Klasse <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, um in der Windows-Registrierung auf den Unterschlüssel **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="67eaa-199">Im folgenden Beispiel werden die installierten .NET Framework-Versionen 1&#8211;4 ermittelt:</span><span class="sxs-lookup"><span data-stu-id="67eaa-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="67eaa-200">Suchen von CLR-Versionen</span><span class="sxs-lookup"><span data-stu-id="67eaa-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="67eaa-201">Suchen der aktuellen CLR-Version mit „Clrver.exe“</span><span class="sxs-lookup"><span data-stu-id="67eaa-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="67eaa-202">Verwenden Sie das [CLR-Versionstool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md), um zu bestimmen, welche Versionen der CLR auf einem Computer installiert sind:</span><span class="sxs-lookup"><span data-stu-id="67eaa-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="67eaa-203">Geben Sie in einer [Developer-Eingabeaufforderung für Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) `clrver` ein.</span><span class="sxs-lookup"><span data-stu-id="67eaa-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="67eaa-204">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="67eaa-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="67eaa-205">Suchen der aktuellen CLR-Version mit der Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="67eaa-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67eaa-206">Für .NET Framework 4.5 und höhere Versionen sollten Sie zum Erkennen der CLR-Version nicht die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="67eaa-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="67eaa-207">Fragen Sie stattdessen die Registrierung ab wie unter [Suchen von .NET Framework-Versionen 4.5 und höher mit Code](#net_d) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67eaa-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="67eaa-208">Fragen Sie die Eigenschaft <xref:System.Environment.Version?displayProperty=nameWithType> ab, um ein <xref:System.Version>-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="67eaa-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="67eaa-209">Das zurückgegebene `System.Version`-Objekt identifiziert die Version der Runtime, die gerade den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="67eaa-210">Es gibt keine Assemblyversionen oder andere Versionen der Runtime zurück, die möglicherweise auf dem Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="67eaa-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="67eaa-211">Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 hat die Zeichenfolgendarstellung des zurückgegebenen <xref:System.Version>-Objekts das Format 4.0.30319.*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="67eaa-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="67eaa-212">Bei .NET Framework 4.6 und höheren Versionen weist sie das Format 4.0.30319.42000 auf.</span><span class="sxs-lookup"><span data-stu-id="67eaa-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="67eaa-213">Fragen Sie das erhaltene `Version`-Objekt wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="67eaa-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="67eaa-214">Verwenden Sie für den Hauptversionsbezeichner (zum Beispiel *4* für Version 4.0) die Eigenschaft <xref:System.Version.Major%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67eaa-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="67eaa-215">Verwenden Sie für den Nebenversionsbezeichner (zum Beispiel *0* für Version 4.0) die Eigenschaft <xref:System.Version.Minor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67eaa-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="67eaa-216">Verwenden Sie für die gesamte Versionszeichenfolge (zum Beispiel *4.0.30319.18010*) die Methode <xref:System.Version.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67eaa-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="67eaa-217">Diese Methode gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="67eaa-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="67eaa-218">Sie gibt keine Assemblyversionen oder andere Runtimeversionen zurück, die möglicherweise auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="67eaa-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="67eaa-219">Im folgenden Beispiel wird die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwendet, um CLR-Versionsinformationen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="67eaa-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="67eaa-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67eaa-220">See also</span></span>

- [<span data-ttu-id="67eaa-221">Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes</span><span class="sxs-lookup"><span data-stu-id="67eaa-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="67eaa-222">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="67eaa-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="67eaa-223">.NET Framework-Versionen und -Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="67eaa-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
