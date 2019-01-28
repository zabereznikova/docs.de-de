---
title: 'Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen'
ms.date: 04/10/2018
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
ms.openlocfilehash: 31200b72cb551c91791e2e14332aacab8e7f0519
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672005"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="4273b-102">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="4273b-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="4273b-103">Benutzer können mehrere Versionen von .NET Framework auf einem Computer installieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="4273b-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="4273b-104">Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4273b-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="4273b-105">Beachten Sie, dass .NET Framework aus zwei Hauptkomponenten besteht, deren Versionen separat voneinander sind:</span><span class="sxs-lookup"><span data-stu-id="4273b-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="4273b-106">Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4273b-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="4273b-107">.NET Framework und Assemblys verwenden die gleiche Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="4273b-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="4273b-108">Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt.</span><span class="sxs-lookup"><span data-stu-id="4273b-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="4273b-109">Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="4273b-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="4273b-110">Sie können die Registrierung öffnen oder in Ihrem Code abfragen, um eine exakte Liste der auf einem Computer installierten Versionen von .NET Framework zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="4273b-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="4273b-111">Anzeigen der Registrierung (Versionen 1-4)</span><span class="sxs-lookup"><span data-stu-id="4273b-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="4273b-112">Anzeigen der Registrierung ( Version 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="4273b-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="4273b-113">Codegesteuertes Anzeigen der Registrierung (Versionen 1-4)</span><span class="sxs-lookup"><span data-stu-id="4273b-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="4273b-114">Codegesteuertes Anzeigen der Registrierung (Version 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="4273b-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="4273b-115">Anzeigen der Registrierung mithilfe von PowerShell (Version 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="4273b-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="4273b-116">Sie können ein Tool oder Code verwenden, um die CLR-Version zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="4273b-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="4273b-117">Verwenden des Clrver-Tools</span><span class="sxs-lookup"><span data-stu-id="4273b-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="4273b-118">Codegesteuertes Abfragen der System.Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="4273b-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="4273b-119">Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Bestimmen der installierten .NET Framework-Updates](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="4273b-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="4273b-120">Informationen zum Installieren von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="4273b-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="4273b-121">Ermitteln der .NET Framework-Versionen durch Anzeigen der Registrierung (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="4273b-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="4273b-122">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4273b-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="4273b-123">Im Feld **Öffnen** geben Sie **regedit.exe** ein.</span><span class="sxs-lookup"><span data-stu-id="4273b-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="4273b-124">Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4273b-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="4273b-125">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="4273b-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="4273b-126">Die installierten Versionen werden unter dem NDP-Unterschlüssel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4273b-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="4273b-127">Die Versionsnummer ist unter dem Eintrag **Version** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4273b-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="4273b-128">In der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]-Version oder höher befindet sich der Eintrag **Version** unter dem Client- oder Full-Unterschlüssel (unter NDP) oder unter beiden Unterschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="4273b-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="4273b-129">Der Ordner "NET Framework Setup" in der Registrierung beginnt nicht mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="4273b-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="4273b-130">Ermitteln der .NET Framework-Versionen durch Anzeigen der Registrierung (.NET Framework 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="4273b-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="4273b-131">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4273b-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="4273b-132">Im Feld **Öffnen** geben Sie **regedit.exe** ein.</span><span class="sxs-lookup"><span data-stu-id="4273b-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="4273b-133">Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4273b-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="4273b-134">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="4273b-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="4273b-135">Beachten Sie, dass der Pfad zum `Full`-Unterschlüssel den Unterschlüssel `Net Framework` anstelle von `.NET Framework` enthält.</span><span class="sxs-lookup"><span data-stu-id="4273b-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4273b-136">Wenn der `Full`-Unterschlüssel nicht vorhanden ist, ist .NET Framework 4.5 oder höher nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="4273b-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="4273b-137">Suchen Sie nach einem DWORD-Wert mit dem Namen `Release`.</span><span class="sxs-lookup"><span data-stu-id="4273b-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="4273b-138">Wenn das `Release`-DWORD vorhanden ist, können Sie von der Installation von [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder höher auf dem Computer ausgehen.</span><span class="sxs-lookup"><span data-stu-id="4273b-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="4273b-139">![Registrierungseintrag für .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="4273b-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="4273b-140">Der Wert von `Release` gibt an, welche Version von .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4273b-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="4273b-141">Wert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="4273b-141">Value of the Release DWORD</span></span>|<span data-ttu-id="4273b-142">Version</span><span class="sxs-lookup"><span data-stu-id="4273b-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="4273b-143">378389</span><span class="sxs-lookup"><span data-stu-id="4273b-143">378389</span></span>|<span data-ttu-id="4273b-144">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4273b-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="4273b-145">378675</span><span class="sxs-lookup"><span data-stu-id="4273b-145">378675</span></span>|<span data-ttu-id="4273b-146">.NET Framework 4.5.1 installiert mit Windows 8.1 oder Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4273b-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="4273b-147">378758</span><span class="sxs-lookup"><span data-stu-id="4273b-147">378758</span></span>|<span data-ttu-id="4273b-148">.NET Framework 4.5.1 installiert unter Windows 8, Windows 7 SP1 oder Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="4273b-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="4273b-149">379893</span><span class="sxs-lookup"><span data-stu-id="4273b-149">379893</span></span>|<span data-ttu-id="4273b-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="4273b-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="4273b-151">Auf Windows 10-Systemen ausschließlich: 393295</span><span class="sxs-lookup"><span data-stu-id="4273b-151">On Windows 10 systems only: 393295</span></span><br /><br /> <span data-ttu-id="4273b-152">Auf allen anderen Betriebssystemversionen: 393297</span><span class="sxs-lookup"><span data-stu-id="4273b-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="4273b-153">Auf Systemen mit dem Windows 10-Update für November ausschließlich: 394254</span><span class="sxs-lookup"><span data-stu-id="4273b-153">On Windows 10 November Update systems only: 394254</span></span><br /><br /> <span data-ttu-id="4273b-154">Auf allen anderen Betriebssystemversionen: 394271</span><span class="sxs-lookup"><span data-stu-id="4273b-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="4273b-155">Auf Systemen unter Windows 10 Anniversary Update und Windows Server 2016: 394802</span><span class="sxs-lookup"><span data-stu-id="4273b-155">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><br /> <span data-ttu-id="4273b-156">Auf allen anderen Betriebssystemversionen: 394806</span><span class="sxs-lookup"><span data-stu-id="4273b-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="4273b-157">Auf Windows 10-Systemen mit Creators Update ausschließlich: 460798</span><span class="sxs-lookup"><span data-stu-id="4273b-157">On Windows 10 Creators Update only: 460798</span></span><br/><br/> <span data-ttu-id="4273b-158">Auf allen anderen Betriebssystemversionen: 460805</span><span class="sxs-lookup"><span data-stu-id="4273b-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="4273b-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="4273b-159">.NET Framework 4.7</span></span> |
    |<span data-ttu-id="4273b-160">Auf Windows 10-Systemen mit Fall Creators Update ausschließlich: 461308</span><span class="sxs-lookup"><span data-stu-id="4273b-160">On Windows 10 Fall Creators Update only: 461308</span></span><br/><br/> <span data-ttu-id="4273b-161">Auf allen anderen Betriebssystemversionen: 461310</span><span class="sxs-lookup"><span data-stu-id="4273b-161">On all other OS versions: 461310</span></span> | <span data-ttu-id="4273b-162">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="4273b-162">.NET Framework 4.7.1</span></span> |
    |<span data-ttu-id="4273b-163">Auf Windows-Systemen mit dem Update von 10. April 2018 ausschließlich: 461808</span><span class="sxs-lookup"><span data-stu-id="4273b-163">On Windows 10 April 2018 Update only: 461808</span></span><br/><br/> <span data-ttu-id="4273b-164">Auf allen anderen Betriebssystemversionen, einschließlich Windows 10 mit dem Oktober-Update 2018: 461814</span><span class="sxs-lookup"><span data-stu-id="4273b-164">On all other OS versions, including Windows 10 October 2018 Update: 461814</span></span>| <span data-ttu-id="4273b-165">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="4273b-165">.NET Framework 4.7.2</span></span> |
    
<a name="net_c"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="4273b-166">Ermitteln der .NET Framework-Versionen durch codegesteuertes Abfragen der Registrierung (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="4273b-166">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="4273b-167">Verwenden Sie die <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>-Klasse, um auf den Unterschlüssel "Software\Microsoft\NET Framework Setup\NDP\" unter "HKEY_LOCAL_MACHINE" in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4273b-167">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="4273b-168">Der folgende Code veranschaulicht diese Abfrage beispielhaft.</span><span class="sxs-lookup"><span data-stu-id="4273b-168">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4273b-169">In diesem Code wird nicht veranschaulicht, wie [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder später zu erkennen ist.</span><span class="sxs-lookup"><span data-stu-id="4273b-169">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="4273b-170">Zum Erkennen dieser Versionen überprüfen Sie das `Release`-DWORD, wie im vorherigen Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4273b-170">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="4273b-171">Informationen zu Code, der [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder höhere Versionen nicht erkennt, finden Sie im nächsten Abschnitt dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="4273b-171">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     <span data-ttu-id="4273b-172">Das Beispiel führt zu einer Ausgabe, die der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="4273b-172">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="4273b-173">Ermitteln der .NET Framework-Versionen durch codegesteuertes Abfragen der Registrierung (.NET Framework 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="4273b-173">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="4273b-174">Wenn das `Release`-DWORD vorhanden ist, können Sie davon ausgehen, dass .NET Framework 4.5 oder neuer auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4273b-174">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="4273b-175">Der Wert des Schlüsselworts gibt die installierte Version an.</span><span class="sxs-lookup"><span data-stu-id="4273b-175">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="4273b-176">Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> der <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>-Klasse, um auf den Unterschlüssel „Software\Microsoft\NET Framework Setup\NDP\v4\Full“ unter „HKEY_LOCAL_MACHINE“ in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4273b-176">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="4273b-177">Überprüfen Sie den Wert des `Release`-Schlüsselworts, um die installierte Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4273b-177">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="4273b-178">Um aufwärtskompatibel zu sein, können Sie einen Wert größer als oder gleich den Werten suchen, die in der Tabelle aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="4273b-178">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="4273b-179">Dies sind die .NET Framework-Versionen und die jeweiligen `Release`-Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="4273b-179">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="4273b-180">Version</span><span class="sxs-lookup"><span data-stu-id="4273b-180">Version</span></span>|<span data-ttu-id="4273b-181">Wert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="4273b-181">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="4273b-182">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4273b-182">.NET Framework 4.5</span></span>|<span data-ttu-id="4273b-183">378389</span><span class="sxs-lookup"><span data-stu-id="4273b-183">378389</span></span>|
    |<span data-ttu-id="4273b-184">.NET Framework 4.5.1 installiert mit Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4273b-184">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="4273b-185">378675</span><span class="sxs-lookup"><span data-stu-id="4273b-185">378675</span></span>|
    |<span data-ttu-id="4273b-186">.NET Framework 4.5.1 installiert unter Windows 8, Windows 7 SP1 oder Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="4273b-186">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="4273b-187">378758</span><span class="sxs-lookup"><span data-stu-id="4273b-187">378758</span></span>|
    |<span data-ttu-id="4273b-188">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="4273b-188">.NET Framework 4.5.2</span></span>|<span data-ttu-id="4273b-189">379893</span><span class="sxs-lookup"><span data-stu-id="4273b-189">379893</span></span>|
    |<span data-ttu-id="4273b-190">.NET Framework 4.6, installiert unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="4273b-190">.NET Framework 4.6 installed with Windows 10</span></span>|<span data-ttu-id="4273b-191">393295</span><span class="sxs-lookup"><span data-stu-id="4273b-191">393295</span></span>|
    |<span data-ttu-id="4273b-192">.NET Framework 4.6, installiert auf allen anderen Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-192">.NET Framework 4.6 installed on all other Windows OS versions</span></span>|<span data-ttu-id="4273b-193">393297</span><span class="sxs-lookup"><span data-stu-id="4273b-193">393297</span></span>|
    |<span data-ttu-id="4273b-194">.NET Framework 4.6.1, installiert unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="4273b-194">.NET Framework 4.6.1 installed on Windows 10</span></span>|<span data-ttu-id="4273b-195">394254</span><span class="sxs-lookup"><span data-stu-id="4273b-195">394254</span></span>|
    |<span data-ttu-id="4273b-196">.NET Framework 4.6.1, installiert auf allen anderen Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-196">.NET Framework 4.6.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="4273b-197">394271</span><span class="sxs-lookup"><span data-stu-id="4273b-197">394271</span></span>|
    |<span data-ttu-id="4273b-198">.NET Framework 4.6.2, installiert unter Windows 10 Anniversary Update und Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4273b-198">.NET Framework 4.6.2 installed on Windows 10 Anniversary Update and Windows Server 2016</span></span>|<span data-ttu-id="4273b-199">394802</span><span class="sxs-lookup"><span data-stu-id="4273b-199">394802</span></span>|
    |<span data-ttu-id="4273b-200">.NET Framework 4.6.2, installiert auf allen anderen Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-200">.NET Framework 4.6.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="4273b-201">394806</span><span class="sxs-lookup"><span data-stu-id="4273b-201">394806</span></span>|
    |<span data-ttu-id="4273b-202">.NET Framework 4.7 installiert unter Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="4273b-202">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="4273b-203">460798</span><span class="sxs-lookup"><span data-stu-id="4273b-203">460798</span></span>|
    |<span data-ttu-id="4273b-204">.NET Framework 4.7 installiert auf allen anderen Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-204">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="4273b-205">460805</span><span class="sxs-lookup"><span data-stu-id="4273b-205">460805</span></span>|
    |<span data-ttu-id="4273b-206">.NET Framework 4.7.1 installiert unter Windows 10 Creators Update</span><span class="sxs-lookup"><span data-stu-id="4273b-206">.NET Framework 4.7.1 installed on Windows 10 Fall Creators Update</span></span>|<span data-ttu-id="4273b-207">461308</span><span class="sxs-lookup"><span data-stu-id="4273b-207">461308</span></span>|
    |<span data-ttu-id="4273b-208">.NET Framework 4.7.1, installiert auf allen anderen Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-208">.NET Framework 4.7.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="4273b-209">461310</span><span class="sxs-lookup"><span data-stu-id="4273b-209">461310</span></span>|
    |<span data-ttu-id="4273b-210">.NET Framework 4.7.2, installiert unter dem Windows 10-Update von April 2018</span><span class="sxs-lookup"><span data-stu-id="4273b-210">.NET Framework 4.7.2 installed on Windows 10 October 2018 Update</span></span>|<span data-ttu-id="4273b-211">461814</span><span class="sxs-lookup"><span data-stu-id="4273b-211">461814</span></span>|
    |<span data-ttu-id="4273b-212">.NET Framework 4.7.2, installiert unter dem Windows 10-Update für April 2018</span><span class="sxs-lookup"><span data-stu-id="4273b-212">.NET Framework 4.7.2 installed on Windows 10 April 2018 Update</span></span>|<span data-ttu-id="4273b-213">461808</span><span class="sxs-lookup"><span data-stu-id="4273b-213">461808</span></span>|
    |<span data-ttu-id="4273b-214">.NET Framework 4.7.2, installiert unter dem Windows 10 Fall Creators Update und früheren Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="4273b-214">.NET Framework 4.7.2 installed on Windows 10 Fall Creators Update and earlier OS versions</span></span>|<span data-ttu-id="4273b-215">461814</span><span class="sxs-lookup"><span data-stu-id="4273b-215">461814</span></span>|
    
     <span data-ttu-id="4273b-216">Das folgende Beispiel überprüft den `Release`-Wert in der Registrierung, um zu ermitteln, ob [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder eine höhere Version von .NET Framework installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4273b-216">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     <span data-ttu-id="4273b-217">In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:</span><span class="sxs-lookup"><span data-stu-id="4273b-217">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="4273b-218">Es überprüft, ob der Wert des `Release`-Eintrags *größer als oder gleich* dem Wert der bekannten Versionsschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="4273b-218">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="4273b-219">Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.</span><span class="sxs-lookup"><span data-stu-id="4273b-219">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="4273b-220">Überprüfen der mindestens erforderlichen Version von .NET Framework durch Abfragen der Registrierung in PowerShell (.NET Framework 4.5 und höher)</span><span class="sxs-lookup"><span data-stu-id="4273b-220">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="4273b-221">Das folgende Beispiel überprüft den Wert des Schlüsselworts `Release`, um unabhängig vom Windows-Betriebssystem zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist (es wird `True` zurückgegeben, falls es installiert ist, andernfalls `False`).</span><span class="sxs-lookup"><span data-stu-id="4273b-221">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    <span data-ttu-id="4273b-222">Sie können `394802` im vorherigen Beispiel durch einen anderen Wert aus der folgenden Tabelle ersetzen, um eine Überprüfung auf eine unterschiedliche mindestens erforderliche Version von .NET Framework durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4273b-222">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="4273b-223">Version</span><span class="sxs-lookup"><span data-stu-id="4273b-223">Version</span></span>|<span data-ttu-id="4273b-224">Minimalwert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="4273b-224">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="4273b-225">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4273b-225">.NET Framework 4.5</span></span>|<span data-ttu-id="4273b-226">378389</span><span class="sxs-lookup"><span data-stu-id="4273b-226">378389</span></span>|
    |<span data-ttu-id="4273b-227">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="4273b-227">.NET Framework 4.5.1</span></span>|<span data-ttu-id="4273b-228">378675</span><span class="sxs-lookup"><span data-stu-id="4273b-228">378675</span></span>|
    |<span data-ttu-id="4273b-229">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="4273b-229">.NET Framework 4.5.2</span></span>|<span data-ttu-id="4273b-230">379893</span><span class="sxs-lookup"><span data-stu-id="4273b-230">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="4273b-231">393295</span><span class="sxs-lookup"><span data-stu-id="4273b-231">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="4273b-232">394254</span><span class="sxs-lookup"><span data-stu-id="4273b-232">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="4273b-233">394802</span><span class="sxs-lookup"><span data-stu-id="4273b-233">394802</span></span>|
    |<span data-ttu-id="4273b-234">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="4273b-234">.NET Framework 4.7</span></span>|<span data-ttu-id="4273b-235">460798</span><span class="sxs-lookup"><span data-stu-id="4273b-235">460798</span></span>|
    |<span data-ttu-id="4273b-236">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="4273b-236">.NET Framework 4.7.1</span></span>|<span data-ttu-id="4273b-237">461308</span><span class="sxs-lookup"><span data-stu-id="4273b-237">461308</span></span>|
    |<span data-ttu-id="4273b-238">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="4273b-238">.NET Framework 4.7.2</span></span>|<span data-ttu-id="4273b-239">461808</span><span class="sxs-lookup"><span data-stu-id="4273b-239">461808</span></span>|

<a name="clr_a"></a> 
## <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="4273b-240">Ermitteln der aktuellen Laufzeitversion mithilfe des Clrver-Tools</span><span class="sxs-lookup"><span data-stu-id="4273b-240">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="4273b-241">Verwenden Sie das CLR-Versions-Tool (Clrver.exe), um zu bestimmen, welche Versionen der Common Language Runtime auf einem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4273b-241">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="4273b-242">Geben Sie in einer Developer-Eingabeaufforderung für Visual Studio `clrver` ein.</span><span class="sxs-lookup"><span data-stu-id="4273b-242">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="4273b-243">Dieser Befehl erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4273b-243">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="4273b-244">Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Clrver.exe (CLR-Versionstool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="4273b-244">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="4273b-245">Ermitteln der aktuellen Laufzeitversion durch programmgesteuerte Abfragen der "Environment"-Klasse</span><span class="sxs-lookup"><span data-stu-id="4273b-245">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="4273b-246">Fragen Sie die <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft ab, um ein <xref:System.Version>-Objekt abzurufen, das die Version der Laufzeit identifiziert, die gerade den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="4273b-246">Query the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="4273b-247">Sie können die <xref:System.Version.Major%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um den Hauptversionsbezeichner (beispielsweise "4 " für Version 4.0) abzurufen, die <xref:System.Version.Minor%2A?displayProperty=nameWithType>-Eigenschaft, um den Nebenversionsbezeichner abzurufen (beispielsweise "0 " für Version 4.0) oder die <xref:System.Object.ToString%2A?displayProperty=nameWithType>-Methode aufrufen, um die gesamte Versionszeichenfolge (beispielsweise "4.0.30319.18010") abzurufen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4273b-247">You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="4273b-248">Diese Eigenschaft gibt einen einzelnen Wert zurück, der die Version der Laufzeit angibt, die gerade den Code ausführt; sie gibt keine Assemblyversionen oder andere Versionen der Laufzeit zurück, die möglicherweise auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4273b-248">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="4273b-249">Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 gibt die <xref:System.Environment.Version%2A?displayProperty=nameWithType>Eigenschaft ein <xref:System.Version>-Objekt zurück, dessen Zeichenfolgedarstellung die Form `4.0.30319.xxxxx`besitzt.</span><span class="sxs-lookup"><span data-stu-id="4273b-249">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="4273b-250">Für .NET Framework 4.6 und höher weist sie die Form `4.0.30319.42000` auf.</span><span class="sxs-lookup"><span data-stu-id="4273b-250">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4273b-251">Für [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] und höher wird das Verwenden der Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> zum Erkennen der Laufzeitversion nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4273b-251">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="4273b-252">Stattdessen empfehlen wir, dass Sie die Registrierung abfragen, wie im Abschnitt [Ermitteln der .NET Framework-Versionen durch codegesteuertes Abfragen der Registrierung (.NET Framework 4.5 und neuer)](#net_d) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4273b-252">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="4273b-253">Der folgende Code zeigt ein Beispiel für die Abfrage der <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft auf Laufzeitversionsinformationen:</span><span class="sxs-lookup"><span data-stu-id="4273b-253">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property for runtime version information:</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     <span data-ttu-id="4273b-254">Das Beispiel führt zu einer Ausgabe, die der folgenden Ausgabe ähnelt:</span><span class="sxs-lookup"><span data-stu-id="4273b-254">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="4273b-255">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4273b-255">See also</span></span>

- [<span data-ttu-id="4273b-256">Vorgehensweise: Bestimmen der installierten .NET Framework-Updates</span><span class="sxs-lookup"><span data-stu-id="4273b-256">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="4273b-257">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="4273b-257">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="4273b-258">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="4273b-258">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)
