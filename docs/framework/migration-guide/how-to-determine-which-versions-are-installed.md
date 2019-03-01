---
title: 'Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen'
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584173"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="ecca3-102">Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="ecca3-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="ecca3-103">Benutzer können mehrere Versionen von .NET Framework auf einem Computer installieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="ecca3-104">Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ecca3-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="ecca3-105">Beachten Sie, dass .NET Framework aus zwei Hauptkomponenten besteht, deren Versionen separat voneinander sind:</span><span class="sxs-lookup"><span data-stu-id="ecca3-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="ecca3-106">Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="ecca3-107">.NET Framework und Assemblys verwenden die gleiche Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="ecca3-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="ecca3-108">Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt.</span><span class="sxs-lookup"><span data-stu-id="ecca3-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="ecca3-109">Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span><span class="sxs-lookup"><span data-stu-id="ecca3-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
<span data-ttu-id="ecca3-110">Sie können die Registrierung öffnen oder in Ihrem Code abfragen, um eine exakte Liste der auf einem Computer installierten Versionen von .NET Framework zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="ecca3-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="ecca3-111">Suchen von .NET Framework-Versionen 1 bis 4 in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ecca3-111">Find .NET Framework versions 1-4 in the registry</span></span>](#net_a)  
 [<span data-ttu-id="ecca3-112">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ecca3-112">Find .NET Framework versions 4.5 and later in the registry)</span></span>](#net_b)  
 [<span data-ttu-id="ecca3-113">Codegesteuertes Anzeigen der Registrierung (Versionen 1-4)</span><span class="sxs-lookup"><span data-stu-id="ecca3-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="ecca3-114">Codegesteuertes Anzeigen der Registrierung (Version 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="ecca3-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="ecca3-115">Anzeigen der Registrierung mithilfe von PowerShell (Version 4.5 und neuer)</span><span class="sxs-lookup"><span data-stu-id="ecca3-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  

 <span data-ttu-id="ecca3-116">Sie können ein Tool oder Code verwenden, um die CLR-Version zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="ecca3-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="ecca3-117">Verwenden des Clrver-Tools</span><span class="sxs-lookup"><span data-stu-id="ecca3-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="ecca3-118">Codegesteuertes Abfragen der System.Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="ecca3-118">Using code to query the System.Environment class</span></span>](#clr_b)  

> [!NOTE]
> <span data-ttu-id="ecca3-119">Zwischen der .NET Framework-Version und der Common Language Runtime-Version (CLR) besteht ein Unterschied.</span><span class="sxs-lookup"><span data-stu-id="ecca3-119">There is a difference between the .NET Framework version and the common language runtime (CLR) version.</span></span> <span data-ttu-id="ecca3-120">Die .NET Framework-Version basiert auf dem Satz von Assemblys, die die .NET Framework-Klassenbibliothek bilden.</span><span class="sxs-lookup"><span data-stu-id="ecca3-120">The .NET Framework is versioned based on the set of assemblies that form the .NET Framework Class Library.</span></span> <span data-ttu-id="ecca3-121">Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="ecca3-121">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> <span data-ttu-id="ecca3-122">Die CLR-Version basiert auf der Runtime, mit der .NET Framework-Anwendungen ausgeführt werden, und eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-122">The CLR is versioned based on the runtime on which .NET Framework applications execute, and a single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="ecca3-123">CLR-Version 4.30319. *xxxxx* unterstützt die .NET Framework-Versionen 4 bis 4.5.2; CLR-Version 4.30319.42000 unterstützt .NET Framework-Versionen ab .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="ecca3-123">CLR version 4.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2; CLR version 4.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> <span data-ttu-id="ecca3-124">Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Environment.Version?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ecca3-124">For more information, see the <xref:System.Environment.Version?displayProperty=nameWithType> property.</span></span>

 <span data-ttu-id="ecca3-125">Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Bestimmen der installierten .NET Framework-Updates](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="ecca3-125">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="ecca3-126">Informationen zum Installieren von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="ecca3-126">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a><span data-ttu-id="ecca3-127">Suchen von .NET Framework-Versionen 1 bis 4 in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ecca3-127">Find .NET Framework versions 1-4 in the registry</span></span> 
  
1.  <span data-ttu-id="ecca3-128">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ecca3-128">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="ecca3-129">Im Feld **Öffnen** geben Sie **regedit.exe** ein.</span><span class="sxs-lookup"><span data-stu-id="ecca3-129">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="ecca3-130">Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ecca3-130">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="ecca3-131">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="ecca3-131">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="ecca3-132">Für die .NET Framework-Versionen 1.1 bis 3.5 sind die installierten Versionen als Unterschlüssel unter dem `NDP`-Unterschlüssel aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ecca3-132">For .NET Framework versions 1.1 through 3.5, the installed versions are listed as subkeys under the `NDP` subkey.</span></span> <span data-ttu-id="ecca3-133">Die Versionsnummer ist unter dem Eintrag **Version** des Unterschlüssels der Version gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ecca3-133">The version number is stored in the version subkey's **Version** entry.</span></span> 
     
     <span data-ttu-id="ecca3-134">Für .NET Framework 4 befindet sich der Eintrag **Version** unter dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`-Unterschlüssel, dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full`-Unterschlüssel oder unter beiden Unterschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ecca3-134">For .NET Framework 4, the **Version** entry is under the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` subkey, the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ecca3-135">Der Ordner "NET Framework Setup" in der Registrierung beginnt nicht mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="ecca3-135">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="ecca3-136">Die folgende Abbildung zeigt den Unterschlüssel für .NET Framework 3.5 zusammen mit seinem **Version**-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="ecca3-136">The following figure shows that the subkey for the .NET Framework 3.5 along with its **Version** entry.</span></span>

     <span data-ttu-id="ecca3-137">![Der Registrierungseintrag für .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 und frühere Versionen")</span><span class="sxs-lookup"><span data-stu-id="ecca3-137">![The registry entry for the .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 and earlier versions")</span></span>

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="ecca3-138">Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ecca3-138">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="ecca3-139">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ecca3-139">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="ecca3-140">Im Feld **Öffnen** geben Sie **regedit.exe** ein.</span><span class="sxs-lookup"><span data-stu-id="ecca3-140">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="ecca3-141">Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ecca3-141">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="ecca3-142">Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:</span><span class="sxs-lookup"><span data-stu-id="ecca3-142">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="ecca3-143">Beachten Sie, dass der Pfad zum `Full`-Unterschlüssel den Unterschlüssel `Net Framework` anstelle von `.NET Framework` enthält.</span><span class="sxs-lookup"><span data-stu-id="ecca3-143">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ecca3-144">Wenn der `Full`-Unterschlüssel nicht vorhanden ist, ist .NET Framework 4.5 oder höher nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="ecca3-144">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="ecca3-145">Suchen Sie nach einem DWORD-Wert mit dem Namen `Release`.</span><span class="sxs-lookup"><span data-stu-id="ecca3-145">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="ecca3-146">Wenn das `Release`-DWORD vorhanden ist, können Sie davon ausgehen, dass .NET Framework 4.5 oder höher auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-146">The existence of the `Release` DWORD indicates that .NET Framework 4.5 or later has been installed on that computer.</span></span> <span data-ttu-id="ecca3-147">Der Wert ist ein Releaseschlüssel, der einer bestimmten Version von .NET Framework entspricht.</span><span class="sxs-lookup"><span data-stu-id="ecca3-147">Its value is a release key that corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="ecca3-148">In der folgenden Abbildung hat das `Release`-DWORD beispielsweise den Wert 378.389, was dem Releaseschlüssel für .NET Framework 4.5 entspricht.</span><span class="sxs-lookup"><span data-stu-id="ecca3-148">In the following figure, for example, the value of the `Release` DWORD is 378389, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="ecca3-149">![Registrierungseintrag für .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="ecca3-149">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

<span data-ttu-id="ecca3-150">Die folgende Tabelle listet für jede .NET Framework-Version den Mindestwert für das `Release`-DWORD auf.</span><span class="sxs-lookup"><span data-stu-id="ecca3-150">The following table lists the minimum value of the `Release` DWORD for each .NET Framework version.</span></span> <span data-ttu-id="ecca3-151">Sie können diese Werte wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="ecca3-151">You can use these values as follows:</span></span>

- <span data-ttu-id="ecca3-152">Um zu bestimmen, ob eine Mindestversion von .NET Framework vorhanden ist, testen Sie, ob der in der Registrierung gefundene `Release`-DWORD-Wert *größer als der oder gleich dem* in der Tabelle aufgeführten Wert ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-152">To determine whether a minimum .NET Framework version is present, test whether the `Release` DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="ecca3-153">Wenn Ihre Anwendung z.B. .NET Framework 4.7 oder höher benötigt, würden Sie testen, ob der Mindestwert des Releaseschlüssels 460.798 beträgt.</span><span class="sxs-lookup"><span data-stu-id="ecca3-153">For example, if your application requires .NET Framework 4.7 or later, you would test for a minimum release key value of 460798.</span></span>

- <span data-ttu-id="ecca3-154">Um zu testen, ob mehrere Versionen vorliegen, beginnen Sie mit der neuesten Version von .NET Framework, und testen Sie dann, ob die einzelnen früheren Versionen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-154">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|<span data-ttu-id="ecca3-155">.NET Framework-Version</span><span class="sxs-lookup"><span data-stu-id="ecca3-155">.NET Framework Version</span></span>|<span data-ttu-id="ecca3-156">Wert des Versions-DWORD</span><span class="sxs-lookup"><span data-stu-id="ecca3-156">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="ecca3-157">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ecca3-157">.NET Framework 4.5</span></span>|<span data-ttu-id="ecca3-158">378389</span><span class="sxs-lookup"><span data-stu-id="ecca3-158">378389</span></span>|
|<span data-ttu-id="ecca3-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="ecca3-159">.NET Framework 4.5.1</span></span>|<span data-ttu-id="ecca3-160">378675</span><span class="sxs-lookup"><span data-stu-id="ecca3-160">378675</span></span>|
|<span data-ttu-id="ecca3-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="ecca3-161">.NET Framework 4.5.2</span></span>|<span data-ttu-id="ecca3-162">379893</span><span class="sxs-lookup"><span data-stu-id="ecca3-162">379893</span></span>|
|<span data-ttu-id="ecca3-163">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="ecca3-163">.NET Framework 4.6</span></span>|<span data-ttu-id="ecca3-164">393295</span><span class="sxs-lookup"><span data-stu-id="ecca3-164">393295</span></span>|
|<span data-ttu-id="ecca3-165">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="ecca3-165">.NET Framework 4.6.1</span></span>|<span data-ttu-id="ecca3-166">394254</span><span class="sxs-lookup"><span data-stu-id="ecca3-166">394254</span></span>|
|<span data-ttu-id="ecca3-167">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ecca3-167">.NET Framework 4.6.2</span></span>|<span data-ttu-id="ecca3-168">394802</span><span class="sxs-lookup"><span data-stu-id="ecca3-168">394802</span></span>|
|<span data-ttu-id="ecca3-169">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="ecca3-169">.NET Framework 4.7</span></span>|<span data-ttu-id="ecca3-170">460798</span><span class="sxs-lookup"><span data-stu-id="ecca3-170">460798</span></span>|
|<span data-ttu-id="ecca3-171">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="ecca3-171">.NET Framework 4.7.1</span></span>|<span data-ttu-id="ecca3-172">461308</span><span class="sxs-lookup"><span data-stu-id="ecca3-172">461308</span></span>|
|<span data-ttu-id="ecca3-173">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="ecca3-173">.NET Framework 4.7.2</span></span>|<span data-ttu-id="ecca3-174">461808</span><span class="sxs-lookup"><span data-stu-id="ecca3-174">461808</span></span>|

<span data-ttu-id="ecca3-175">Eine vollständige Tabelle der Releaseschlüssel für das .NET Framework für bestimmte Versionen des Windows-Betriebssystems finden Sie unter [.NET Framework-Releaseschlüssel und Windows-Betriebssystemversionen](release-keys-and-os-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ecca3-175">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a><span data-ttu-id="ecca3-176">Suchen der .NET Framework-Versionen 1 bis 4 mit Code</span><span class="sxs-lookup"><span data-stu-id="ecca3-176">Find .NET Framework versions 1-4 with code</span></span>

- <span data-ttu-id="ecca3-177">Verwenden Sie die <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>-Klasse für den Zugriff auf den `Software\Microsoft\NET Framework Setup\NDP\`-Unterschlüssel unter dem `HKEY_LOCAL_MACHINE`-Zweig in der Windows-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="ecca3-177">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the `Software\Microsoft\NET Framework Setup\NDP\` subkey under `HKEY_LOCAL_MACHINE` branch in the Windows registry.</span></span>

     <span data-ttu-id="ecca3-178">Der folgende Code veranschaulicht diese Abfrage beispielhaft.</span><span class="sxs-lookup"><span data-stu-id="ecca3-178">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ecca3-179">In diesem Code wird nicht veranschaulicht, wie .NET Framework 4.5 oder höher zu erkennen ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-179">This code does not show how to detect .NET Framework 4.5 or later.</span></span> <span data-ttu-id="ecca3-180">Zum Erkennen dieser Versionen überprüfen Sie das `Release`-DWORD, wie im vorherigen Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecca3-180">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="ecca3-181">Informationen zu Code, der .NET Framework 4.5 oder höhere Versionen erkennt, finden Sie im nächsten Abschnitt dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="ecca3-181">For code that detects .NET Framework 4.5 or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="ecca3-182">Suchen von .NET Framework-Versionen 4.5 und höher mit Code</span><span class="sxs-lookup"><span data-stu-id="ecca3-182">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="ecca3-183">Wenn das `Release`-DWORD im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`-Schlüssel vorhanden ist, können Sie davon ausgehen, dass .NET Framework 4.5 oder höher auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-183">The existence of the `Release` DWORD in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key indicates that the .NET Framework 4.5 or later is installed on a computer.</span></span> <span data-ttu-id="ecca3-184">Der Wert des Schlüsselworts gibt die installierte Version an.</span><span class="sxs-lookup"><span data-stu-id="ecca3-184">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="ecca3-185">Um dieses Schlüsselwort zu überprüfen, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType>- und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>-Methode, um auf den Unterschlüssel in der Windows-Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-185">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the subkey in the Windows registry.</span></span>

2. <span data-ttu-id="ecca3-186">Überprüfen Sie den Wert des `Release`-Schlüsselworts, um die installierte Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-186">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="ecca3-187">Um die Aufwärtskompatibilität zu überprüfen, stellen Sie fest, ob ein Wert vorliegt, der größer als der oder gleich dem Wert ist, der im Abschnitt [Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung](#net_b) in der Tabelle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-187">To be forward-compatible, you can check for a value greater than or equal to the value listed in the table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section.</span></span>

<span data-ttu-id="ecca3-188">Das folgende Beispiel überprüft den `Release`-Wert in der Registrierung, um zu ermitteln, ob .NET Framework 4.5 oder eine höhere Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-188">The following example checks the `Release` value in the registry to determine whether .NET Framework 4.5 or a later version is installed.</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="ecca3-189">In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:</span><span class="sxs-lookup"><span data-stu-id="ecca3-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="ecca3-190">Es überprüft, ob der Wert des `Release`-Eintrags *größer als oder gleich* dem Wert der bekannten Versionsschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="ecca3-190">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="ecca3-191">Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.</span><span class="sxs-lookup"><span data-stu-id="ecca3-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="ecca3-192">Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt</span><span class="sxs-lookup"><span data-stu-id="ecca3-192">Check for a minimum required .NET Framework version (4.5 and later) with PowerShell</span></span>

<span data-ttu-id="ecca3-193">Das folgende Beispiel überprüft den Wert des Schlüsselworts `Release`, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist (es wird `True` zurückgegeben, falls es installiert ist, andernfalls `False`).</span><span class="sxs-lookup"><span data-stu-id="ecca3-193">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="ecca3-194">Suchen der aktuellen CLR-Version mit „Clrver.exe“</span><span class="sxs-lookup"><span data-stu-id="ecca3-194">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="ecca3-195">Verwenden Sie das CLR-Versions-Tool (Clrver.exe), um zu bestimmen, welche Versionen der Common Language Runtime auf einem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ecca3-195">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

<span data-ttu-id="ecca3-196">Geben Sie in einer Developer-Eingabeaufforderung für Visual Studio `clrver` ein.</span><span class="sxs-lookup"><span data-stu-id="ecca3-196">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="ecca3-197">Dieser Befehl erzeugt eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ecca3-197">This command produces output similar to the following:</span></span>

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

<span data-ttu-id="ecca3-198">Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Clrver.exe (CLR-Versionstool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span><span class="sxs-lookup"><span data-stu-id="ecca3-198">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="ecca3-199">Suchen der aktuellen CLR-Version mit der Environment-Klasse</span><span class="sxs-lookup"><span data-stu-id="ecca3-199">Find the current CLR version with the Environment class</span></span>

<span data-ttu-id="ecca3-200">Sie können den Wert der <xref:System.Environment.Version?displayProperty=nameWithType>-Eigenschaft abrufen, um ein <xref:System.Version>-Objekt abzurufen, das die Version der Runtime identifiziert, die gerade den Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="ecca3-200">You can retrieve the value of the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="ecca3-201">Diese Eigenschaft gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die derzeit den Code ausführt. Es werden keine Assemblyversionen oder andere Versionen der Runtime zurückgegeben, die ggf. auf dem Computer installiert wurden. Sie können mit der <xref:System.Version.Major%2A?displayProperty=nameWithType>-Eigenschaft den Hauptversionsbezeichner abrufen (z.B. „4“ für Version 4.0), mit der <xref:System.Version.Minor%2A?displayProperty=nameWithType>-Eigenschaft den Nebenversionsbezeichner (z.B. „0“ für Version 4.0), oder mit der <xref:System.Version.ToString%2A?displayProperty=nameWithType>-Methode die gesamte Versionszeichenfolge (z.B. „4.0.30319.18010“, wie im folgenden Code gezeigt).</span><span class="sxs-lookup"><span data-stu-id="ecca3-201">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> 

<span data-ttu-id="ecca3-202">Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 gibt die <xref:System.Environment.Version%2A?displayProperty=nameWithType>Eigenschaft ein <xref:System.Version>-Objekt zurück, dessen Zeichenfolgedarstellung die Form `4.0.30319.xxxxx`besitzt.</span><span class="sxs-lookup"><span data-stu-id="ecca3-202">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="ecca3-203">Für .NET Framework 4.6 und höher weist sie die Form `4.0.30319.42000` auf.</span><span class="sxs-lookup"><span data-stu-id="ecca3-203">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecca3-204">Für .NET Framework 4.5 und höher wird das Verwenden der Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> zum Erkennen der Runtimeversion nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ecca3-204">For the .NET Framework 4.5 and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="ecca3-205">Stattdessen empfehlen wir, dass Sie die Registrierung abfragen, wie im Abschnitt [Ermitteln der .NET Framework-Versionen durch codegesteuertes Abfragen der Registrierung (.NET Framework 4.5 und neuer)](#net_d) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecca3-205">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

<span data-ttu-id="ecca3-206">Das folgende Beispiel verwendet die <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft, um Runtimeversionsinformationen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="ecca3-206">The following example used the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve runtime version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="ecca3-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecca3-207">See also</span></span>

- [<span data-ttu-id="ecca3-208">Vorgehensweise: Bestimmen der installierten .NET Framework-Updates</span><span class="sxs-lookup"><span data-stu-id="ecca3-208">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="ecca3-209">Installieren von .NET Framework für Entwickler</span><span class="sxs-lookup"><span data-stu-id="ecca3-209">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="ecca3-210">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ecca3-210">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)
