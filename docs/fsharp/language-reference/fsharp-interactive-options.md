---
title: Interaktive Optionen
description: Erfahren Sie mehr über die von F# Interactive unterstützten Befehlszeilenoptionen fsi.exe.
ms.date: 07/22/2020
ms.openlocfilehash: abddd1fd990be18ede139ab26ffe80513ba6e0dd
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855347"
---
# <a name="f-interactive-options"></a><span data-ttu-id="9da46-103">F# Interactive Optionen</span><span class="sxs-lookup"><span data-stu-id="9da46-103">F# Interactive options</span></span>

<span data-ttu-id="9da46-104">In diesem Artikel werden die von F# Interactive unterstützten Befehlszeilenoptionen beschrieben `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="9da46-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="9da46-105">F# Interactive akzeptiert viele der gleichen Befehlszeilenoptionen wie der F #-Compiler, akzeptiert aber auch einige zusätzliche Optionen.</span><span class="sxs-lookup"><span data-stu-id="9da46-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="9da46-106">Verwenden von F# Interactive für die Skripterstellung</span><span class="sxs-lookup"><span data-stu-id="9da46-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="9da46-107">F# Interactive, `dotnet fsi` , kann interaktiv gestartet werden, oder es kann über die Befehlszeile gestartet werden, um ein Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9da46-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="9da46-108">Die Befehlszeilen Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="9da46-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="9da46-109">Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.</span><span class="sxs-lookup"><span data-stu-id="9da46-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="9da46-110">Tabelle der F# Interactive-Optionen</span><span class="sxs-lookup"><span data-stu-id="9da46-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="9da46-111">In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="9da46-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="9da46-112">Sie können diese Optionen in der Befehlszeile oder über die Visual Studio-IDE festlegen.</span><span class="sxs-lookup"><span data-stu-id="9da46-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="9da46-113">Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen Sie **das Menü Extras** , wählen Sie **Optionen**aus, erweitern Sie den Knoten **F #-Tools** , und wählen Sie dann **F# Interactive**aus.</span><span class="sxs-lookup"><span data-stu-id="9da46-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="9da46-114">Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.</span><span class="sxs-lookup"><span data-stu-id="9da46-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="9da46-115">Option</span><span class="sxs-lookup"><span data-stu-id="9da46-115">Option</span></span>|<span data-ttu-id="9da46-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9da46-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="9da46-117">Wird verwendet, um F# Interactive anzuweisen, verbleibende Argumente als Befehlszeilenargumente für das F #-Programm oder-Skript zu behandeln, auf das Sie in Code mithilfe der List **FSI. CommandLineArgs**zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9da46-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="9da46-118">**--aktiviert**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-119">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-120">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-121">**--Codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="9da46-122">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-123">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-125">Gibt Warn-und Fehlermeldungen in Farbe aus.</span><span class="sxs-lookup"><span data-stu-id="9da46-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="9da46-126">**--crossoptimiert**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-127">Aktiviert oder deaktiviert modulübergreifende Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="9da46-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="9da46-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="9da46-129">**--Debug:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="9da46-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="9da46-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="9da46-131">**-g:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="9da46-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="9da46-132">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-133">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-134">**--define: &lt; Zeichenfolge&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="9da46-135">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-136">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-137">**--deterministisch**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-138">Erzeugt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).</span><span class="sxs-lookup"><span data-stu-id="9da46-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="9da46-139">**--Exec**</span><span class="sxs-lookup"><span data-stu-id="9da46-139">**--exec**</span></span>|<span data-ttu-id="9da46-140">Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9da46-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="9da46-141">**--FullPath**</span><span class="sxs-lookup"><span data-stu-id="9da46-141">**--fullpaths**</span></span>|<span data-ttu-id="9da46-142">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-143">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-145">Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife.</span><span class="sxs-lookup"><span data-stu-id="9da46-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="9da46-146">Die Standardeinstellung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9da46-146">The default is enabled.</span></span>|
|<span data-ttu-id="9da46-147">**--Hilfe**</span><span class="sxs-lookup"><span data-stu-id="9da46-147">**--help**</span></span><br /><br /><span data-ttu-id="9da46-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="9da46-148">**-?**</span></span>|<span data-ttu-id="9da46-149">Wird verwendet, um die Befehlszeilen Syntax und eine kurze Beschreibung der einzelnen Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9da46-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="9da46-150">**--lib: &lt; Ordner-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="9da46-151">**-I: &lt; Ordnerliste&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="9da46-152">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-153">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-154">**--Load: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="9da46-155">Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9da46-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span> <span data-ttu-id="9da46-156">Wenn die Ziel Quelle Skript Direktiven wie **#use** oder **#Load**enthält, müssen Sie **--use** oder **#use** anstelle von **--Load** oder **#Load**verwenden.</span><span class="sxs-lookup"><span data-stu-id="9da46-156">If the target source contains scripting directives such as **#use** or **#load**, then you must use **--use** or **#use** instead of **--load** or **#load**.</span></span>|
|<span data-ttu-id="9da46-157">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="9da46-157">**--mlcompatibility**</span></span>|<span data-ttu-id="9da46-158">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-158">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-159">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-159">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-160">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="9da46-160">**--noframework**</span></span>|<span data-ttu-id="9da46-161">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-161">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-162">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md) .</span><span class="sxs-lookup"><span data-stu-id="9da46-162">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="9da46-163">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="9da46-163">**--nologo**</span></span>|<span data-ttu-id="9da46-164">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-164">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-165">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-165">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-166">**--nowarn: &lt; Warning-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-166">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="9da46-167">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-167">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-168">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-168">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-169">**--optimieren**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-169">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-170">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-170">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-171">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-171">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-172">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-172">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="9da46-173">Gibt den bevorzugten Kultur Namen der Ausgabesprache an (z. b. "es-es", "ja-JP").</span><span class="sxs-lookup"><span data-stu-id="9da46-173">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="9da46-174">**--Quiet**</span><span class="sxs-lookup"><span data-stu-id="9da46-174">**--quiet**</span></span>|<span data-ttu-id="9da46-175">Unterdrücken der F# Interactive Ausgabe in den **stdout** -Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="9da46-175">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="9da46-176">**--Zitate-Debuggen**</span><span class="sxs-lookup"><span data-stu-id="9da46-176">**--quotations-debug**</span></span>|<span data-ttu-id="9da46-177">Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9da46-177">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="9da46-178">Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksstrukturknotens hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9da46-178">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="9da46-179">Weitere Informationen finden Sie unter [Code Notierungen](code-quotations.md) und [expr. CustomAttribute](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span><span class="sxs-lookup"><span data-stu-id="9da46-179">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="9da46-180">**--Read Line**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-180">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-181">Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.</span><span class="sxs-lookup"><span data-stu-id="9da46-181">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="9da46-182">**--Reference: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-182">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="9da46-183">**-r: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-183">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="9da46-184">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-184">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-185">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-185">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-186">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-186">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-187">Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht.</span><span class="sxs-lookup"><span data-stu-id="9da46-187">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="9da46-188">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9da46-188">This option is enabled by default.</span></span>|
|<span data-ttu-id="9da46-189">**--targetprofile: &lt; Zeichenfolge&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-189">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="9da46-190">Gibt das zielframeworkprofil dieser Assembly an.</span><span class="sxs-lookup"><span data-stu-id="9da46-190">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="9da46-191">Gültige Werte sind `mscorlib`, `netcore` oder `netstandard`.</span><span class="sxs-lookup"><span data-stu-id="9da46-191">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="9da46-192">Der Standardwert lautet `mscorlib`.</span><span class="sxs-lookup"><span data-stu-id="9da46-192">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="9da46-193">**--use: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-193">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="9da46-194">Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9da46-194">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="9da46-195">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="9da46-195">**--utf8output**</span></span>|<span data-ttu-id="9da46-196">Identisch mit der fsc.exe-Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-196">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="9da46-197">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-197">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-198">**--Warn: &lt; Warnstufe&gt;**</span><span class="sxs-lookup"><span data-stu-id="9da46-198">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="9da46-199">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-199">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-200">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-200">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-201">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="9da46-201">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="9da46-202">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-202">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-203">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-203">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="9da46-204">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-List &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="9da46-204">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="9da46-205">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="9da46-205">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="9da46-206">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="9da46-206">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="9da46-207">F# Interactive strukturierter Druck</span><span class="sxs-lookup"><span data-stu-id="9da46-207">F# Interactive structured printing</span></span>

