---
title: Kompositionsanalysetool (Mefx)
description: In diesem Artikel erhalten Sie Informationen zum Kompositionsanalysetool (Mefx), das DLL- und EXE-Dateien analysiert, die Managed Extensibility Framework-Teile (MEF) in .NET enthalten.
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: d3f3a282cfa9274a1939d312987dd58b24eab2af
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255792"
---
# <a name="composition-analysis-tool-mefx"></a>Kompositionsanalysetool (Mefx)

Das Kompositionsanalysetool MEFX ist eine Befehlszeilenanwendung, die Bibliotheks- (.dll) und Anwendungsdateien (.exe) mit Teilen des Managed Extensibility Framework (MEF) analysiert. MEFX dient in erster Linie dazu, Entwicklern eine Möglichkeit zur Diagnose von Kompositionsfehlern in MEF-Anwendungen zu bieten, ohne dass der Anwendung selbst unübersichtlicher Ablaufverfolgungscode hinzugefügt werden muss. Darüber hinaus kann das Tool nützlich sein, um Teile einer Bibliothek zu verstehen, die von einem Drittanbieter bereitgestellt wird. In diesem Thema wird beschrieben, wie MEFX verwendet wird, und ein Verweis auf die Syntax wird bereitgestellt.  
  
<a name="getting_mefx"></a>

## <a name="getting-mefx"></a>Abrufen von MEFX  

 MEFX steht auf GitHub unter [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0) zur Verfügung. Nach dem Herunterladen müssen Sie das Tool nur noch entpacken.  
  
<a name="basic_syntax"></a>

## <a name="basic-syntax"></a>Allgemeine Syntax  

 MEFX kann wie folgt über die Befehlszeile aufgerufen werden:  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 Im ersten Satz von Argumenten werden die Dateien und Verzeichnisse angegeben, aus denen Teile für die Analyse geladen werden. Dateien können mit dem Schalter `/file:` und Verzeichnisse mit dem Schalter `/directory:` angegeben werden. Sie können mehrere Dateien oder Verzeichnisse angeben, wie im folgenden Beispiel veranschaulicht:  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> Jede DLL- oder EXE-Datei sollte nur einmal geladen werden. Wenn eine Datei mehrmals geladen wird, gibt das Tool möglicherweise falsche Informationen zurück.  
  
 Nach der Liste der Dateien und Verzeichnisse müssen Sie einen Befehl sowie alle Optionen für den Befehl angeben.  
  
<a name="listing_available_parts"></a>

## <a name="listing-available-parts"></a>Auflisten verfügbarer Teile  

 Mit der Aktion `/parts` können Sie alle deklarierten Teile in den geladenen Dateien auflisten. Das Ergebnis ist eine einfache Liste mit den Namen der Teile.  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 Mit der Option `/verbose` können Sie weitere Informationen über Teile abrufen. Dadurch erhalten Sie weitere Angaben zu allen verfügbaren Teilen. Um weitere Informationen über ein einzelnes Teil abzurufen, verwenden Sie die Aktion `/type` anstelle von `/parts`.  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>

## <a name="listing-imports-and-exports"></a>Auflisten von Importen und Exporten  

 Mit der Aktion `/imports` und der Aktion `/exports` werden alle importierten Teile und alle exportierten Teile aufgeführt. Sie können auch die Teile auflisten, mit denen ein bestimmter Typ importiert oder exportiert wird, indem Sie die `/importers` - oder die `/exporters` -Aktionen verwenden.  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 Sie können auch die `/verbose` -Option für diese Aktionen verwenden.  
  
<a name="finding_rejected_parts"></a>

## <a name="finding-rejected-parts"></a>Suchen abgelehnter Teile  

 Sobald die verfügbaren Teile geladen wurden, werden diese von MEFX mit der MEF-Kompositions-Engine erstellt. Die Teile, die nicht erfolgreich erstellt werden können, werden als *abgelehnt* bezeichnet. Mit der `/rejected` -Aktion können Sie alle abgelehnten Teile auflisten.  
  
 Mit der `/verbose` -Option und der `/rejected` -Aktion können Sie detaillierte Informationen über abgelehnte Teile ausgeben. Die DLL-Datei `ClassLibrary1` im folgenden Beispiel enthält das Teil `AddIn` , mit dem das Teil `MemberPart` und das Teil `ChainOne` importiert werden. `ChainOne` importiert `ChainTwo`, `ChainTwo` ist jedoch nicht vorhanden. Dies bedeutet, dass `ChainOne` abgelehnt wird, wodurch `AddIn` abgelehnt wird.  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 Im Folgenden wird die gesamte Ausgabe des vorherigen Befehls veranschaulicht:  
  
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
  
 Die interessanten Ergebnisse sind in `[Exception]` und `[Unsuitable]` enthalten. Das Ergebnis `[Exception]` enthält Informationen dazu, warum ein Teil abgelehnt wurde. Das `[Unsuitable]` -Ergebnis gibt an, warum ein Teil, das andernfalls geeignet gewesen wäre, nicht zum Ausfüllen eines Imports verwendet werden konnte. Im vorliegenden Fall wurde das Teil selbst aufgrund fehlender Importe abgelehnt.  
  
<a name="analyzing_primary_causes"></a>

## <a name="analyzing-primary-causes"></a>Analysieren primärer Ursachen  

 Bei mehreren verknüpften Teilen in einer langen Abhängigkeitskette kann ein Problem mit einem Teil im unteren Bereich zu einer Ablehnung der gesamten Kette führen. Diese Probleme können sich als schwerwiegend erweisen, da die Ursache des Fehlers nicht immer offensichtlich ist. Um eine Lösung für das Problem zu finden, können Sie die `/causes` -Aktion verwenden. Diese Aktion zielt darauf ab, die Ursache einer kaskadierenden Ablehnung zu finden.  
  
 Wenn Sie die `/causes` -Aktion im vorangehenden Beispiel verwenden, werden nur Informationen für `ChainOne`aufgeführt. Der nicht ausgefüllte Import ist in diesem Fall die Ursache für die Ablehnung von `AddIn`. Die `/causes` -Aktion kann bei normalen und `/verbose` -Optionen verwendet werden.  
  
> [!NOTE]
> In den meisten Fällen können Sie mithilfe von MEFX die Ursache eines kaskadierenden Fehlers aufspüren. Wenn die Teile einem Container jedoch programmgesteuert hinzugefügt werden, wenn hierarchische Container verwendet werden oder wenn benutzerdefinierte `ExportProvider` -Implementierungen enthalten sind, kann die Ursache nicht mit MEFX ermittelt werden. Die vorstehend beschriebenen Fälle sollten nach Möglichkeit vermieden werden, da hier eine Fehlerdiagnose nur sehr schwer möglich ist.  
  
<a name="white_lists"></a>

## <a name="white-lists"></a>Whitelisten  

 Mit der `/whitelist` -Option können Sie eine Textdatei mit den Teilen angeben, die wahrscheinlich abgelehnt werden. Unerwartete Ablehnungen werden dann gekennzeichnet. Dies kann hilfreich sein, wenn Sie eine unvollständige oder eine untergeordnete Bibliothek analysieren, bei der einige Abhängigkeiten fehlen. Die `/whitelist` -Option kann mit der `/rejected` -Aktion oder der `/causes` -Aktion verwendet werden.  
  
 Angenommen, die Datei test.txt enthält den Text "ClassLibrary1.ChainOne". Wenn Sie die `/rejected` -Aktion mit der `/whitelist` -Option im vorherigen Beispiel ausführen, wird folgende Ausgabe erzeugt:  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
