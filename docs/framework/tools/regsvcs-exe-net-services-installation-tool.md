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
ms.openlocfilehash: fc349e13aba84de8c266442e9be8130e5f8604c2
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219775"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="b86bd-102">Regsvcs.exe (.NET Services Installation-Tool)</span><span class="sxs-lookup"><span data-stu-id="b86bd-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="b86bd-103">Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b86bd-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
-   <span data-ttu-id="b86bd-104">Laden und Registrieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="b86bd-104">Loads and registers an assembly.</span></span>  
  
-   <span data-ttu-id="b86bd-105">Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b86bd-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
-   <span data-ttu-id="b86bd-106">Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="b86bd-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="b86bd-107">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b86bd-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b86bd-108">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b86bd-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="b86bd-109">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b86bd-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b86bd-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b86bd-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b86bd-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="b86bd-111">Parameters</span></span>  
  
|<span data-ttu-id="b86bd-112">Argument</span><span class="sxs-lookup"><span data-stu-id="b86bd-112">Argument</span></span>|<span data-ttu-id="b86bd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b86bd-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b86bd-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="b86bd-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="b86bd-115">Die Quelldatei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="b86bd-115">The source assembly file.</span></span> <span data-ttu-id="b86bd-116">Die Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="b86bd-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="b86bd-117">Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="b86bd-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="b86bd-118">Option</span><span class="sxs-lookup"><span data-stu-id="b86bd-118">Option</span></span>|<span data-ttu-id="b86bd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b86bd-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b86bd-120">**/appdir:** *pfad*</span><span class="sxs-lookup"><span data-stu-id="b86bd-120">**/appdir:** *path*</span></span>|<span data-ttu-id="b86bd-121">Gibt das Stammverzeichnis der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="b86bd-122">**/appname:** *anwendungsname*</span><span class="sxs-lookup"><span data-stu-id="b86bd-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="b86bd-123">Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="b86bd-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="b86bd-124">**/c**</span></span>|<span data-ttu-id="b86bd-125">Erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="b86bd-125">Creates the target application.</span></span>|  
|<span data-ttu-id="b86bd-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="b86bd-126">**/componly**</span></span>|<span data-ttu-id="b86bd-127">Konfiguriert nur Komponenten und ignoriert Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b86bd-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="b86bd-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="b86bd-128">**/exapp**</span></span>|<span data-ttu-id="b86bd-129">Legt für das Tool fest, dass eine vorhandene Anwendung erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="b86bd-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="b86bd-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="b86bd-130">**/extlb**</span></span>|<span data-ttu-id="b86bd-131">Verwendet eine vorhandene Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b86bd-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="b86bd-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="b86bd-132">**/fc**</span></span>|<span data-ttu-id="b86bd-133">Sucht oder erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="b86bd-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="b86bd-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="b86bd-134">**/help**</span></span>|<span data-ttu-id="b86bd-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="b86bd-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="b86bd-136">**/noreconfig**</span></span>|<span data-ttu-id="b86bd-137">Eine vorhandene Zielanwendung wird nicht neu konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b86bd-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="b86bd-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="b86bd-138">**/nologo**</span></span>|<span data-ttu-id="b86bd-139">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b86bd-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="b86bd-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="b86bd-140">**/parname:** *name*</span></span>|<span data-ttu-id="b86bd-141">Gibt den Namen oder die ID der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="b86bd-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="b86bd-142">**/reconfig**</span></span>|<span data-ttu-id="b86bd-143">Konfiguriert eine vorhandene Zielanwendung neu.</span><span class="sxs-lookup"><span data-stu-id="b86bd-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="b86bd-144">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b86bd-144">This is the default.</span></span>|  
|<span data-ttu-id="b86bd-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="b86bd-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="b86bd-146">Gibt die zu installierende Typbibliotheksdatei an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="b86bd-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="b86bd-147">**/u**</span></span>|<span data-ttu-id="b86bd-148">Deinstalliert die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="b86bd-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="b86bd-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="b86bd-149">**/quiet**</span></span>|<span data-ttu-id="b86bd-150">Gibt den stillen Modus an und unterdrückt das Logo und die Anzeige von Erfolgsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="b86bd-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="b86bd-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="b86bd-151">**/?**</span></span>|<span data-ttu-id="b86bd-152">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b86bd-153">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b86bd-153">Remarks</span></span>  
 <span data-ttu-id="b86bd-154">Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b86bd-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="b86bd-155">Diese Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="b86bd-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="b86bd-156">Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="b86bd-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="b86bd-157">Die Namen der Zielanwendung und der Typbibliothek sind optional.</span><span class="sxs-lookup"><span data-stu-id="b86bd-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="b86bd-158">Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b86bd-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="b86bd-159">Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden.</span><span class="sxs-lookup"><span data-stu-id="b86bd-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="b86bd-160">Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="b86bd-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="b86bd-161">Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) und [Linkaufrufen](../../../docs/framework/misc/link-demands.md) für diese Methoden.</span><span class="sxs-lookup"><span data-stu-id="b86bd-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="b86bd-162">Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b86bd-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="b86bd-163">"Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="b86bd-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="b86bd-164">Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b86bd-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="b86bd-165">Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="b86bd-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b86bd-166">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b86bd-166">Examples</span></span>  
 <span data-ttu-id="b86bd-167">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="b86bd-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="b86bd-168">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="b86bd-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="b86bd-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b86bd-169">See also</span></span>
- [<span data-ttu-id="b86bd-170">Extras</span><span class="sxs-lookup"><span data-stu-id="b86bd-170">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="b86bd-171">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="b86bd-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [<span data-ttu-id="b86bd-172">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="b86bd-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
