---
title: Interaktive Optionen
description: Erfahren Sie mehr über die von F# Interactive unterstützten Befehlszeilenoptionen fsi.exe.
ms.date: 07/22/2020
ms.openlocfilehash: f9932cac24fad187c332306968fb13981912e80a
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795462"
---
# <a name="f-interactive-options"></a>F# Interactive Optionen

In diesem Artikel werden die von F# Interactive unterstützten Befehlszeilenoptionen beschrieben `fsi.exe` . F# Interactive akzeptiert viele Befehlszeilenoptionen des F#-Compilers, jedoch auch einige zusätzliche Optionen.

## <a name="use-f-interactive-for-scripting"></a>Verwenden von F# Interactive für die Skripterstellung

F# Interactive, `dotnet fsi` , kann interaktiv gestartet werden, oder es kann über die Befehlszeile gestartet werden, um ein Skript auszuführen. Die Befehlszeilensyntax lautet wie folgt:

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

Die Dateierweiterung für F#-Skriptdateien lautet `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabelle der F# Interactive-Optionen

In der folgenden Tabelle werden die von F# Interactive unterstützten Optionen zusammengefasst. Sie können diese Optionen an der Befehlszeile oder in der Visual Studio-IDE festlegen. Um diese Optionen in der Visual Studio-IDE festzulegen, öffnen Sie das Menü Extras, wählen Sie **Optionen**aus, erweitern Sie **dann den Knoten** **F #-Tools** , und wählen Sie **F# Interactive**aus.

Wenn F# Interactive-Optionsargumente Listen enthalten, werden Listenelemente durch Semikolons (`;`) getrennt.

