---
title: F# Interactive-Optionen
description: Erfahren Sie mehr über die Befehlszeilenoptionen, die von unterstützt F# interaktiv fsi.exe.
ms.date: 05/16/2016
ms.openlocfilehash: cca1ef6671878acb1b837d6590139d5de7b7167d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128153"
---
# <a name="f-interactive-options"></a>F# Interactive-Optionen

> [!NOTE]
> Dieser Artikel beschreibt derzeit nur das Erlebnis für Windows.  Er wird neu geschrieben.

In diesem Thema werden die von F# Interactive (`fsi.exe`) unterstützten Befehlszeilenoptionen beschrieben. F# Interactive akzeptiert viele Befehlszeilenoptionen des F#-Compilers, jedoch auch einige zusätzliche Optionen.

## <a name="using-f-interactive-for-scripting"></a>Verwenden von F# Interactive für die Skripterstellung
F#Interaktive `fsi.exe`, interaktiv gestartet werden oder über die Befehlszeile zum Ausführen eines Skripts gestartet werden. Die Befehlszeilensyntax lautet wie folgt:

```
> fsi.exe [options] [ script-file [arguments] ]
```

Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabelle der F# Interactive-Optionen
In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst. Sie können diese Optionen an der Befehlszeile oder in der Visual Studio-IDE festlegen. Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen die **Tools** , wählen Sie im Menü **Optionen...** , erweitern Sie dann die  **F# Tools** Knoten, und wählen  **F# interaktiv**.

Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.

|Option|Beschreibung|
|------|-----------|
|**--**|Verwendet, um anzuweisen F# Interactive, um die übrigen Argumente als Befehlszeilenargumente zum Behandeln der F# Programms oder Skripts, die Sie im Code zugreifen können, indem die Liste **fsi.CommandLineArgs**.|
|**– aktiviert**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Codepage:&lt;Int&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Consolecolors**[**+**&#124;**-**]|Warnung Ausgaben und Fehlermeldungen in der Farbe.|
|**--crossoptimize**[**+**&#124;**-**]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**--debug**[**+**&#124;**-**]<br /><br />**--debug:**[**vollständige**&#124;**"pdbonly"**&#124;**portable**&#124;**eingebettete**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--define:&lt;string&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Erstellt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).|
|**--exec**|Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.|
|**--fullpaths**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife. Die Option ist standardmäßig aktiviert.|
|**--help**<br /><br />**-?**|Wird verwendet, um die Befehlszeilensyntax und eine kurze Beschreibung jeder Option anzuzeigen.|
|**--Lib:&lt;Ordnerliste&gt;**<br /><br />**-I:&lt;Ordnerliste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**– Laden:&lt;Dateiname&gt;**|Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung. Wenn der Zielquellcode skriptanweisungen, z. B. enthält **#use** oder **#load**, müssen Sie verwenden **– verwenden Sie** oder **#use** statt **--laden** oder **#load**.|
|**--mlcompatibility**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--noframework**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md)|
|**--nologo**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**-Nowarn:&lt;Liste der Warnungen&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**– Optimieren**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Gibt die Namen der bevorzugten ausgabesprache Kultur an (z. B. "es-ES", "ja-JP"). |
|**--quiet**|Unterdrücken F# interaktiv die Ausgabe, um die **"stdout"** Stream.|
|**--quotations-debug**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksbaumstrukturknotens hinzugefügt. Finden Sie unter [Codezitate](code-quotations.md) und [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.|
|**– Referenz:&lt;Dateiname&gt;**<br /><br />**-r:&lt;Dateiname&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--shadowcopyreferences**[**+**&#124;**-**]|Verhindern, dass Verweise von gesperrt werden, indem die F# interaktiven Prozess.|
|**--simpleresolution**|Löst Assemblyverweisen mithilfe der Verzeichnis-basierte Regeln anstelle von MSBuild-Auflösung an.|
|**--Tailcalls**[**+**&#124;**-**]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht. Diese Option ist standardmäßig aktiviert.|
|**--"targetprofile":&lt;Zeichenfolge&gt;**|Gibt das Zielframeworkprofil dieser Assembly an. Gültige Werte sind "mscorlib" ",".NET Core "oder" Netstandard.  Der Standardwert ist "mscorlib".|
|**– Verwenden Sie:&lt;Dateiname&gt;**|Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.|
|**--utf8output**|Identisch mit der fsc.exe-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Warnen:&lt;Warnstufe&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**-Warnaserror**[**+**&#124;**-**]:**&lt;Int-Liste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die Befehlszeilenoptionen für die F# Compiler **fsc.exe**.|
