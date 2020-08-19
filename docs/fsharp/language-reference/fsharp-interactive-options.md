---
title: Interaktive Optionen
description: Erfahren Sie mehr über die von F# Interactive unterstützten Befehlszeilenoptionen fsi.exe.
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558607"
---
# <a name="f-interactive-options"></a><span data-ttu-id="af40b-103">F# Interactive Optionen</span><span class="sxs-lookup"><span data-stu-id="af40b-103">F# Interactive options</span></span>

<span data-ttu-id="af40b-104">In diesem Artikel werden die von F# Interactive unterstützten Befehlszeilenoptionen beschrieben `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="af40b-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="af40b-105">F# Interactive akzeptiert viele der gleichen Befehlszeilenoptionen wie der F #-Compiler, akzeptiert aber auch einige zusätzliche Optionen.</span><span class="sxs-lookup"><span data-stu-id="af40b-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="af40b-106">Verwenden von F# Interactive für die Skripterstellung</span><span class="sxs-lookup"><span data-stu-id="af40b-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="af40b-107">F# Interactive, `dotnet fsi` , kann interaktiv gestartet werden, oder es kann über die Befehlszeile gestartet werden, um ein Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af40b-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="af40b-108">Die Befehlszeilen Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="af40b-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="af40b-109">Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.</span><span class="sxs-lookup"><span data-stu-id="af40b-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="af40b-110">Tabelle der F# Interactive-Optionen</span><span class="sxs-lookup"><span data-stu-id="af40b-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="af40b-111">In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="af40b-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="af40b-112">Sie können diese Optionen in der Befehlszeile oder über die Visual Studio-IDE festlegen.</span><span class="sxs-lookup"><span data-stu-id="af40b-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="af40b-113">Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen Sie **das Menü Extras** , wählen Sie **Optionen**aus, erweitern Sie den Knoten **F #-Tools** , und wählen Sie dann **F# Interactive**aus.</span><span class="sxs-lookup"><span data-stu-id="af40b-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="af40b-114">Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.</span><span class="sxs-lookup"><span data-stu-id="af40b-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="af40b-115">Option</span><span class="sxs-lookup"><span data-stu-id="af40b-115">Option</span></span>|<span data-ttu-id="af40b-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af40b-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="af40b-117">Wird verwendet, um F# Interactive anzuweisen, verbleibende Argumente als Befehlszeilenargumente für das F #-Programm oder-Skript zu behandeln, auf das Sie in Code mithilfe der List **FSI. CommandLineArgs**zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="af40b-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="af40b-118">**--aktiviert**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-119">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-120">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-121">**--Codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="af40b-122">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-123">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-125">Gibt Warn-und Fehlermeldungen in Farbe aus.</span><span class="sxs-lookup"><span data-stu-id="af40b-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="af40b-126">**--crossoptimiert**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-127">Aktiviert oder deaktiviert modulübergreifende Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="af40b-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="af40b-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="af40b-129">**--Debug:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="af40b-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="af40b-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="af40b-131">**-g:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="af40b-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="af40b-132">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-133">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-134">**--define: &lt; Zeichenfolge&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="af40b-135">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-136">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-137">**--deterministisch**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-138">Erzeugt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).</span><span class="sxs-lookup"><span data-stu-id="af40b-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="af40b-139">**--Exec**</span><span class="sxs-lookup"><span data-stu-id="af40b-139">**--exec**</span></span>|<span data-ttu-id="af40b-140">Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="af40b-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="af40b-141">**--FullPath**</span><span class="sxs-lookup"><span data-stu-id="af40b-141">**--fullpaths**</span></span>|<span data-ttu-id="af40b-142">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-143">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-145">Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife.</span><span class="sxs-lookup"><span data-stu-id="af40b-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="af40b-146">Die Standardeinstellung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af40b-146">The default is enabled.</span></span>|
|<span data-ttu-id="af40b-147">**--Hilfe**</span><span class="sxs-lookup"><span data-stu-id="af40b-147">**--help**</span></span><br /><br /><span data-ttu-id="af40b-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="af40b-148">**-?**</span></span>|<span data-ttu-id="af40b-149">Wird verwendet, um die Befehlszeilen Syntax und eine kurze Beschreibung der einzelnen Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af40b-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="af40b-150">**--lib: &lt; Ordner-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="af40b-151">**-I: &lt; Ordnerliste&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="af40b-152">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-153">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-154">**--Load: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="af40b-155">Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="af40b-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span>|
|<span data-ttu-id="af40b-156">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="af40b-156">**--mlcompatibility**</span></span>|<span data-ttu-id="af40b-157">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-157">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-158">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-158">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-159">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="af40b-159">**--noframework**</span></span>|<span data-ttu-id="af40b-160">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-160">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-161">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md) .</span><span class="sxs-lookup"><span data-stu-id="af40b-161">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="af40b-162">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="af40b-162">**--nologo**</span></span>|<span data-ttu-id="af40b-163">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-163">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-164">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-164">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-165">**--nowarn: &lt; Warning-List&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-165">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="af40b-166">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-166">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-167">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-167">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-168">**--optimieren**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-168">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-169">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-169">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-170">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-170">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-171">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-171">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="af40b-172">Gibt den bevorzugten Kultur Namen der Ausgabesprache an (z. b. "es-es", "ja-JP").</span><span class="sxs-lookup"><span data-stu-id="af40b-172">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="af40b-173">**--Quiet**</span><span class="sxs-lookup"><span data-stu-id="af40b-173">**--quiet**</span></span>|<span data-ttu-id="af40b-174">Unterdrücken der F# Interactive Ausgabe in den **stdout** -Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="af40b-174">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="af40b-175">**--Zitate-Debuggen**</span><span class="sxs-lookup"><span data-stu-id="af40b-175">**--quotations-debug**</span></span>|<span data-ttu-id="af40b-176">Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="af40b-176">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="af40b-177">Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksstrukturknotens hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="af40b-177">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="af40b-178">Weitere Informationen finden Sie unter [Code Notierungen](code-quotations.md) und [expr. CustomAttribute](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span><span class="sxs-lookup"><span data-stu-id="af40b-178">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="af40b-179">**--Read Line**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-179">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-180">Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.</span><span class="sxs-lookup"><span data-stu-id="af40b-180">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="af40b-181">**--Reference: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-181">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="af40b-182">**-r: &lt; Dateiname&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-182">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="af40b-183">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-183">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-184">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-184">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-185">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-185">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-186">Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht.</span><span class="sxs-lookup"><span data-stu-id="af40b-186">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="af40b-187">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af40b-187">This option is enabled by default.</span></span>|
|<span data-ttu-id="af40b-188">**--targetprofile: &lt; Zeichenfolge&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-188">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="af40b-189">Gibt das zielframeworkprofil dieser Assembly an.</span><span class="sxs-lookup"><span data-stu-id="af40b-189">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="af40b-190">Gültige Werte sind `mscorlib`, `netcore` oder `netstandard`.</span><span class="sxs-lookup"><span data-stu-id="af40b-190">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="af40b-191">Der Standardwert lautet `mscorlib`.</span><span class="sxs-lookup"><span data-stu-id="af40b-191">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="af40b-192">**--use: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-192">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="af40b-193">Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="af40b-193">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="af40b-194">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="af40b-194">**--utf8output**</span></span>|<span data-ttu-id="af40b-195">Identisch mit der fsc.exe-Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-195">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="af40b-196">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-196">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-197">**--Warn: &lt; Warnstufe&gt;**</span><span class="sxs-lookup"><span data-stu-id="af40b-197">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="af40b-198">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-198">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-199">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-199">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-200">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="af40b-200">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="af40b-201">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-201">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-202">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-202">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="af40b-203">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-List &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="af40b-203">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="af40b-204">Identisch mit der **fsc.exe** -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="af40b-204">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="af40b-205">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="af40b-205">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="af40b-206">F# Interactive strukturierter Druck</span><span class="sxs-lookup"><span data-stu-id="af40b-206">F# Interactive structured printing</span></span>