|Option|BESCHREIBUNG|
|------|-----------|
|**--**|Wird verwendet, um F# Interactive anzuweisen, verbleibende Argumente als Befehlszeilenargumente für das F #-Programm oder-Skript zu behandeln, auf das Sie in Code mithilfe der List **FSI. CommandLineArgs**zugreifen können.|
|**--aktiviert**[ **+**&#124;**-** ]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Codepage: &lt; int&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--consolecolors**[ **+**&#124;**-** ]|Gibt Warn-und Fehlermeldungen in Farbe aus.|
|**--crossoptimiert**[ **+**&#124;**-** ]|Aktiviert oder deaktiviert modulübergreifende Optimierungen.|
|**--Debug**[ **+**&#124;**-** ]<br /><br />**--Debug:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]<br /><br />**-g**[ **+**&#124;**-** ]<br /><br />**-g:**[**Full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--define: &lt; Zeichenfolge&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--deterministisch**[ **+**&#124;**-** ]|Erzeugt eine deterministische Assembly (einschließlich Modul Versions-GUID und Timestamp).|
|**--Exec**|Weist das Beenden von F# Interactive an, nachdem die Dateien geladen wurden oder die in der Befehlszeile angegebene Skriptdatei ausgeführt wurde.|
|**--FullPath**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--GUI**[ **+**&#124;**-** ]|Aktiviert oder deaktiviert die Windows Forms-Ereignisschleife. Die Standardeinstellung ist aktiviert.|
|**--Hilfe**<br /><br />**-?**|Wird verwendet, um die Befehlszeilensyntax und eine kurze Beschreibung jeder Option anzuzeigen.|
|**--lib: &lt; Ordner-List&gt;**<br /><br />**-I: &lt; Ordnerliste&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Load: &lt; Dateiname&gt;**|Kompiliert beim Start den angegebenen Quellcode und lädt die kompilierten F#-Konstrukte in die Sitzung. Wenn die Ziel Quelle Skript Direktiven wie **#use** oder **#Load**enthält, müssen Sie **--use** oder **#use** anstelle von **--Load** oder **#Load**verwenden.|
|**--mlcompatibility**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--noframework**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md) .|
|**--nologo**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--nowarn: &lt; Warning-List&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--optimieren**[ **+**&#124;**-** ]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--preferreduilang: &lt; lang&gt;**| Gibt den bevorzugten Kultur Namen der Ausgabesprache an (z. b. "es-es", "ja-JP"). |
|**--Quiet**|Unterdrücken der F# Interactive Ausgabe in den **stdout** -Datenstrom.|
|**--Zitate-Debuggen**|Gibt an, dass zusätzliche Debuginformationen für Ausdrücke ausgegeben werden, die von F#-Quotation-Literalen und reflektierten Definitionen abgeleitet werden. Die Debuginformationen werden zu den benutzerdefinierten Attributen eines F#-Ausdrucksstrukturknotens hinzugefügt. Weitere Informationen finden Sie unter [Code Notierungen](code-quotations.md) und [expr. CustomAttribute](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--Read Line**[ **+**&#124;**-** ]|Aktiviert oder deaktiviert die Vervollständigung mit der TAB-TASTE im interaktiven Modus.|
|**--Reference: &lt; Dateiname&gt;**<br /><br />**-r: &lt; Dateiname&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--tailcalls**[ **+**&#124;**-** ]|Aktiviert oder deaktiviert die Verwendung der Tail-IL-Anweisung, die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens verursacht. Diese Option ist standardmäßig aktiviert.|
|**--targetprofile: &lt; Zeichenfolge&gt;**|Gibt das zielframeworkprofil dieser Assembly an. Gültige Werte sind "mscorlib", "Netcore" oder "netstandard".  Der Standardwert ist mscorlib.|
|**--use: &lt; filename&gt;**|Weist den Interpreter an, beim Start die angegebene Datei als anfängliche Eingabe zu verwenden.|
|**--utf8output**|Identisch mit der fsc.exe-Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--Warn: &lt; Warnstufe&gt;**|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[ **+**&#124;**-** ]|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|
|**--warnaserror**[ **+**&#124;**-** ]:** &lt; int-List &gt; **|Identisch mit der **fsc.exe** -Compileroption. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).|

## <a name="f-interactive-structured-printing"></a>F# Interactive strukturierter Druck

F# Interactive ( `dotnet fsi` ) verwendet eine erweiterte Version der [strukturierten Klartext-Formatierung](plaintext-formatting.md) , um Werte zu melden.

1. Alle Funktionen der nur `%A` -Text-Formatierung werden unterstützt, und einige sind zusätzlich anpassbar.

2. Das Drucken wird eingefärbt, wenn Farben von der Ausgabe Konsole unterstützt werden.

3. Es wird ein Grenzwert für die Länge der angezeigten Zeichen folgen festgelegt, es sei denn, Sie bewerten diese Zeichenfolge explizit.

4. Ein Satz von benutzerdefinierbaren Einstellungen ist über das- `fsi` Objekt verfügbar.

Die verfügbaren Einstellungen zum Anpassen des Klartext-Druckens für gemeldete Werte lauten:

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

### <a name="customize-with-addprinter-and-addprinttransformer"></a>Anpassen mit `AddPrinter` und`AddPrintTransformer`

Das Drucken in F# Interactive Ausgaben kann mithilfe von und angepasst werden `fsi.AddPrinter` `fsi.AddPrintTransformer` .
Die erste Funktion gibt Text an, um das Drucken eines Objekts zu ersetzen. Die zweite Funktion gibt ein Ersatzobjekt zurück, das stattdessen angezeigt werden soll. Sehen Sie sich beispielsweise den folgenden F #-Code an:

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

Wenn Sie das Beispiel in F# Interactive ausführen, wird es basierend auf der Formatierungs Options Menge ausgegeben. In diesem Fall hat dies Auswirkungen auf die Formatierung von Datum und Uhrzeit:

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

`fsi.AddPrintTransformer`kann verwendet werden, um ein Ersatzobjekt zum Drucken zu geben:

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

Diese Ausgabe:

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

Wenn die an übertraene Transformer-Funktion `fsi.AddPrintTransformer` zurückgegeben `null` wird, wird der Druck Transformator ignoriert.
Dies kann verwendet werden, um beliebige Eingabewerte zu filtern, indem Sie mit dem Typ beginnen `obj` .  Beispiel:

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

Diese Ausgabe:

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a>Verwandte Themen

|Titel|BESCHREIBUNG|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die Befehlszeilenoptionen, die für den F #-Compiler verfügbar sind, **fsc.exe**.|
