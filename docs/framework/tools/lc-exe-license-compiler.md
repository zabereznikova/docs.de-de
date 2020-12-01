---
title: Lc.exe (License Compiler-Tool)
description: Verwenden Sie Lc.exe, den Lizenzcompiler. Dieses Tool liest Textdateien mit Lizenzierungsinformationen und erstellt eine Binärdatei, die als Ressource in eine ausführbare Datei für die CLR eingebettet werden soll.
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: d1644ff4d69c857e36e87f7e83f668908b7ba021
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275761"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="dbc5f-104">Lc.exe (License Compiler-Tool)</span><span class="sxs-lookup"><span data-stu-id="dbc5f-104">Lc.exe (License Compiler)</span></span>

<span data-ttu-id="dbc5f-105">Der Lizenzcompiler liest Textdateien mit Informationen über die Lizenzierung und erstellt eine Binärdatei, die als Ressource in eine ausführbare Datei der Common Language Runtime eingebettet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-105">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="dbc5f-106">Eine LICX-Textdatei wird vom Windows Forms-Designer automatisch generiert oder aktualisiert, sobald dem Formular ein lizenziertes Steuerelement hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-106">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="dbc5f-107">Bei der Kompilierung wandelt das Projektsystem die LICX-Textdatei in eine binäre LICENSES-Ressource um, die die Lizenzierung des .NET-Steuerelements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-107">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="dbc5f-108">Die binäre Ressource wird anschließend in die Projektausgabe eingebettet.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-108">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="dbc5f-109">Kreuzkompilierung zwischen 32-Bit und 64-Bit wird nicht unterstützt, wenn Sie beim Erstellen des Projekts den Lizenzcompiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-109">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="dbc5f-110">Das liegt daran, dass der Lizenzcompiler Assemblys laden muss und das Laden von 64-Bit-Assemblys aus einer 32-Bit-Anwendung und umgekehrt nicht erlaubt ist.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-110">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="dbc5f-111">Verwenden Sie in diesem Fall den Lizenzcompiler von der Befehlszeile aus, um die Lizenz manuell zu kompilieren, und geben Sie die entsprechende Architektur an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-111">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="dbc5f-112">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="dbc5f-113">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-113">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="dbc5f-114">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="dbc5f-114">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="dbc5f-115">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="dbc5f-115">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc5f-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbc5f-116">Syntax</span></span>  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="dbc5f-117">Option</span><span class="sxs-lookup"><span data-stu-id="dbc5f-117">Option</span></span>|<span data-ttu-id="dbc5f-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dbc5f-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="dbc5f-119">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="dbc5f-119">**/complist:** *filename*</span></span>|<span data-ttu-id="dbc5f-120">Gibt den Namen einer Datei an, die die Liste der lizenzierten Komponenten enthält, die in die LICENSES-Datei eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-120">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="dbc5f-121">Auf die einzelnen Komponenten wird mit dem vollständigen Namen verwiesen, wobei pro Zeile jeweils nur eine Komponente aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-121">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="dbc5f-122">Benutzer der Befehlszeile können für jedes Formular des Projekts eine eigene Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-122">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="dbc5f-123">"Lc.exe" akzeptiert mehrere Eingabedateien und erstellt eine einzige LICENSES-Datei.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-123">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="dbc5f-124">**-h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="dbc5f-124">**/h**[**elp**]</span></span>|<span data-ttu-id="dbc5f-125">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-125">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="dbc5f-126">**/i:** *module*</span><span class="sxs-lookup"><span data-stu-id="dbc5f-126">**/i:** *module*</span></span>|<span data-ttu-id="dbc5f-127">Gibt die Module an, die die in der Datei **/complist** aufgelisteten Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-127">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="dbc5f-128">Verwenden Sie mehrere **/i**-Flags, um mehrere Module anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-128">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="dbc5f-129">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="dbc5f-129">**/nologo**</span></span>|<span data-ttu-id="dbc5f-130">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-130">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="dbc5f-131">**/outdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="dbc5f-131">**/outdir:** *path*</span></span>|<span data-ttu-id="dbc5f-132">Gibt das Verzeichnis an, in dem die LICENSES-Ausgabedatei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-132">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="dbc5f-133">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="dbc5f-133">**/target:** *targetPE*</span></span>|<span data-ttu-id="dbc5f-134">Gibt die ausführbare Datei an, für die die LICENSES-Datei generiert wird.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-134">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="dbc5f-135">**/v**</span><span class="sxs-lookup"><span data-stu-id="dbc5f-135">**/v**</span></span>|<span data-ttu-id="dbc5f-136">Gibt den ausführlichen Modus an und zeigt Statusinformationen zur Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-136">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="dbc5f-137">**@** *file*</span><span class="sxs-lookup"><span data-stu-id="dbc5f-137">**@** *file*</span></span>|<span data-ttu-id="dbc5f-138">Gibt die Antwortdatei (.rsp) an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-138">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="dbc5f-139">**/?**</span><span class="sxs-lookup"><span data-stu-id="dbc5f-139">**/?**</span></span>|<span data-ttu-id="dbc5f-140">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-140">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dbc5f-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbc5f-141">Example</span></span>  
  
1. <span data-ttu-id="dbc5f-142">Wenn Sie das lizenzierte Steuerelement `MyCompany.Samples.LicControl1` verwenden, das in `Samples.DLL` in einer Anwendung namens `HostApp.exe` *,* enthalten ist, können Sie `HostAppLic.txt` mit folgendem Inhalt erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-142">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="dbc5f-143">Erstellen Sie die LICENSES-Datei `HostApp.exe.licenses` mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-143">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="dbc5f-144">Erstellen Sie `HostApp.exe` mit der LICENSES-Datei als Ressource.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-144">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="dbc5f-145">Wenn Sie eine C#-Anwendung erstellt haben, erstellen Sie die Anwendung mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-145">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="dbc5f-146">Mit dem folgenden Befehl wird `myApp.licenses` aus den von `hostapplic.txt`, `hostapplic2.txt` und `hostapplic3.txt` angegebenen Listen lizenzierter Komponenten kompiliert.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-146">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="dbc5f-147">Das `modulesList`-Argument gibt die Module mit den lizenzierten Komponenten an.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-147">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="dbc5f-148">Beispiel für eine Antwortdatei</span><span class="sxs-lookup"><span data-stu-id="dbc5f-148">Response File Example</span></span>  

 <span data-ttu-id="dbc5f-149">Die folgende Auflistung enthält ein Beispiel für eine Antwortdatei namens `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-149">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="dbc5f-150">Weitere Informationen zu Antwortdateien finden Sie unter [Antwortdateien](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="dbc5f-150">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="dbc5f-151">In der folgenden Befehlszeile wird die `response.rsp` Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbc5f-151">The following command line uses the `response.rsp` file.</span></span>  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbc5f-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbc5f-152">See also</span></span>

- [<span data-ttu-id="dbc5f-153">Extras</span><span class="sxs-lookup"><span data-stu-id="dbc5f-153">Tools</span></span>](index.md)
- [<span data-ttu-id="dbc5f-154">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="dbc5f-154">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)
- [<span data-ttu-id="dbc5f-155">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="dbc5f-155">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
