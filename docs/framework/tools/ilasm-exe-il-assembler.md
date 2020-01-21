---
title: Ilasm.exe (IL-Assembler)
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: cb995e78e534048043886070536ef0dd0a45c057
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105095"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="349ef-102">Ilasm.exe (IL-Assembler)</span><span class="sxs-lookup"><span data-stu-id="349ef-102">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="349ef-103">Der IL-Assembler generiert eine portierbare ausführbare Datei (Portable Executable, PE) aus der Zwischensprache (Intermediate Language, IL).</span><span class="sxs-lookup"><span data-stu-id="349ef-103">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="349ef-104">Weitere Informationen über die Zwischensprache finden Sie unter [Der verwaltete Ausführungsprozess](../../standard/managed-execution-process.md). Die erstellte ausführbare Datei, die IL und die erforderlichen Metadaten enthält, können Sie ausführen, um zu überprüfen, ob die IL wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="349ef-104">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="349ef-105">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="349ef-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="349ef-106">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="349ef-106">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="349ef-107">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="349ef-107">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="349ef-108">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="349ef-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="349ef-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="349ef-109">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="349ef-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="349ef-110">Parameters</span></span>

| <span data-ttu-id="349ef-111">Argument</span><span class="sxs-lookup"><span data-stu-id="349ef-111">Argument</span></span> | <span data-ttu-id="349ef-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="349ef-112">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="349ef-113">Der Name der IL-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="349ef-113">The name of the .il source file.</span></span> <span data-ttu-id="349ef-114">Diese Datei besteht aus Direktiven für die Deklaration von Metadaten und symbolischen IL-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="349ef-114">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="349ef-115">Zum Erstellen einer einzelnen PE-Datei mithilfe von *Ilasm.exe* können mehrere Quelldateiargumente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="349ef-115">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="349ef-116">**Hinweis**: Vergewissern Sie sich, dass die letzte Codezeile in der IL-Quelldatei entweder ein nachgestelltes Leerzeichen oder ein Zeilenendezeichen besitzt.</span><span class="sxs-lookup"><span data-stu-id="349ef-116">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="349ef-117">Option</span><span class="sxs-lookup"><span data-stu-id="349ef-117">Option</span></span> | <span data-ttu-id="349ef-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="349ef-118">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="349ef-119">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="349ef-119">**/32bitpreferred**</span></span>|<span data-ttu-id="349ef-120">Erstellt ein Abbild im PE32-Format (vorzugweise 32 Bit).</span><span class="sxs-lookup"><span data-stu-id="349ef-120">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="349ef-121">**/alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="349ef-121">**/alignment:** `integer`</span></span>|<span data-ttu-id="349ef-122">Legt FileAlignment auf den Wert fest, der im NT Optional-Header per `integer` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="349ef-122">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="349ef-123">Wenn die .alignment-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="349ef-123">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="349ef-124">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="349ef-124">**/appcontainer**</span></span>|<span data-ttu-id="349ef-125">Erstellt als Ausgabe eine *DLL*- oder *EXE*-Datei, die im Windows-App-Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="349ef-125">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="349ef-126">**/arm**</span><span class="sxs-lookup"><span data-stu-id="349ef-126">**/arm**</span></span>|<span data-ttu-id="349ef-127">Gibt die ARM (Advanced RISC Machine) als Zielprozessor an.</span><span class="sxs-lookup"><span data-stu-id="349ef-127">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="349ef-128">Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="349ef-128">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="349ef-129">**/base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="349ef-129">**/base:** `integer`</span></span>|<span data-ttu-id="349ef-130">Legt ImageBase auf den Wert fest, der im NT Optional-Header per `integer` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="349ef-130">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="349ef-131">Wenn die .imagebase-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="349ef-131">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="349ef-132">**/clock**</span><span class="sxs-lookup"><span data-stu-id="349ef-132">**/clock**</span></span>|<span data-ttu-id="349ef-133">Erfasst und berichtet die folgenden Kompilierungszeiten (in Millisekunden) für die angegebene IL-Quelldatei:</span><span class="sxs-lookup"><span data-stu-id="349ef-133">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="349ef-134">**Total Run:** Die gesamte für die Ausführung aller nachfolgenden spezifischen Vorgänge benötigte Zeit.</span><span class="sxs-lookup"><span data-stu-id="349ef-134">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="349ef-135">**Startup:** Laden und Öffnen der Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-135">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="349ef-136">**Emitting MD:** Ausgabe von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="349ef-136">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="349ef-137">**Ref to Def Resolution:** Auflösen von Verweisen auf Definitionen in der Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-137">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="349ef-138">**CEE File Generation:** Generieren des Dateiimages im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="349ef-138">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="349ef-139">**PE File Writing:** Schreiben des Images in eine PE-Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-139">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="349ef-140">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="349ef-140">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="349ef-141">Schließt Debuginformationen (Namen lokaler Variablen und Argumente sowie Zeilennummern) ein.</span><span class="sxs-lookup"><span data-stu-id="349ef-141">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="349ef-142">Erstellt eine PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-142">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="349ef-143">**/debug** ohne zusätzlichen Wert deaktiviert die JIT-Optimierung und verwendet Sequenzpunkte aus der PDB-Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-143">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="349ef-144">**IMPL** deaktiviert die JIT-Optimierung und verwendet implizite Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="349ef-144">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="349ef-145">**OPT** aktiviert die JIT-Optimierung und verwendet implizite Sequenzpunkte.</span><span class="sxs-lookup"><span data-stu-id="349ef-145">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="349ef-146">**/dll**</span><span class="sxs-lookup"><span data-stu-id="349ef-146">**/dll**</span></span>|<span data-ttu-id="349ef-147">Erzeugt eine *DLL*-Datei als Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="349ef-147">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="349ef-148">**/enc:** `file`</span><span class="sxs-lookup"><span data-stu-id="349ef-148">**/enc:** `file`</span></span>|<span data-ttu-id="349ef-149">Erstellt Edit-and-Continue-Deltas aus der angegebenen Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="349ef-149">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="349ef-150">Die Verwendung dieses Arguments ist nur zu akademischen Zwecken vorgesehen. Ein Einsatz zu kommerziellen Zwecken wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="349ef-150">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="349ef-151">**/exe**</span><span class="sxs-lookup"><span data-stu-id="349ef-151">**/exe**</span></span>|<span data-ttu-id="349ef-152">Erstellt eine ausführbare Datei als Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="349ef-152">Produces an executable file as output.</span></span> <span data-ttu-id="349ef-153">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="349ef-153">This is the default.</span></span>|
|<span data-ttu-id="349ef-154">**/flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="349ef-154">**/flags:** `integer`</span></span>|<span data-ttu-id="349ef-155">Legt ImageFlags“ auf den Wert, der im Common Language Runtime-Header durch `integer` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="349ef-155">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="349ef-156">Wenn die .corflags-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="349ef-156">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="349ef-157">Eine Liste der für *integer*gültigen Werte finden Sie unter "CorHdr.h, COMIMAGE_FLAGS".</span><span class="sxs-lookup"><span data-stu-id="349ef-157">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="349ef-158">**/fold**</span><span class="sxs-lookup"><span data-stu-id="349ef-158">**/fold**</span></span>|<span data-ttu-id="349ef-159">Fasst identische Methodentexte in einem Text zusammen.</span><span class="sxs-lookup"><span data-stu-id="349ef-159">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="349ef-160">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="349ef-160">/**highentropyva**</span></span>|<span data-ttu-id="349ef-161">Erstellt eine ausführbare Ausgabedatei, die ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="349ef-161">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="349ef-162">(Standardeinstellung für **/appcontainer**.)</span><span class="sxs-lookup"><span data-stu-id="349ef-162">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="349ef-163">**/include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="349ef-163">**/include:** `includePath`</span></span>|<span data-ttu-id="349ef-164">Legt einen Suchpfad für in `#include`aufgeführte Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="349ef-164">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="349ef-165">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="349ef-165">**/itanium**</span></span>|<span data-ttu-id="349ef-166">Gibt Intel Itanium als Zielprozessor an.</span><span class="sxs-lookup"><span data-stu-id="349ef-166">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="349ef-167">Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="349ef-167">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="349ef-168">**/key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="349ef-168">**/key:** `keyFile`</span></span>|<span data-ttu-id="349ef-169">Kompiliert `filename` mit einer starken Signatur unter Verwendung des privaten Schlüssels in `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="349ef-169">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="349ef-170">**/key:**  @`keySource`</span><span class="sxs-lookup"><span data-stu-id="349ef-170">**/key:** @`keySource`</span></span>|<span data-ttu-id="349ef-171">Kompiliert `filename` mit einer starken Signatur unter Verwendung des bei `keySource` erstellten privaten Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="349ef-171">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="349ef-172">**/listing**</span><span class="sxs-lookup"><span data-stu-id="349ef-172">**/listing**</span></span>|<span data-ttu-id="349ef-173">Erstellt eine Listingdatei in der Standardausgabe.</span><span class="sxs-lookup"><span data-stu-id="349ef-173">Produces a listing file on the standard output.</span></span> <span data-ttu-id="349ef-174">Wenn Sie diese Option weglassen, wird keine Listingdatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="349ef-174">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="349ef-175">In .NET Framework 2.0 (oder höher) wird dieser Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="349ef-175">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="349ef-176">**/mdv:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="349ef-176">**/mdv:** `versionString`</span></span>|<span data-ttu-id="349ef-177">Legt die Zeichenfolge der Metadatenversion fest.</span><span class="sxs-lookup"><span data-stu-id="349ef-177">Sets the metadata version string.</span></span>|
|<span data-ttu-id="349ef-178">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="349ef-178">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="349ef-179">Legt die Version des Metadatenstreams fest, wobei `major` und `minor` ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="349ef-179">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="349ef-180">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="349ef-180">**/noautoinherit**</span></span>|<span data-ttu-id="349ef-181">Deaktiviert die Standardvererbung von <xref:System.Object> , wenn keine Basisklasse angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="349ef-181">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="349ef-182">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="349ef-182">**/nocorstub**</span></span>|<span data-ttu-id="349ef-183">Unterdrückt die Generierung des CORExeMain-Stubs.</span><span class="sxs-lookup"><span data-stu-id="349ef-183">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="349ef-184">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="349ef-184">**/nologo**</span></span>|<span data-ttu-id="349ef-185">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="349ef-185">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="349ef-186">**/output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="349ef-186">**/output:** `file.ext`</span></span>|<span data-ttu-id="349ef-187">Gibt den Namen und die Erweiterung der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="349ef-187">Specifies the output file name and extension.</span></span> <span data-ttu-id="349ef-188">In der Standardeinstellung ist der Name der Ausgabedatei mit dem der ersten Quelldatei identisch.</span><span class="sxs-lookup"><span data-stu-id="349ef-188">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="349ef-189">Die Standarderweiterung ist *.exe*.</span><span class="sxs-lookup"><span data-stu-id="349ef-189">The default extension is *.exe*.</span></span> <span data-ttu-id="349ef-190">Wenn Sie die Option **/dll** angeben, lautet die Standarderweiterung *.dll*.</span><span class="sxs-lookup"><span data-stu-id="349ef-190">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="349ef-191">**Hinweis**: Durch Angabe von „ **/output**:myfile.dll“ wird die Option **/dll** nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="349ef-191">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="349ef-192">Wenn Sie **/dll** nicht angeben, wird eine ausführbare Datei mit dem Namen *myfile.dll* erstellt.</span><span class="sxs-lookup"><span data-stu-id="349ef-192">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="349ef-193">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="349ef-193">**/optimize**</span></span>|<span data-ttu-id="349ef-194">Optimiert lange Anweisungen in kurze Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="349ef-194">Optimizes long instructions to short.</span></span> <span data-ttu-id="349ef-195">Beispiel: `br` wird zu `br.s`.</span><span class="sxs-lookup"><span data-stu-id="349ef-195">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="349ef-196">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="349ef-196">**/pe64**</span></span>|<span data-ttu-id="349ef-197">Erstellt ein 64-Bit-Abbild (PE32+).</span><span class="sxs-lookup"><span data-stu-id="349ef-197">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="349ef-198">Wenn kein Zielprozessor angegeben wird, lautet der Standardwert `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="349ef-198">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="349ef-199">**/pdb**</span><span class="sxs-lookup"><span data-stu-id="349ef-199">**/pdb**</span></span>|<span data-ttu-id="349ef-200">Erstellt eine PDB-Datei, ohne das Nachverfolgen von Debuginformationen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="349ef-200">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="349ef-201">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="349ef-201">**/quiet**</span></span>|<span data-ttu-id="349ef-202">Gibt den stillen Modus an, bei dem keine Angaben zum Verlauf der Assembly gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="349ef-202">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="349ef-203">**/resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="349ef-203">**/resource:** `file.res`</span></span>|<span data-ttu-id="349ef-204">Bezieht die angegebene Ressourcendatei im Format „\*.res“ in die resultierende *EXE*- oder *DLL*-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="349ef-204">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="349ef-205">Mit der Option **/resource** kann nur eine einzige RES-Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="349ef-205">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="349ef-206">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="349ef-206">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="349ef-207">Legt die Subsystemversionsnummer im NT Optional-Header fest.</span><span class="sxs-lookup"><span data-stu-id="349ef-207">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="349ef-208">Für **/appcontainer** und **/arm** lautet die minimale Versionsnummer 6.02.</span><span class="sxs-lookup"><span data-stu-id="349ef-208">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="349ef-209">**/stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="349ef-209">**/stack:** `stackSize`</span></span>|<span data-ttu-id="349ef-210">Legt den SizeOfStackReserve-Wert im NT Optional-Header auf `stackSize`fest.</span><span class="sxs-lookup"><span data-stu-id="349ef-210">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="349ef-211">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="349ef-211">**/stripreloc**</span></span>|<span data-ttu-id="349ef-212">Gibt an, dass Basisumsetzungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="349ef-212">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="349ef-213">**/subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="349ef-213">**/subsystem:** `integer`</span></span>|<span data-ttu-id="349ef-214">Legt „subsystem“ auf den Wert fest, der im NT Optional-Header durch `integer` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="349ef-214">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="349ef-215">Wenn die .subsystem-IL-Direktive in der Datei angegeben ist, wird sie durch diesen Befehl überschrieben.</span><span class="sxs-lookup"><span data-stu-id="349ef-215">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="349ef-216">Eine Liste der gültigen Werte für `integer` finden Sie unter „winnt.h, IMAGE_SUBSYSTEM“.</span><span class="sxs-lookup"><span data-stu-id="349ef-216">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="349ef-217">**/x64**</span><span class="sxs-lookup"><span data-stu-id="349ef-217">**/x64**</span></span>|<span data-ttu-id="349ef-218">Gibt einen 64-Bit-AMD-Prozessor als Zielprozessor an.</span><span class="sxs-lookup"><span data-stu-id="349ef-218">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="349ef-219">Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="349ef-219">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="349ef-220">**/?**</span><span class="sxs-lookup"><span data-stu-id="349ef-220">**/?**</span></span>|<span data-ttu-id="349ef-221">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="349ef-221">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="349ef-222">Bei allen Optionen für *Ilasm.exe* wird nicht zwischen Groß- und Kleinschreibung unterschieden, und sie werden anhand der ersten drei Buchstaben erkannt.</span><span class="sxs-lookup"><span data-stu-id="349ef-222">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="349ef-223">So ist zum Beispiel **/lis** das Gleiche wie **/listing**, und **/res**:myresfile.res entspricht **/resource:** myresfile.res. Optionen, die Argumente angeben, können entweder einen Doppelpunkt (:) oder ein Gleichheitszeichen (=) als Trennzeichen zwischen der Option und dem Argument enthalten.</span><span class="sxs-lookup"><span data-stu-id="349ef-223">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="349ef-224">So wären zum Beispiel **/output:** *file.ext* und **/output=** =*file.ext* identisch.</span><span class="sxs-lookup"><span data-stu-id="349ef-224">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="349ef-225">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="349ef-225">Remarks</span></span>

