---
title: F# Interactive-Optionen
description: Erfahren Sie mehr über die Befehlszeilenoptionen, F# die von Interactive, fsi. exe unterstützt werden.
ms.date: 05/16/2016
ms.openlocfilehash: e4ce0f3f76a7be803942e4b403e5fa6543a09e54
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425319"
---
# <a name="f-interactive-options"></a>F# Interactive-Optionen

> [!NOTE]
> Dieser Artikel beschreibt derzeit nur das Erlebnis für Windows.  Er wird neu geschrieben.

In diesem Thema werden die von F# Interactive (`fsi.exe`) unterstützten Befehlszeilenoptionen beschrieben. F# Interactive akzeptiert viele Befehlszeilenoptionen des F#-Compilers, jedoch auch einige zusätzliche Optionen.

## <a name="using-f-interactive-for-scripting"></a>Verwenden von F# Interactive für die Skripterstellung

F#Interaktiv, `fsi.exe`, kann interaktiv gestartet werden, oder es kann über die Befehlszeile gestartet werden, um ein Skript auszuführen. Die Befehlszeilensyntax lautet wie folgt:

```console
> fsi.exe [options] [ script-file [arguments] ]
```

Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabelle der F# Interactive-Optionen

In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst. Sie können diese Optionen an der Befehlszeile oder in der Visual Studio-IDE festlegen. Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen Sie **das Menü Extras** , wählen Sie **Optionen**aus, erweitern Sie dann den  **F# Knoten Tools** , und wählen Sie  **F# Interactive**aus.

Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.

|Option|Beschreibung|
|------|-----------|
|**--**|Wird verwendet, F# um Interactive anzuweisen, verbleibende Argumente als Befehlszeilen F# Argumente für das Programm oder Skript zu behandeln, auf das Sie in Code mithilfe der Liste **FSI. CommandLineArgs**zugreifen können.|
|**--aktiviert**[ **+** &#124; **-** ]|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Codepage:&lt;int&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--consolecolors**[ **+** &#124; **-** ]|Gibt Warn-und Fehlermeldungen in Farbe aus.|
|**--crossoptimiert**[ **+** &#124; **-** ]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**--Debug**[ **+** &#124; **-** ]<br /><br />**--Debug:** [**vollständiges**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]<br /><br />**-g**[ **+** &#124; **-** ]<br /><br />**-g:** [**vollständiges**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--define:&lt;Zeichenfolge&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--deterministisch**[ **+** &#124; **-** ]|Erzeugt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).|
|**--Exec**|Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.|
|**--FullPath**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--GUI**[ **+** &#124; **-** ]|Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife. Die Option ist standardmäßig aktiviert.|
|**--Hilfe**<br /><br />**-?**|Wird verwendet, um die Befehlszeilensyntax und eine kurze Beschreibung jeder Option anzuzeigen.|
|**--lib:&lt;Ordner-List&gt;**<br /><br />**-I:&lt;Ordnerliste&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Load:&lt;filename&gt;**|Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung. Wenn die Ziel Quelle Skript Direktiven wie **#use** oder **#Load**enthält, müssen Sie **--use** oder **#use** anstelle von **--Load** oder **#Load**verwenden.|
|**--mlcompatibility**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--noframework**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md) .|
|**--nologo**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--nowarn:&lt;Warning-List&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--optimieren**[ **+** &#124; **-** ]|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Gibt den bevorzugten Kultur Namen der Ausgabesprache an (z. b. "es-es", "ja-JP"). |
|**--Quiet**|Unter F# Drücken der interaktiven Ausgabe in den **stdout** -Datenstrom.|
|**--Zitate-Debuggen**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksstrukturknotens hinzugefügt. Weitere Informationen finden Sie unter [Code Notierungen](code-quotations.md) und [expr. CustomAttribute](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--Read Line**[ **+** &#124; **-** ]|Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.|
|**--Reference:&lt;Dateiname&gt;**<br /><br />**-r:&lt;Dateiname&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--shadowcopyreferences**[ **+** &#124; **-** ]|Verhindert, dass Verweise durch den F# interaktiven Prozess gesperrt werden.|
|**--simpleresolution**|Löst Assemblyverweise mithilfe von Verzeichnis basierten Regeln anstelle der MSBuild-Auflösung auf.|
|**--tailcalls**[ **+** &#124; **-** ]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht. Diese Option ist standardmäßig aktiviert.|
|**--targetprofile:&lt;Zeichenfolge&gt;**|Gibt das zielframeworkprofil dieser Assembly an. Gültige Werte sind "mscorlib", "Netcore" oder "netstandard".  Der Standardwert ist mscorlib.|
|**--use:&lt;filename&gt;**|Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.|
|**--utf8output**|Identisch mit der fsc.exe-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Warn:&lt;Warnstufe&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]: **&lt;int-List&gt;**|Identisch mit der " **FSC. exe** "-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die verfügbaren Befehlszeilenoptionen F# für den Compiler " **FSC. exe**".|