<span data-ttu-id="9da46-208">F# Interactive ( `dotnet fsi` ) verwendet eine erweiterte Version der [strukturierten Klartext-Formatierung](plaintext-formatting.md) , um Werte zu melden.</span><span class="sxs-lookup"><span data-stu-id="9da46-208">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="9da46-209">Alle Funktionen der nur `%A` -Text-Formatierung werden unterstützt, und einige sind zusätzlich anpassbar.</span><span class="sxs-lookup"><span data-stu-id="9da46-209">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="9da46-210">Das Drucken wird eingefärbt, wenn Farben von der Ausgabe Konsole unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="9da46-210">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="9da46-211">Es wird ein Grenzwert für die Länge der angezeigten Zeichen folgen festgelegt, es sei denn, Sie bewerten diese Zeichenfolge explizit.</span><span class="sxs-lookup"><span data-stu-id="9da46-211">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="9da46-212">Eine Reihe von benutzerdefinierbaren Einstellungen ist über das- `fsi` Objekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9da46-212">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="9da46-213">Die verfügbaren Einstellungen zum Anpassen des Klartext-Druckens für gemeldete Werte lauten:</span><span class="sxs-lookup"><span data-stu-id="9da46-213">The available settings to customize plain text printing for reported values are:</span></span>

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="9da46-214">Anpassen mit `AddPrinter` und`AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="9da46-214">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="9da46-215">Das Drucken in F# Interactive Ausgaben kann mithilfe von und angepasst werden `fsi.AddPrinter` `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="9da46-215">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="9da46-216">Die erste Funktion gibt Text an, um das Drucken eines Objekts zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9da46-216">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="9da46-217">Die zweite Funktion gibt ein Ersatzobjekt zurück, das stattdessen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9da46-217">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="9da46-218">Sehen Sie sich beispielsweise den folgenden F #-Code an:</span><span class="sxs-lookup"><span data-stu-id="9da46-218">For example, consider the following F# code:</span></span>

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