<span data-ttu-id="349ef-226">Der IL-Assembler unterstützt Anbieter von Tools beim Entwerfen und Implementieren von IL-Generatoren.</span><span class="sxs-lookup"><span data-stu-id="349ef-226">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="349ef-227">Durch die Verwendung von *Ilasm.exe* können sich Entwickler von Tools und Compilern auf die Generierung von IL und Metadaten konzentrieren, ohne sich um IL-Ausgaben im PE-Dateiformat kümmern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="349ef-227">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="349ef-228">Ähnlich wie andere Laufzeitcompiler (z.B. C# und Visual Basic) erstellt *Ilasm.exe* keine Objektzwischendateien und benötigt keine Verknüpfungsstufe zum Erstellen einer PE-Datei.</span><span class="sxs-lookup"><span data-stu-id="349ef-228">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="349ef-229">Der IL-Assembler kann alle vorhandenen Metadaten und IL-Funktionen der Programmiersprachen ausdrücken, die die Laufzeit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="349ef-229">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="349ef-230">Dadurch kann verwalteter Code, der in einer dieser Programmiersprachen geschrieben wurde, im IL-Assembler adäquat ausgedrückt und mit *Ilasm.exe* kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="349ef-230">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="349ef-231">Wenn die letzte Codezeile in der IL-Quelldatei weder ein nachgestelltes Leerzeichen noch ein Zeilenendezeichen besitzt, kann die Kompilierung fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="349ef-231">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="349ef-232">Sie können *Ilasm.exe* zusammen mit dem zugehörigen Tool [*Ildasm.exe*](ildasm-exe-il-disassembler.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="349ef-232">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="349ef-233">*Ildasm.exe* nimmt eine PE-Datei mit IL-Code entgegen und erstellt eine Textdatei, die als Eingabe für *Ilasm.exe* geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="349ef-233">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="349ef-234">Dies ist zum Beispiel nützlich, wenn Code in einer Programmiersprache programmiert werde soll, die nicht alle Attribute der Metadaten der Laufzeit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="349ef-234">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="349ef-235">Nachdem der Code kompiliert und die Ausgabe über *Ildasm.exe* verarbeitet wurde, kann die resultierende IL-Textdatei manuell bearbeitet werden, um die fehlenden Attribute hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="349ef-235">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="349ef-236">Anschließend können Sie diese Textdatei per *Ilasm.exe* verarbeiten, um eine endgültige ausführbare Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="349ef-236">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="349ef-237">Mit diesem Verfahren können Sie auch eine einzelne PE-Datei aus mehreren PE-Dateien erstellen, die von unterschiedlichen Compilern generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="349ef-237">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="349ef-238">Für PE-Dateien, die eingebetteten systemeigenen Code enthalten (z. B. von Visual C++ erstellte PE-Dateien), ist dieses Verfahren gegenwärtig jedoch nicht geeignet.</span><span class="sxs-lookup"><span data-stu-id="349ef-238">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="349ef-239">Damit dieses Zusammenspiel von *Ildasm.exe* und *Ilasm.exe* so exakt wie möglich erfolgt, ersetzt der Assembler lange Codierungen (die Sie möglicherweise in Ihren IL-Quellen geschrieben haben oder die aus einem anderen Compiler ausgegeben wurden) standardmäßig nicht durch kurze Codierungen.</span><span class="sxs-lookup"><span data-stu-id="349ef-239">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="349ef-240">Verwenden Sie die Option **/optimize** , um kurze Codierungen nach Möglichkeit zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="349ef-240">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="349ef-241">*Ildasm.exe* kann nur für Dateien auf der Festplatte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="349ef-241">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="349ef-242">Bei Dateien, die im globalen Assemblycache installiert sind, funktioniert dieses Tool nicht.</span><span class="sxs-lookup"><span data-stu-id="349ef-242">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="349ef-243">Weitere Informationen zur Grammatik von IL finden Sie in der Datei „asmparse.grammar“ im Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="349ef-243">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="349ef-244">Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="349ef-244">Version Information</span></span>

<span data-ttu-id="349ef-245">Ab .NET Framework 4.5 können Sie ein benutzerdefiniertes Attribut an eine Schnittstellenimplementierung anfügen, indem Sie Code verwenden, der in etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="349ef-245">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="349ef-246">Ab .NET Framework 4.5 können Sie ein beliebiges Marshall-BLOB (Binary Large Object) angeben, indem Sie die entsprechenden unformatierten Binärdaten wie im folgenden Code gezeigt angeben:</span><span class="sxs-lookup"><span data-stu-id="349ef-246">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="349ef-247">Weitere Informationen zur Grammatik von IL finden Sie in der Datei „asmparse.grammar“ im Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="349ef-247">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="349ef-248">Beispiele</span><span class="sxs-lookup"><span data-stu-id="349ef-248">Examples</span></span>

<span data-ttu-id="349ef-249">Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die ausführbare Datei *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="349ef-249">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="349ef-250">Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die *DLL*-Datei *myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="349ef-250">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="349ef-251">Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die *DLL*-Datei *myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="349ef-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="349ef-252">Im folgenden Codebeispiel wird eine sehr einfache Anwendung gezeigt, die "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="349ef-252">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="349ef-253">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="349ef-253">to the console.</span></span> <span data-ttu-id="349ef-254">Sie können diesen Code kompilieren und dann das Tool [*Ildasm.exe*](ildasm-exe-il-disassembler.md) verwenden, um eine IL-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="349ef-254">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="349ef-255">Das folgende IL-Codebeispiel entspricht dem vorherigen C#-Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="349ef-255">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="349ef-256">Sie können diesen Code mithilfe des IL Assembler-Tools in eine Assembly kompilieren.</span><span class="sxs-lookup"><span data-stu-id="349ef-256">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="349ef-257">Sowohl der IL- als auch der C#-Beispielcode geben "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="349ef-257">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="349ef-258">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="349ef-258">to the console.</span></span>

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="349ef-259">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="349ef-259">See also</span></span>

- [<span data-ttu-id="349ef-260">Extras</span><span class="sxs-lookup"><span data-stu-id="349ef-260">Tools</span></span>](index.md)
- [<span data-ttu-id="349ef-261">*Ildasm.exe* (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="349ef-261">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="349ef-262">Der verwaltete Ausführungsprozess</span><span class="sxs-lookup"><span data-stu-id="349ef-262">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="349ef-263">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="349ef-263">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
