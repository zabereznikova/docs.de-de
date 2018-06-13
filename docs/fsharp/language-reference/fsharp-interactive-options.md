---
title: F# Interactive-Optionen
description: Erfahren Sie mehr über die Befehlszeilenoptionen, die von f# Interactive unterstützten fsi.exe.
ms.date: 05/16/2016
ms.openlocfilehash: a461dd0eeff2de3d15e557ba37138fbd62ca43ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565804"
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
|**--überprüft**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Codepage:&lt;Int&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Consolecolors**[**+**&#124;**-**]|Ausgaben Warnung und Fehlermeldungen in Farbe.|
|**--crossoptimize**[**+**&#124;**-**]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**--debug**[**+**&#124;**-**]<br /><br />**--Debuggen:**[**vollständige**&#124;**"pdbonly"**&#124;**portable**&#124;**eingebettete**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--define:&lt;string&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Erzeugt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).|
|**--exec**|Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.|
|**--fullpaths**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife. Die Option ist standardmäßig aktiviert.|
|**--help**<br /><br />**-?**|Wird verwendet, um die Befehlszeilensyntax und eine kurze Beschreibung jeder Option anzuzeigen.|
|**--Lib:&lt;Ordnerliste&gt;**<br /><br />**-I:&lt;Ordnerliste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Laden:&lt;Dateiname&gt;**|Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung. Wenn der Zielquellcode skriptanweisungen, z. B. enthält **#use** oder **#load**, müssen Sie verwenden **--verwenden Sie** oder **#use** statt **– laden** oder **#load**.|
|**--mlcompatibility**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--noframework**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [(Compileroptionen)](compiler-options.md)|
|**--nologo**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Nowarn:&lt;Warnung-Liste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**– Optimieren**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Gibt die bevorzugte Sprache Kultur Ausgabename (z. B. es-ES, ja-JP) an. |
|**--Stille**|Unterdrückt die Ausgabe von f# Interactive an den **"stdout"** Stream.|
|**--quotations-debug**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksbaumstrukturknotens hinzugefügt. Finden Sie unter [Codezitate](code-quotations.md) und [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.|
|**– Referenz:&lt;Dateiname&gt;**<br /><br />**-r:&lt;Dateiname&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--shadowcopyreferences**[**+**&#124;**-**]|Verhindert, dass Verweise, die durch den f# Interactive-Prozess gesperrt wird.|
|**--simpleresolution**|Löst Assemblyverweise mit verzeichnisbasierten Regeln nicht mit MSBuild-Auflösung an.|
|**--Tailcalls**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht. Diese Option ist standardmäßig aktiviert.|
|**--Targetprofile:&lt;Zeichenfolge&gt;**|Gibt das Zielframeworkprofil dieser Assembly an. Gültige Werte sind "mscorlib", Netcore oder netstandard-.  Der Standardwert ist "mscorlib".|
|**– Verwenden Sie:&lt;Dateiname&gt;**|Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.|
|**--utf8output**|Identisch mit der fsc.exe-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**– Warnung:&lt;Warnstufe&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Warnaserror**[**+**&#124;**-**]:**&lt;Int-Liste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die Befehlszeilenoptionen für den f#-Compiler verfügbar **fsc.exe**.|