<span data-ttu-id="9da46-219">Wenn Sie das Beispiel in F# Interactive ausführen, wird es basierend auf der Formatierungs Options Menge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="9da46-219">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="9da46-220">In diesem Fall hat dies Auswirkungen auf die Formatierung von Datum und Uhrzeit:</span><span class="sxs-lookup"><span data-stu-id="9da46-220">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="9da46-221">`fsi.AddPrintTransformer`kann verwendet werden, um ein Ersatzobjekt zum Drucken zu geben:</span><span class="sxs-lookup"><span data-stu-id="9da46-221">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="9da46-222">Diese Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9da46-222">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="9da46-223">Wenn die an übertraene Transformer-Funktion `fsi.AddPrintTransformer` zurückgegeben `null` wird, wird der Druck Transformator ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9da46-223">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="9da46-224">Dies kann verwendet werden, um beliebige Eingabewerte zu filtern, indem Sie mit dem Typ beginnen `obj` .</span><span class="sxs-lookup"><span data-stu-id="9da46-224">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="9da46-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9da46-225">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="9da46-226">Diese Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9da46-226">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="9da46-227">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9da46-227">Related topics</span></span>

|<span data-ttu-id="9da46-228">Titel</span><span class="sxs-lookup"><span data-stu-id="9da46-228">Title</span></span>|<span data-ttu-id="9da46-229">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9da46-229">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="9da46-230">Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="9da46-230">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="9da46-231">Beschreibt die Befehlszeilenoptionen, die für den F #-Compiler verfügbar sind, **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="9da46-231">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
