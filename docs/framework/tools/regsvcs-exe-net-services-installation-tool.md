---
title: Regsvcs.exe (.NET Services Installation-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3de5b196d6ec35febe4ba30f7ac41bacacf884cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529107"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="d2ba1-102">Regsvcs.exe (.NET Services Installation-Tool)</span><span class="sxs-lookup"><span data-stu-id="d2ba1-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="d2ba1-103">Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d2ba1-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
-   <span data-ttu-id="d2ba1-104">Laden und Registrieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="d2ba1-104">Loads and registers an assembly.</span></span>  
  
-   <span data-ttu-id="d2ba1-105">Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d2ba1-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
-   <span data-ttu-id="d2ba1-106">Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="d2ba1-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="d2ba1-107">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="d2ba1-107">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d2ba1-108">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d2ba1-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="d2ba1-109">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d2ba1-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ba1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2ba1-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2ba1-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2ba1-111">Parameters</span></span>  
  
|<span data-ttu-id="d2ba1-112">Argument</span><span class="sxs-lookup"><span data-stu-id="d2ba1-112">Argument</span></span>|<span data-ttu-id="d2ba1-113">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="d2ba1-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d2ba1-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="d2ba1-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="d2ba1-115">Die Quelldatei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-115">The source assembly file.</span></span> <span data-ttu-id="d2ba1-116">Die Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="d2ba1-117">Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="d2ba1-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="d2ba1-118">Option</span><span class="sxs-lookup"><span data-stu-id="d2ba1-118">Option</span></span>|<span data-ttu-id="d2ba1-119">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="d2ba1-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d2ba1-120">**/appdir:** *pfad*</span><span class="sxs-lookup"><span data-stu-id="d2ba1-120">**/appdir:** *path*</span></span>|<span data-ttu-id="d2ba1-121">Gibt das Stammverzeichnis der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="d2ba1-122">**/appname:** *anwendungsname*</span><span class="sxs-lookup"><span data-stu-id="d2ba1-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="d2ba1-123">Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="d2ba1-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-124">**/c**</span></span>|<span data-ttu-id="d2ba1-125">Erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-125">Creates the target application.</span></span>|  
|<span data-ttu-id="d2ba1-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-126">**/componly**</span></span>|<span data-ttu-id="d2ba1-127">Konfiguriert nur Komponenten und ignoriert Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="d2ba1-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-128">**/exapp**</span></span>|<span data-ttu-id="d2ba1-129">Legt für das Tool fest, dass eine vorhandene Anwendung erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="d2ba1-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-130">**/extlb**</span></span>|<span data-ttu-id="d2ba1-131">Verwendet eine vorhandene Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="d2ba1-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-132">**/fc**</span></span>|<span data-ttu-id="d2ba1-133">Sucht oder erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="d2ba1-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-134">**/help**</span></span>|<span data-ttu-id="d2ba1-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="d2ba1-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-136">**/noreconfig**</span></span>|<span data-ttu-id="d2ba1-137">Eine vorhandene Zielanwendung wird nicht neu konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="d2ba1-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-138">**/nologo**</span></span>|<span data-ttu-id="d2ba1-139">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="d2ba1-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="d2ba1-140">**/parname:** *name*</span></span>|<span data-ttu-id="d2ba1-141">Gibt den Namen oder die ID der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="d2ba1-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-142">**/reconfig**</span></span>|<span data-ttu-id="d2ba1-143">Konfiguriert eine vorhandene Zielanwendung neu.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="d2ba1-144">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-144">This is the default.</span></span>|  
|<span data-ttu-id="d2ba1-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="d2ba1-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="d2ba1-146">Gibt die zu installierende Typbibliotheksdatei an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="d2ba1-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-147">**/u**</span></span>|<span data-ttu-id="d2ba1-148">Deinstalliert die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="d2ba1-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-149">**/quiet**</span></span>|<span data-ttu-id="d2ba1-150">Gibt den stillen Modus an und unterdrückt das Logo und die Anzeige von Erfolgsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="d2ba1-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="d2ba1-151">**/?**</span></span>|<span data-ttu-id="d2ba1-152">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2ba1-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2ba1-153">Remarks</span></span>  
 <span data-ttu-id="d2ba1-154">Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="d2ba1-155">Diese Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="d2ba1-156">Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="d2ba1-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="d2ba1-157">Die Namen der Zielanwendung und der Typbibliothek sind optional.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="d2ba1-158">Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="d2ba1-159">Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="d2ba1-160">Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="d2ba1-161">Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](https://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) und [Linkaufrufen](../../../docs/framework/misc/link-demands.md) für diese Methoden.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://msdn.microsoft.com/library/e5283e28-2366-4519-b27d-ef5c1ddc1f48) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="d2ba1-162">Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="d2ba1-163">"Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="d2ba1-164">Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="d2ba1-165">Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d2ba1-166">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d2ba1-166">Examples</span></span>  
 <span data-ttu-id="d2ba1-167">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="d2ba1-168">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="d2ba1-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2ba1-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ba1-169">See Also</span></span>  
 [<span data-ttu-id="d2ba1-170">Extras</span><span class="sxs-lookup"><span data-stu-id="d2ba1-170">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="d2ba1-171">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="d2ba1-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="d2ba1-172">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="d2ba1-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
