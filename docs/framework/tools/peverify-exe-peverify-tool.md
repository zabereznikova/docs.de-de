---
title: Peverify.exe (PEVerify-Tool)
description: Verwenden Sie „Peverify.exe“ (Portable Executable Verify), um zu bestimmen, ob MSIL-Code und -Metadaten (Microsoft Intermediate Language) den Typsicherheitsstandards in .NET entsprechen.
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
ms.openlocfilehash: 478c04a45c7f9d3ad568a6bc4a12a89fe786583a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325617"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="19cd7-103">Peverify.exe (PEVerify-Tool)</span><span class="sxs-lookup"><span data-stu-id="19cd7-103">Peverify.exe (PEVerify tool)</span></span>

<span data-ttu-id="19cd7-104">Mit dem PEVerify-Tool können Entwickler, die MSIL (Microsoft Intermediate Language) generieren (wie Compilerentwickler und Skript-Engine-Entwickler), herausfinden, ob ihr MSIL-Code und die zugeordneten Metadaten den Anforderungen an die Typsicherheit entsprechen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-104">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers and script engine developers) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="19cd7-105">Einige Compiler generieren nur dann überprüfbar typsicheren Code, wenn bestimmte Sprachkonstrukte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19cd7-105">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="19cd7-106">Wenn Sie einen solchen Compiler verwenden, sollten Sie unter Umständen prüfen, ob die Typsicherheit des Codes beeinträchtigt wurde.</span><span class="sxs-lookup"><span data-stu-id="19cd7-106">If you're using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="19cd7-107">Sie können das PEVerify-Tool für die Dateien ausführen und damit die MSIL und Metadaten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-107">You can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="19cd7-108">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="19cd7-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="19cd7-109">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="19cd7-110">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="19cd7-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="19cd7-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="19cd7-111">Syntax</span></span>  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="19cd7-112">Parameter</span><span class="sxs-lookup"><span data-stu-id="19cd7-112">Parameters</span></span>  
  