<span data-ttu-id="af40b-207">F# Interactive ( `dotnet fsi` ) verwendet eine erweiterte Version der [strukturierten Klartext-Formatierung](plaintext-formatting.md) , um Werte zu melden.</span><span class="sxs-lookup"><span data-stu-id="af40b-207">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="af40b-208">Alle Funktionen der nur `%A` -Text-Formatierung werden unterstützt, und einige sind zusätzlich anpassbar.</span><span class="sxs-lookup"><span data-stu-id="af40b-208">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="af40b-209">Das Drucken wird eingefärbt, wenn Farben von der Ausgabe Konsole unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="af40b-209">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="af40b-210">Es wird ein Grenzwert für die Länge der angezeigten Zeichen folgen festgelegt, es sei denn, Sie bewerten diese Zeichenfolge explizit.</span><span class="sxs-lookup"><span data-stu-id="af40b-210">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="af40b-211">Eine Reihe von benutzerdefinierbaren Einstellungen ist über das- `fsi` Objekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af40b-211">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="af40b-212">Die verfügbaren Einstellungen zum Anpassen des Klartext-Druckens für gemeldete Werte lauten:</span><span class="sxs-lookup"><span data-stu-id="af40b-212">The available settings to customize plain text printing for reported values are:</span></span>

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

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="af40b-213">Anpassen mit `AddPrinter` und `AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="af40b-213">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="af40b-214">Das Drucken in F# Interactive Ausgaben kann mithilfe von und angepasst werden `fsi.AddPrinter` `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="af40b-214">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="af40b-215">Die erste Funktion gibt Text an, um das Drucken eines Objekts zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="af40b-215">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="af40b-216">Die zweite Funktion gibt ein Ersatzobjekt zurück, das stattdessen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="af40b-216">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="af40b-217">Sehen Sie sich beispielsweise den folgenden F #-Code an:</span><span class="sxs-lookup"><span data-stu-id="af40b-217">For example, consider the following F# code:</span></span>

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

