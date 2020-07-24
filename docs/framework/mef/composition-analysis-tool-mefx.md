---
title: Kompositionsanalysetool (Mefx)
description: In diesem Artikel erhalten Sie Informationen zum Kompositionsanalysetool (Mefx), das DLL- und EXE-Dateien analysiert, die Managed Extensibility Framework-Teile (MEF) in .NET enthalten.
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: abb1459afc5aeb2d39ee553c62fe382bb7af58d5
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281276"
---
# <a name="composition-analysis-tool-mefx"></a><span data-ttu-id="1184e-103">Kompositionsanalysetool (Mefx)</span><span class="sxs-lookup"><span data-stu-id="1184e-103">Composition Analysis Tool (Mefx)</span></span>
<span data-ttu-id="1184e-104">Das Kompositionsanalysetool MEFX ist eine Befehlszeilenanwendung, die Bibliotheks- (.dll) und Anwendungsdateien (.exe) mit Teilen des Managed Extensibility Framework (MEF) analysiert.</span><span class="sxs-lookup"><span data-stu-id="1184e-104">The Composition Analysis Tool (Mefx) is a command-line application that analyzes library (.dll) and application (.exe) files containing Managed Extensibility Framework (MEF) parts.</span></span> <span data-ttu-id="1184e-105">MEFX dient in erster Linie dazu, Entwicklern eine Möglichkeit zur Diagnose von Kompositionsfehlern in MEF-Anwendungen zu bieten, ohne dass der Anwendung selbst unübersichtlicher Ablaufverfolgungscode hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1184e-105">The primary purpose of Mefx is to provide developers a way to diagnose composition failures in their MEF applications without the requirement to add cumbersome tracing code to the application itself.</span></span> <span data-ttu-id="1184e-106">Darüber hinaus kann das Tool nützlich sein, um Teile einer Bibliothek zu verstehen, die von einem Drittanbieter bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1184e-106">It can also be useful to help understand parts from a library provided by a third party.</span></span> <span data-ttu-id="1184e-107">In diesem Thema wird beschrieben, wie MEFX verwendet wird, und ein Verweis auf die Syntax wird bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1184e-107">This topic describes how to use Mefx and provides a reference for its syntax.</span></span>  
  