|<span data-ttu-id="19cd7-113">Argument</span><span class="sxs-lookup"><span data-stu-id="19cd7-113">Argument</span></span>|<span data-ttu-id="19cd7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19cd7-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="19cd7-115">*filename*</span><span class="sxs-lookup"><span data-stu-id="19cd7-115">*filename*</span></span>|<span data-ttu-id="19cd7-116">Die portierbare ausführbare Datei (Portable Executable, PE), deren MSIL und Metadaten überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="19cd7-117">Option</span><span class="sxs-lookup"><span data-stu-id="19cd7-117">Option</span></span>|<span data-ttu-id="19cd7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19cd7-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="19cd7-119">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="19cd7-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="19cd7-120">Bricht die Überprüfung nach *maxErrorCount*-Fehlern ab.</span><span class="sxs-lookup"><span data-stu-id="19cd7-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="19cd7-121">Dieser Parameter wird in .NET Framework, Version 2.0 oder höher, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19cd7-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="19cd7-122">**/clock**</span><span class="sxs-lookup"><span data-stu-id="19cd7-122">**/clock**</span></span>|<span data-ttu-id="19cd7-123">Erfasst und meldet die folgenden Überprüfungszeiten in Millisekunden:</span><span class="sxs-lookup"><span data-stu-id="19cd7-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="19cd7-124">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="19cd7-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="19cd7-125">Validierungszyklus der Metadaten</span><span class="sxs-lookup"><span data-stu-id="19cd7-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="19cd7-126">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="19cd7-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="19cd7-127">Reine Metadatenvalidierung</span><span class="sxs-lookup"><span data-stu-id="19cd7-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="19cd7-128">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="19cd7-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="19cd7-129">Überprüfungszyklus der Microsoft Intermediate Language (MSIL)</span><span class="sxs-lookup"><span data-stu-id="19cd7-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="19cd7-130">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="19cd7-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="19cd7-131">Reine MSIL-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="19cd7-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="19cd7-132">Die Zeiten **MD Val. cycle** und **IL Ver. cycle** umfassen die Zeit, die erforderlich ist, um die notwendigen Prozeduren zum Starten und Herunterfahren auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="19cd7-133">Die Zeiten **MD Val. pure** und **IL Ver pure** umfassen die Zeit, die erforderlich ist, um nur die Validierung oder Überprüfung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="19cd7-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="19cd7-134">**/help**</span></span>|<span data-ttu-id="19cd7-135">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="19cd7-136">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="19cd7-136">**/hresult**</span></span>|<span data-ttu-id="19cd7-137">Zeigt Fehlercodes im Hexadezimalformat an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="19cd7-138">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="19cd7-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="19cd7-139">Ignoriert die angegebenen Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="19cd7-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="19cd7-140">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="19cd7-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="19cd7-141">Ignoriert die in der angegebenen Antwortdatei aufgelisteten Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="19cd7-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="19cd7-142">**/il**</span><span class="sxs-lookup"><span data-stu-id="19cd7-142">**/il**</span></span>|<span data-ttu-id="19cd7-143">Führt Überprüfungen der MSIL-Typsicherheit für Methoden durch, die in der durch *dateiname* angegebenen Assembly implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="19cd7-144">Das Tool gibt eine detaillierte Beschreibung aller gefundenen Probleme zurück, sofern Sie nicht die **/quiet**-Option angeben.</span><span class="sxs-lookup"><span data-stu-id="19cd7-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="19cd7-145">**/md**</span><span class="sxs-lookup"><span data-stu-id="19cd7-145">**/md**</span></span>|<span data-ttu-id="19cd7-146">Führt Validierungen von Metadaten in der durch *Dateiname* angegebenen Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="19cd7-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="19cd7-147">Bei dieser Option wird die gesamte Metadatenstruktur in der Datei durchlaufen und über alle gefundenen Validierungsprobleme berichtet.</span><span class="sxs-lookup"><span data-stu-id="19cd7-147">This option walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="19cd7-148">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="19cd7-148">**/nologo**</span></span>|<span data-ttu-id="19cd7-149">Unterdrückt die Anzeige der Produktversion sowie von Copyrightinformationen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="19cd7-150">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="19cd7-150">**/nosymbols**</span></span>|<span data-ttu-id="19cd7-151">Unterdrückt in .NET Framework, Version 2.0, Zeilennummern, um Abwärtskompatibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="19cd7-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="19cd7-152">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="19cd7-152">**/quiet**</span></span>|<span data-ttu-id="19cd7-153">Gibt den stillen Modus an. Hierbei wird die Ausgabe von Berichten über die während der Überprüfung gefundenen Probleme unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="19cd7-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="19cd7-154">"Peverify.exe" meldet weiterhin, ob die Datei typsicher ist, es werden jedoch keine Informationen zu Problemen ausgegeben, die die Überprüfung der Typsicherheit verhindern.</span><span class="sxs-lookup"><span data-stu-id="19cd7-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="19cd7-155">Überprüfen Sie nur die transparenten Methoden.</span><span class="sxs-lookup"><span data-stu-id="19cd7-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="19cd7-156">**/unique**</span><span class="sxs-lookup"><span data-stu-id="19cd7-156">**/unique**</span></span>|<span data-ttu-id="19cd7-157">Ignoriert wiederholt auftretende Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="19cd7-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="19cd7-158">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="19cd7-158">**/verbose**</span></span>|<span data-ttu-id="19cd7-159">Zeigt in .NET Framework, Version 2.0, zusätzliche Informationen in MSIL-Überprüfungsmeldungen an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="19cd7-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="19cd7-160">**/?**</span></span>|<span data-ttu-id="19cd7-161">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19cd7-162">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19cd7-162">Remarks</span></span>  
 <span data-ttu-id="19cd7-163">Die Common Language Runtime erfordert die typsichere Ausführung von Anwendungscode, um Sicherheits- und Isolierungsmechanismen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="19cd7-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="19cd7-164">Normalerweise kann Code, der nicht [überprüfbar typsicher](../../standard/security/key-security-concepts.md#type-safety-and-security) ist, nicht ausgeführt werden. Sie können jedoch die Sicherheitsrichtlinie so festlegen, dass vertrauenswürdiger, aber nicht überprüfbarer Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19cd7-164">Normally, code that is not [verifiably type safe](../../standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="19cd7-165">Wenn weder die **/md**-Option noch die **/il**-Option angegeben wurde, führt „peverify.exe“ beide Überprüfungen durch.</span><span class="sxs-lookup"><span data-stu-id="19cd7-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="19cd7-166">„everify.exe“ führt zuerst **/md**-Überprüfungen aus.</span><span class="sxs-lookup"><span data-stu-id="19cd7-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="19cd7-167">Wenn keine Fehler auftreten, werden **/il**-Überprüfungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="19cd7-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="19cd7-168">Wenn Sie **/md** und **/il** angeben, werden auch **/il**-Überprüfungen durchgeführt, wenn in den Metadaten Fehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="19cd7-169">Daher stimmt **peverify** *filename* mit **peverify** *filename* **/md** **/il** überein, wenn die Metadaten nicht fehlerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="19cd7-170">"Peverify.exe" führt umfangreiche MSIL-Überprüfungen anhand der Datenflussanalyse sowie einer Liste mit mehreren hundert Regeln für die Gültigkeit von Metadaten durch.</span><span class="sxs-lookup"><span data-stu-id="19cd7-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="19cd7-171">Detaillierte Informationen zu den von „Peverify.exe“ ausgeführten Überprüfungen finden Sie im Windows SDK im Ordner „Tools Developers Guide“ unter „Metadata Validation Specification“ und „MSIL Instruction Set Specification“.</span><span class="sxs-lookup"><span data-stu-id="19cd7-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the Windows SDK.</span></span>  
  
<span data-ttu-id="19cd7-172">.NET Framework, Version 2.0 oder höher, unterstützt überprüfbare `byref`-Rückgaben, die unter Verwendung der folgenden MSIL-Anweisungen angegeben werden: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` und `unbox`.</span><span class="sxs-lookup"><span data-stu-id="19cd7-172">.NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call`, and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="19cd7-173">Beispiele</span><span class="sxs-lookup"><span data-stu-id="19cd7-173">Examples</span></span>  
 <span data-ttu-id="19cd7-174">Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="19cd7-175">Wenn diese Anforderung erfolgreich ausgeführt wurde, zeigt "Peverify.exe" die folgende Meldung an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="19cd7-176">Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="19cd7-177">Das Tool zeigt an, wie viel Zeit zur Durchführung dieser Überprüfungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="19cd7-177">The tool displays the time required to perform these checks.</span></span>  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="19cd7-178">Wenn diese Anforderung erfolgreich ausgeführt wurde, zeigt "Peverify.exe" die folgende Meldung an.</span><span class="sxs-lookup"><span data-stu-id="19cd7-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="19cd7-179">Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="19cd7-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="19cd7-180">"Peverify.exe" wird jedoch beendet, wenn es die maximale Fehleranzahl von 100 erreicht.</span><span class="sxs-lookup"><span data-stu-id="19cd7-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="19cd7-181">Das Tool ignoriert auch die angegebenen Fehlercodes.</span><span class="sxs-lookup"><span data-stu-id="19cd7-181">The tool also ignores the specified error codes.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="19cd7-182">Der folgende Befehl führt zum gleichen Ergebnis wie das vorherige Beispiel, nur werden hier die in der Antwortdatei `ignoreErrors.rsp` zu ignorierenden Fehlercodes angegeben.</span><span class="sxs-lookup"><span data-stu-id="19cd7-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="19cd7-183">Die Antwortdatei kann eine durch Trennzeichen getrennte Liste von Fehlercodes enthalten.</span><span class="sxs-lookup"><span data-stu-id="19cd7-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```text
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="19cd7-184">Wahlweise kann die Antwortdatei auch mit einem Fehlercode pro Zeile formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="19cd7-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="19cd7-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19cd7-185">See also</span></span>

- [<span data-ttu-id="19cd7-186">Extras</span><span class="sxs-lookup"><span data-stu-id="19cd7-186">Tools</span></span>](index.md)
- [<span data-ttu-id="19cd7-187">Schreiben von überprüfbar typsicherem Code</span><span class="sxs-lookup"><span data-stu-id="19cd7-187">Writing Verifiably Type-Safe Code</span></span>](../misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="19cd7-188">Typsicherheit und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="19cd7-188">Type Safety and Security</span></span>](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="19cd7-189">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="19cd7-189">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
