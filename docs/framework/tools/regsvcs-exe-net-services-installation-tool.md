---
title: Regsvcs.exe (.NET Services Installation-Tool)
description: Verwenden Sie „Regsvcs.exe“, das .NET-Dienstinstallationstool. Laden und registrieren Sie eine Assembly, konfigurieren Sie Dienste, die Sie einer Klasse programmgesteuert hinzugefügt haben, und vielesmehr.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: 474018b8bc39e4d5c36bd4bc6481072b218d6270
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558393"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="1ff23-104">Regsvcs.exe (.NET Services Installation-Tool)</span><span class="sxs-lookup"><span data-stu-id="1ff23-104">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="1ff23-105">Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1ff23-105">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="1ff23-106">Laden und Registrieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="1ff23-106">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="1ff23-107">Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1ff23-107">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="1ff23-108">Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="1ff23-108">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="1ff23-109">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ff23-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="1ff23-110">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1ff23-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="1ff23-111">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1ff23-111">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff23-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ff23-112">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="1ff23-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ff23-113">Parameters</span></span>  
  
|<span data-ttu-id="1ff23-114">Argument</span><span class="sxs-lookup"><span data-stu-id="1ff23-114">Argument</span></span>|<span data-ttu-id="1ff23-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ff23-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1ff23-116">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="1ff23-116">*assemblyFile.dll*</span></span>|<span data-ttu-id="1ff23-117">Die Quelldatei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="1ff23-117">The source assembly file.</span></span> <span data-ttu-id="1ff23-118">Die Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1ff23-118">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="1ff23-119">Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="1ff23-119">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="1ff23-120">Option</span><span class="sxs-lookup"><span data-stu-id="1ff23-120">Option</span></span>|<span data-ttu-id="1ff23-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ff23-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1ff23-122">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="1ff23-122">**/appdir:** *path*</span></span>|<span data-ttu-id="1ff23-123">Gibt das Stammverzeichnis der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-123">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="1ff23-124">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="1ff23-124">**/appname:** *applicationName*</span></span>|<span data-ttu-id="1ff23-125">Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-125">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="1ff23-126">**/c**</span><span class="sxs-lookup"><span data-stu-id="1ff23-126">**/c**</span></span>|<span data-ttu-id="1ff23-127">Erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ff23-127">Creates the target application.</span></span>|  
|<span data-ttu-id="1ff23-128">**/componly**</span><span class="sxs-lookup"><span data-stu-id="1ff23-128">**/componly**</span></span>|<span data-ttu-id="1ff23-129">Konfiguriert nur Komponenten und ignoriert Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1ff23-129">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="1ff23-130">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="1ff23-130">**/exapp**</span></span>|<span data-ttu-id="1ff23-131">Legt für das Tool fest, dass eine vorhandene Anwendung erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1ff23-131">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="1ff23-132">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="1ff23-132">**/extlb**</span></span>|<span data-ttu-id="1ff23-133">Verwendet eine vorhandene Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ff23-133">Uses an existing type library.</span></span>|  
|<span data-ttu-id="1ff23-134">**/fc**</span><span class="sxs-lookup"><span data-stu-id="1ff23-134">**/fc**</span></span>|<span data-ttu-id="1ff23-135">Sucht oder erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ff23-135">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="1ff23-136">**/help**</span><span class="sxs-lookup"><span data-stu-id="1ff23-136">**/help**</span></span>|<span data-ttu-id="1ff23-137">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-137">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="1ff23-138">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="1ff23-138">**/noreconfig**</span></span>|<span data-ttu-id="1ff23-139">Eine vorhandene Zielanwendung wird nicht neu konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1ff23-139">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="1ff23-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="1ff23-140">**/nologo**</span></span>|<span data-ttu-id="1ff23-141">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ff23-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="1ff23-142">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="1ff23-142">**/parname:** *name*</span></span>|<span data-ttu-id="1ff23-143">Gibt den Namen oder die ID der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-143">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="1ff23-144">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="1ff23-144">**/reconfig**</span></span>|<span data-ttu-id="1ff23-145">Konfiguriert eine vorhandene Zielanwendung neu.</span><span class="sxs-lookup"><span data-stu-id="1ff23-145">Reconfigures an existing target application.</span></span> <span data-ttu-id="1ff23-146">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1ff23-146">This is the default.</span></span>|  
|<span data-ttu-id="1ff23-147">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="1ff23-147">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="1ff23-148">Gibt die zu installierende Typbibliotheksdatei an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-148">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="1ff23-149">**/u**</span><span class="sxs-lookup"><span data-stu-id="1ff23-149">**/u**</span></span>|<span data-ttu-id="1ff23-150">Deinstalliert die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ff23-150">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="1ff23-151">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="1ff23-151">**/quiet**</span></span>|<span data-ttu-id="1ff23-152">Gibt den stillen Modus an und unterdrückt das Logo und die Anzeige von Erfolgsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="1ff23-152">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="1ff23-153">**/?**</span><span class="sxs-lookup"><span data-stu-id="1ff23-153">**/?**</span></span>|<span data-ttu-id="1ff23-154">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-154">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ff23-155">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ff23-155">Remarks</span></span>  
 <span data-ttu-id="1ff23-156">Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ff23-156">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="1ff23-157">Diese Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1ff23-157">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="1ff23-158">Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="1ff23-158">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="1ff23-159">Die Namen der Zielanwendung und der Typbibliothek sind optional.</span><span class="sxs-lookup"><span data-stu-id="1ff23-159">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="1ff23-160">Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1ff23-160">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="1ff23-161">Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ff23-161">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="1ff23-162">Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="1ff23-162">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="1ff23-163">Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) und [Linkaufrufen](../misc/link-demands.md) für diese Methoden.</span><span class="sxs-lookup"><span data-stu-id="1ff23-163">When Regsvcs.exe registers a component's methods, it is subject to the [demands](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="1ff23-164">Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1ff23-164">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="1ff23-165">"Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="1ff23-165">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="1ff23-166">Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="1ff23-166">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="1ff23-167">Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="1ff23-167">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1ff23-168">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1ff23-168">Examples</span></span>  
 <span data-ttu-id="1ff23-169">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="1ff23-169">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="1ff23-170">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="1ff23-170">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ff23-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ff23-171">See also</span></span>

- [<span data-ttu-id="1ff23-172">Extras</span><span class="sxs-lookup"><span data-stu-id="1ff23-172">Tools</span></span>](index.md)
- [<span data-ttu-id="1ff23-173">How to: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="1ff23-173">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="1ff23-174">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="1ff23-174">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