<a name="getting_mefx"></a>
## <a name="getting-mefx"></a><span data-ttu-id="1184e-108">Abrufen von MEFX</span><span class="sxs-lookup"><span data-stu-id="1184e-108">Getting Mefx</span></span>  
 <span data-ttu-id="1184e-109">MEFX steht auf GitHub unter [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1184e-109">Mefx is available on GitHub at [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span></span> <span data-ttu-id="1184e-110">Nach dem Herunterladen müssen Sie das Tool nur noch entpacken.</span><span class="sxs-lookup"><span data-stu-id="1184e-110">Simply download and unzip the tool.</span></span>  
  
<a name="basic_syntax"></a>
## <a name="basic-syntax"></a><span data-ttu-id="1184e-111">Allgemeine Syntax</span><span class="sxs-lookup"><span data-stu-id="1184e-111">Basic Syntax</span></span>  
 <span data-ttu-id="1184e-112">MEFX kann wie folgt über die Befehlszeile aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="1184e-112">Mefx is invoked from the command line in the following format:</span></span>  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 <span data-ttu-id="1184e-113">Im ersten Satz von Argumenten werden die Dateien und Verzeichnisse angegeben, aus denen Teile für die Analyse geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-113">The first set of arguments specify the files and directories from which to load parts for analysis.</span></span> <span data-ttu-id="1184e-114">Dateien können mit dem Schalter `/file:` und Verzeichnisse mit dem Schalter `/directory:` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-114">Specify a file with the `/file:` switch, and a directory with the `/directory:` switch.</span></span> <span data-ttu-id="1184e-115">Sie können mehrere Dateien oder Verzeichnisse angeben, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1184e-115">You can specify multiple files or directories, as shown in the following example:</span></span>  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> <span data-ttu-id="1184e-116">Jede DLL- oder EXE-Datei sollte nur einmal geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-116">Each .dll or .exe should only be loaded one time.</span></span> <span data-ttu-id="1184e-117">Wenn eine Datei mehrmals geladen wird, gibt das Tool möglicherweise falsche Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="1184e-117">If a file is loaded multiple times, the tool may return incorrect information.</span></span>  
  
 <span data-ttu-id="1184e-118">Nach der Liste der Dateien und Verzeichnisse müssen Sie einen Befehl sowie alle Optionen für den Befehl angeben.</span><span class="sxs-lookup"><span data-stu-id="1184e-118">After the list of files and directories, you must specify a command, and any options for that command.</span></span>  
  
<a name="listing_available_parts"></a>
## <a name="listing-available-parts"></a><span data-ttu-id="1184e-119">Auflisten verfügbarer Teile</span><span class="sxs-lookup"><span data-stu-id="1184e-119">Listing Available Parts</span></span>  
 <span data-ttu-id="1184e-120">Mit der Aktion `/parts` können Sie alle deklarierten Teile in den geladenen Dateien auflisten.</span><span class="sxs-lookup"><span data-stu-id="1184e-120">Use the `/parts` action to list all the parts declared in the files loaded.</span></span> <span data-ttu-id="1184e-121">Das Ergebnis ist eine einfache Liste mit den Namen der Teile.</span><span class="sxs-lookup"><span data-stu-id="1184e-121">The result is a simple list of part names.</span></span>  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 <span data-ttu-id="1184e-122">Mit der Option `/verbose` können Sie weitere Informationen über Teile abrufen.</span><span class="sxs-lookup"><span data-stu-id="1184e-122">For more information about the parts, use the `/verbose` option.</span></span> <span data-ttu-id="1184e-123">Dadurch erhalten Sie weitere Angaben zu allen verfügbaren Teilen.</span><span class="sxs-lookup"><span data-stu-id="1184e-123">This will output more information for all available parts.</span></span> <span data-ttu-id="1184e-124">Um weitere Informationen über ein einzelnes Teil abzurufen, verwenden Sie die Aktion `/type` anstelle von `/parts`.</span><span class="sxs-lookup"><span data-stu-id="1184e-124">To get more information about a single part, use the `/type` action instead of `/parts`.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>
## <a name="listing-imports-and-exports"></a><span data-ttu-id="1184e-125">Auflisten von Importen und Exporten</span><span class="sxs-lookup"><span data-stu-id="1184e-125">Listing Imports and Exports</span></span>  
 <span data-ttu-id="1184e-126">Mit der Aktion `/imports` und der Aktion `/exports` werden alle importierten Teile und alle exportierten Teile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1184e-126">The `/imports` and `/exports` actions will list all the imported parts and all the exported parts, respectively.</span></span> <span data-ttu-id="1184e-127">Sie können auch die Teile auflisten, mit denen ein bestimmter Typ importiert oder exportiert wird, indem Sie die `/importers` - oder die `/exporters` -Aktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1184e-127">You can also list the parts that import or export a particular type by using the `/importers` or `/exporters` actions.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 <span data-ttu-id="1184e-128">Sie können auch die `/verbose` -Option für diese Aktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1184e-128">You can also apply the `/verbose` option to these actions.</span></span>  
  
<a name="finding_rejected_parts"></a>
## <a name="finding-rejected-parts"></a><span data-ttu-id="1184e-129">Suchen abgelehnter Teile</span><span class="sxs-lookup"><span data-stu-id="1184e-129">Finding Rejected Parts</span></span>  
 <span data-ttu-id="1184e-130">Sobald die verfügbaren Teile geladen wurden, werden diese von MEFX mit der MEF-Kompositions-Engine erstellt.</span><span class="sxs-lookup"><span data-stu-id="1184e-130">Once it has loaded the available parts, Mefx uses the MEF composition engine to compose them.</span></span> <span data-ttu-id="1184e-131">Die Teile, die nicht erfolgreich erstellt werden können, werden als *abgelehnt*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1184e-131">Parts that cannot be successfully composed are referred to as *rejected*.</span></span> <span data-ttu-id="1184e-132">Mit der `/rejected` -Aktion können Sie alle abgelehnten Teile auflisten.</span><span class="sxs-lookup"><span data-stu-id="1184e-132">To list all the rejected parts, use the `/rejected` action.</span></span>  
  
 <span data-ttu-id="1184e-133">Mit der `/verbose` -Option und der `/rejected` -Aktion können Sie detaillierte Informationen über abgelehnte Teile ausgeben.</span><span class="sxs-lookup"><span data-stu-id="1184e-133">You can use the `/verbose` option with the `/rejected` action to print detailed information about rejected parts.</span></span> <span data-ttu-id="1184e-134">Die DLL-Datei `ClassLibrary1` im folgenden Beispiel enthält das Teil `AddIn` , mit dem das Teil `MemberPart` und das Teil `ChainOne` importiert werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-134">In the following example, the `ClassLibrary1` DLL contains the `AddIn` part, which imports the `MemberPart` and `ChainOne` parts.</span></span> <span data-ttu-id="1184e-135">`ChainOne` importiert `ChainTwo`, `ChainTwo` ist jedoch nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1184e-135">`ChainOne` imports `ChainTwo`, but `ChainTwo` does not exist.</span></span> <span data-ttu-id="1184e-136">Dies bedeutet, dass `ChainOne` abgelehnt wird, wodurch `AddIn` abgelehnt wird.</span><span class="sxs-lookup"><span data-stu-id="1184e-136">This means that `ChainOne` is rejected, which causes `AddIn` to be rejected.</span></span>  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 <span data-ttu-id="1184e-137">Im Folgenden wird die gesamte Ausgabe des vorherigen Befehls veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1184e-137">The following shows the complete output of the previous command:</span></span>  
  
```output
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 <span data-ttu-id="1184e-138">Die interessanten Ergebnisse sind in `[Exception]` und `[Unsuitable]` enthalten.</span><span class="sxs-lookup"><span data-stu-id="1184e-138">The interesting information is contained in the `[Exception]` and `[Unsuitable]` results.</span></span> <span data-ttu-id="1184e-139">Das Ergebnis `[Exception]` enthält Informationen dazu, warum ein Teil abgelehnt wurde.</span><span class="sxs-lookup"><span data-stu-id="1184e-139">The `[Exception]` result provides information about why a part was rejected.</span></span> <span data-ttu-id="1184e-140">Das `[Unsuitable]` -Ergebnis gibt an, warum ein Teil, das andernfalls geeignet gewesen wäre, nicht zum Ausfüllen eines Imports verwendet werden konnte. Im vorliegenden Fall wurde das Teil selbst aufgrund fehlender Importe abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="1184e-140">The `[Unsuitable]` result indicates why an otherwise-matching part could not be used to fill an import; in this case, because that part was itself rejected for missing imports.</span></span>  
  
<a name="analyzing_primary_causes"></a>
## <a name="analyzing-primary-causes"></a><span data-ttu-id="1184e-141">Analysieren primärer Ursachen</span><span class="sxs-lookup"><span data-stu-id="1184e-141">Analyzing Primary Causes</span></span>  
 <span data-ttu-id="1184e-142">Bei mehreren verknüpften Teilen in einer langen Abhängigkeitskette kann ein Problem mit einem Teil im unteren Bereich zu einer Ablehnung der gesamten Kette führen.</span><span class="sxs-lookup"><span data-stu-id="1184e-142">If several parts are linked in a long dependency chain, a problem involving a part near the bottom may cause the entire chain to be rejected.</span></span> <span data-ttu-id="1184e-143">Diese Probleme können sich als schwerwiegend erweisen, da die Ursache des Fehlers nicht immer offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="1184e-143">Diagnosing these problems can be difficult because the root cause of the failure is not always obvious.</span></span> <span data-ttu-id="1184e-144">Um eine Lösung für das Problem zu finden, können Sie die `/causes` -Aktion verwenden. Diese Aktion zielt darauf ab, die Ursache einer kaskadierenden Ablehnung zu finden.</span><span class="sxs-lookup"><span data-stu-id="1184e-144">To help with the problem, you can use the `/causes` action, which attempts to find the root cause of any cascading rejection.</span></span>  
  
 <span data-ttu-id="1184e-145">Wenn Sie die `/causes` -Aktion im vorangehenden Beispiel verwenden, werden nur Informationen für `ChainOne`aufgeführt. Der nicht ausgefüllte Import ist in diesem Fall die Ursache für die Ablehnung von `AddIn`.</span><span class="sxs-lookup"><span data-stu-id="1184e-145">Using the `/causes` action on the previous example would list only information for `ChainOne`, whose unfilled import is the root cause of the rejection of `AddIn`.</span></span> <span data-ttu-id="1184e-146">Die `/causes` -Aktion kann bei normalen und `/verbose` -Optionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-146">The `/causes` action can be used in both normal and `/verbose` options.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1184e-147">In den meisten Fällen können Sie mithilfe von MEFX die Ursache eines kaskadierenden Fehlers aufspüren.</span><span class="sxs-lookup"><span data-stu-id="1184e-147">In most cases, Mefx will be able to diagnose the root cause of a cascading failure.</span></span> <span data-ttu-id="1184e-148">Wenn die Teile einem Container jedoch programmgesteuert hinzugefügt werden, wenn hierarchische Container verwendet werden oder wenn benutzerdefinierte `ExportProvider` -Implementierungen enthalten sind, kann die Ursache nicht mit MEFX ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-148">However, in cases where parts are added programmatically to a container, cases involving hierarchical containers, or cases involving custom `ExportProvider` implementations, Mefx will not be able to diagnose the cause.</span></span> <span data-ttu-id="1184e-149">Die vorstehend beschriebenen Fälle sollten nach Möglichkeit vermieden werden, da hier eine Fehlerdiagnose nur sehr schwer möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1184e-149">In general, the previously described cases should be avoided where possible, as failures are generally difficult to diagnose.</span></span>  
  
<a name="white_lists"></a>
## <a name="white-lists"></a><span data-ttu-id="1184e-150">Whitelisten</span><span class="sxs-lookup"><span data-stu-id="1184e-150">White Lists</span></span>  
 <span data-ttu-id="1184e-151">Mit der `/whitelist` -Option können Sie eine Textdatei mit den Teilen angeben, die wahrscheinlich abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-151">The `/whitelist` option enables you to specify a text file that lists parts that are expected to be rejected.</span></span> <span data-ttu-id="1184e-152">Unerwartete Ablehnungen werden dann gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="1184e-152">Unexpected rejections will then be flagged.</span></span> <span data-ttu-id="1184e-153">Dies kann hilfreich sein, wenn Sie eine unvollständige oder eine untergeordnete Bibliothek analysieren, bei der einige Abhängigkeiten fehlen.</span><span class="sxs-lookup"><span data-stu-id="1184e-153">This can be useful when you analyze an incomplete library, or a sub-library that is missing some dependencies.</span></span> <span data-ttu-id="1184e-154">Die `/whitelist` -Option kann mit der `/rejected` -Aktion oder der `/causes` -Aktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1184e-154">The `/whitelist` option can be applied to the `/rejected` or `/causes` actions.</span></span>  
  
 <span data-ttu-id="1184e-155">Angenommen, die Datei test.txt enthält den Text "ClassLibrary1.ChainOne".</span><span class="sxs-lookup"><span data-stu-id="1184e-155">Consider a file named test.txt that contains the text "ClassLibrary1.ChainOne".</span></span> <span data-ttu-id="1184e-156">Wenn Sie die `/rejected` -Aktion mit der `/whitelist` -Option im vorherigen Beispiel ausführen, wird folgende Ausgabe erzeugt:</span><span class="sxs-lookup"><span data-stu-id="1184e-156">If you run the `/rejected` action with the `/whitelist` option on the previous example, it will produce the following output:</span></span>  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
