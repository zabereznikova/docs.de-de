---
title: F# Interactive-Optionen
description: "Erfahren Sie mehr über die Befehlszeilenoptionen, die von f# Interactive unterstützten fsi.exe."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9f3e39b-ce6c-41ff-991f-0625f46441ae
ms.openlocfilehash: a9b36a12aa9ffcfa26ea50d72d018a25f5f65243
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="f-interactive-options"></a>F# Interactive-Optionen

> [!NOTE]
Dieser Artikel beschreibt derzeit nur das Erlebnis für Windows.  Er wird neu geschrieben.

In diesem Thema werden die von F# Interactive (`fsi.exe`) unterstützten Befehlszeilenoptionen beschrieben. F# Interactive akzeptiert viele Befehlszeilenoptionen des F#-Compilers, jedoch auch einige zusätzliche Optionen.

## <a name="using-f-interactive-for-scripting"></a>Verwenden von F# Interactive für die Skripterstellung
F# Interactive, `fsi.exe`, interaktiv gestartet werden kann oder über die Befehlszeile zum Ausführen eines Skripts gestartet werden. Die Befehlszeilensyntax lautet wie folgt:

```
> fsi.exe [options] [ script-file [arguments] ]
```

Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabelle der F# Interactive-Optionen
In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst. Sie können diese Optionen an der Befehlszeile oder in der Visual Studio-IDE festlegen. Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen Sie die **Tools** klicken Sie im Menü **Optionen...** , erweitern Sie dann die **f#-Tools** Knoten, und wählen **f# Interactive**.

Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.

|Option|Beschreibung|
|------|-----------|
|**--**|Verwendet, um f# Interactive anzuweisen zu behandeln, restliche Argumente als Befehlszeilenargumente des F#-Programms oder Skripts, die Sie im Code zugreifen können, mithilfe der Liste **fsi.CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--Codepage:&lt;Int&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--crossoptimize**[**+**&#124;**-**]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**--debug**[**+**&#124;**-**]<br /><br />**--debug:**[**full**&#124;**pdbonly**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--definieren:&lt;Zeichenfolge&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--exec**|Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.|
|**--fullpaths**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife. Die Option ist standardmäßig aktiviert.|
|**--help**<br /><br />**-?**|Wird verwendet, um die Befehlszeilensyntax und eine kurze Beschreibung jeder Option anzuzeigen.|
|**--Lib:&lt;Ordnerliste&gt;**<br /><br />**-I:&lt;folder-list&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--Laden:&lt;Dateiname&gt;**|Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung. Wenn der Zielquellcode skriptanweisungen, z. B. enthält **#use** oder **#load**, müssen Sie verwenden **--verwenden Sie** oder **#use** statt **– laden** oder **#load**.|
|**--mlcompatibility**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--noframework**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [(Compileroptionen)](../../language-reference/compiler-options.md)|
|**--nologo**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--Nowarn:&lt;Warnung-Liste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--optimize**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--quiet**|Unterdrückt die Ausgabe von f# Interactive an den **"stdout"** Stream.|
|**--quotations-debug**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksbaumstrukturknotens hinzugefügt. Finden Sie unter [Codezitate](../../language-reference/code-quotations.md) und [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.|
|**– Referenz:&lt;Dateiname&gt;**<br /><br />**-r:&lt;Dateiname&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--tailcalls**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht. Diese Option ist standardmäßig aktiviert.|
|**– Verwenden Sie:&lt;Dateiname&gt;**|Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.|
|**--utf8output**|Identisch mit der fsc.exe-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**– Warnung:&lt;Warnstufe&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](../../language-reference/compiler-options.md).|

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[Compileroptionen](../../language-reference/compiler-options.md)|Beschreibt die Befehlszeilenoptionen für den f#-Compiler verfügbar **fsc.exe**.|
