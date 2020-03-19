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
ms.openlocfilehash: aecd2f6894558b45898c7f22dd333617d9e2e327
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180363"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="1ba84-102">Regsvcs.exe (.NET Services Installation-Tool)</span><span class="sxs-lookup"><span data-stu-id="1ba84-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="1ba84-103">Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1ba84-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="1ba84-104">Laden und Registrieren einer Assembly</span><span class="sxs-lookup"><span data-stu-id="1ba84-104">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="1ba84-105">Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1ba84-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="1ba84-106">Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="1ba84-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="1ba84-107">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ba84-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="1ba84-108">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1ba84-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="1ba84-109">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1ba84-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba84-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ba84-110">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="1ba84-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ba84-111">Parameters</span></span>  
  
|<span data-ttu-id="1ba84-112">Argument</span><span class="sxs-lookup"><span data-stu-id="1ba84-112">Argument</span></span>|<span data-ttu-id="1ba84-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ba84-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1ba84-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="1ba84-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="1ba84-115">Die Quelldatei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="1ba84-115">The source assembly file.</span></span> <span data-ttu-id="1ba84-116">Die Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1ba84-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="1ba84-117">Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="1ba84-117">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="1ba84-118">Option</span><span class="sxs-lookup"><span data-stu-id="1ba84-118">Option</span></span>|<span data-ttu-id="1ba84-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ba84-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1ba84-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="1ba84-120">**/appdir:** *path*</span></span>|<span data-ttu-id="1ba84-121">Gibt das Stammverzeichnis der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="1ba84-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="1ba84-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="1ba84-123">Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="1ba84-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="1ba84-124">**/c**</span></span>|<span data-ttu-id="1ba84-125">Erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ba84-125">Creates the target application.</span></span>|  
|<span data-ttu-id="1ba84-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="1ba84-126">**/componly**</span></span>|<span data-ttu-id="1ba84-127">Konfiguriert nur Komponenten und ignoriert Methoden und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1ba84-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="1ba84-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="1ba84-128">**/exapp**</span></span>|<span data-ttu-id="1ba84-129">Legt für das Tool fest, dass eine vorhandene Anwendung erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1ba84-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="1ba84-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="1ba84-130">**/extlb**</span></span>|<span data-ttu-id="1ba84-131">Verwendet eine vorhandene Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1ba84-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="1ba84-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="1ba84-132">**/fc**</span></span>|<span data-ttu-id="1ba84-133">Sucht oder erstellt die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ba84-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="1ba84-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="1ba84-134">**/help**</span></span>|<span data-ttu-id="1ba84-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="1ba84-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="1ba84-136">**/noreconfig**</span></span>|<span data-ttu-id="1ba84-137">Eine vorhandene Zielanwendung wird nicht neu konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1ba84-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="1ba84-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="1ba84-138">**/nologo**</span></span>|<span data-ttu-id="1ba84-139">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ba84-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="1ba84-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="1ba84-140">**/parname:** *name*</span></span>|<span data-ttu-id="1ba84-141">Gibt den Namen oder die ID der zu suchenden oder zu erstellenden COM+-Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="1ba84-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="1ba84-142">**/reconfig**</span></span>|<span data-ttu-id="1ba84-143">Konfiguriert eine vorhandene Zielanwendung neu.</span><span class="sxs-lookup"><span data-stu-id="1ba84-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="1ba84-144">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1ba84-144">This is the default.</span></span>|  
|<span data-ttu-id="1ba84-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="1ba84-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="1ba84-146">Gibt die zu installierende Typbibliotheksdatei an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="1ba84-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="1ba84-147">**/u**</span></span>|<span data-ttu-id="1ba84-148">Deinstalliert die Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="1ba84-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="1ba84-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="1ba84-149">**/quiet**</span></span>|<span data-ttu-id="1ba84-150">Gibt den stillen Modus an und unterdrückt das Logo und die Anzeige von Erfolgsmeldungen.</span><span class="sxs-lookup"><span data-stu-id="1ba84-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="1ba84-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="1ba84-151">**/?**</span></span>|<span data-ttu-id="1ba84-152">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba84-153">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ba84-153">Remarks</span></span>  
 <span data-ttu-id="1ba84-154">Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ba84-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="1ba84-155">Diese Assembly muss mit einem starken Namen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="1ba84-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="1ba84-156">Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="1ba84-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="1ba84-157">Die Namen der Zielanwendung und der Typbibliothek sind optional.</span><span class="sxs-lookup"><span data-stu-id="1ba84-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="1ba84-158">Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1ba84-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="1ba84-159">Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden.</span><span class="sxs-lookup"><span data-stu-id="1ba84-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="1ba84-160">Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="1ba84-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="1ba84-161">Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) und [Linkaufrufen](../misc/link-demands.md) für diese Methoden.</span><span class="sxs-lookup"><span data-stu-id="1ba84-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="1ba84-162">Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1ba84-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="1ba84-163">"Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="1ba84-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="1ba84-164">Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="1ba84-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="1ba84-165">Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="1ba84-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1ba84-166">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1ba84-166">Examples</span></span>  
 <span data-ttu-id="1ba84-167">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="1ba84-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="1ba84-168">Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="1ba84-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ba84-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ba84-169">See also</span></span>

- [<span data-ttu-id="1ba84-170">Extras</span><span class="sxs-lookup"><span data-stu-id="1ba84-170">Tools</span></span>](index.md)
- [<span data-ttu-id="1ba84-171">How to: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="1ba84-171">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="1ba84-172">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="1ba84-172">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