<span data-ttu-id="af40b-218">Wenn Sie das Beispiel in F# Interactive ausführen, wird es basierend auf der Formatierungs Options Menge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="af40b-218">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="af40b-219">In diesem Fall hat dies Auswirkungen auf die Formatierung von Datum und Uhrzeit:</span><span class="sxs-lookup"><span data-stu-id="af40b-219">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="af40b-220">`fsi.AddPrintTransformer` kann verwendet werden, um ein Ersatzobjekt zum Drucken zu geben:</span><span class="sxs-lookup"><span data-stu-id="af40b-220">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="af40b-221">Diese Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="af40b-221">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="af40b-222">Wenn die an übertraene Transformer-Funktion `fsi.AddPrintTransformer` zurückgegeben `null` wird, wird der Druck Transformator ignoriert.</span><span class="sxs-lookup"><span data-stu-id="af40b-222">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="af40b-223">Dies kann verwendet werden, um beliebige Eingabewerte zu filtern, indem Sie mit dem Typ beginnen `obj` .</span><span class="sxs-lookup"><span data-stu-id="af40b-223">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="af40b-224">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af40b-224">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="af40b-225">Diese Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="af40b-225">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="af40b-226">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="af40b-226">Related topics</span></span>

|<span data-ttu-id="af40b-227">Titel</span><span class="sxs-lookup"><span data-stu-id="af40b-227">Title</span></span>|<span data-ttu-id="af40b-228">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af40b-228">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="af40b-229">Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="af40b-229">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="af40b-230">Beschreibt die Befehlszeilenoptionen, die für den F #-Compiler verfügbar sind, **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="af40b-230">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
