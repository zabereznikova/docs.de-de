---
title: Referenz zu F# Interactive (dotnet)
description: Hier erfahren Sie, wie F# Interactive (dotnet fsi) zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts verwendet wird.
ms.date: 11/29/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 71ec5d1b050b02ecbdb98adce814fce011cdbca0
ms.sourcegitcommit: c6de55556add9f92af17e0f8d1da8f356a19a03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96549396"
---
# <a name="interactive-programming-with-f"></a>Interaktive Programmierung mit F\#

F# Interactive (dotnet fsi) dient zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts. Dies bedeutet, dass F# Interactive eine REPL (Read, Evaluate, Print Loop = Lesen-Auswerten-Drucken-Schleife) für F# ausführt.

Führen Sie `dotnet fsi` aus, um F# Interactive in der Konsole auszuführen. Sie finden `dotnet fsi` in einem beliebigen .NET SDK.

Informationen zu verfügbaren Befehlszeilenoptionen finden Sie unter [F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md).

## <a name="executing-code-directly-in-f-interactive"></a>Direktes Ausführen von Code in F# Interactive

Da F# Interactive eine REPL (read-eval-print-Loop) ist, können Sie Code interaktiv in dieser Loop ausführen. Nachfolgend finden Sie ein Beispiel für eine interaktive Sitzung, nachdem `dotnet fsi` über die Befehlszeile ausgeführt wurde:

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

Beachten Sie zwei wichtige Aspekte:

1. Der gesamte Code muss zur Auswertung mit einem doppelten Semikolon (`;;`) beendet werden.
2. Der Code wird ausgewertet und in einem `it`-Wert gespeichert. Sie können interaktiv auf `it` verweisen.

F# Interactive unterstützt zudem mehrzeilige Eingaben. Sie müssen Ihre Eingaben lediglich mit einem doppelten Semikolon (`;;`) beenden. Sehen Sie sich den folgenden Ausschnitt an, der in F# Interactive eingefügt und ausgewertet wurde:

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

Die Formatierung des Codes wird beibehalten, und die Eingabe wird durch ein doppeltes Semikolon (`;;`) beendet. Anschließend wurde der Code von F# Interactive ausgewertet, und die Ergebnisse wurden ausgegeben.

## <a name="scripting-with-f"></a>Skripterstellung mit F\#

Die interaktive Auswertung von Code in F# Interactive ist eine hervorragende Lernmethode. Sie werden jedoch rasch feststellen, dass diese Vorgehensweise weniger produktiv ist als das Schreiben von Code in einem normalen Editor. Um die reguläre Codebearbeitung zu unterstützen, können Sie F#-Skripts schreiben.

Für Skripts wird die Dateierweiterung **.fsx** verwendet. Statt Quellcode zu kompilieren und später die kompilierte Assembly auszuführen, können Sie einfach **dotnet fsi** ausführen und den Dateinamen des Skripts mit dem F#-Quellcode angeben. F# Interactive liest dann den Code und führt ihn in Echtzeit aus. Sehen wir uns z. B. das folgende Skript `Script.fsx` an:

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

printfn "%A" (getOddSquares [1..10])
```

Wenn diese Datei auf Ihrem Computer erstellt wird, können Sie sie mit `dotnet fsi` ausführen. Die Ausgabe wird unmittelbar in Ihrem Terminalfenster angezeigt:

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

Das Erstellen von F#-Skripts wird nativ in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) und [Visual Studio für Mac](../../get-started/get-started-with-visual-studio-for-mac.md) unterstützt.

## <a name="referencing-packages-in-f-interactive"></a>Verweisen auf Pakete in F# Interactive

> [!NOTE]
> Das Paketverwaltungssystem ist erweiterbar. Lesen Sie mehr [über andere Erweiterungen](https://github.com/dotnet/fsharp/tree/main/src/fsharp/Microsoft.DotNet.DependencyManager).

F# Interactive unterstützt Verweise auf NuGet-Pakete mit der `#r "nuget:"`-Syntax und einer optionalen Version:

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

Wenn keine Version angegeben wird, wird das höchste verfügbare Paket verwendet, bei dem es sich nicht um eine Vorschauversion handelt. Um auf eine bestimmte Version zu verweisen, fügen Sie die Version mit Komma ein. Dies kann nützlich sein, um auf eine Vorschauversion eines Pakets zu verweisen. Sehen Sie sich z. B. das folgende Skript an, bei dem eine Vorschauversion von [DiffSharp](https://diffsharp.github.io/) verwendet wird:

```fsharp
#r "nuget: DiffSharp-lite, 1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

### <a name="specifying-a-package-source"></a>Angeben einer Paketquelle

Sie können eine Paketquelle auch mit dem `#i`-Befehl angeben. Im folgenden Beispiel wird eine Remotequelle und eine lokale Quelle angegeben:

```fsharp
#i "nuget:https://my-remote-package-source/index.json
#i @"path-to-my-local-source"
```

Dadurch wird die Auflösungs-Engine unter der Haube ebenfalls dazu angeleitet, die Remotequellen und/oder lokalen Quellen miteinzubeziehen, die einem Skript hinzugefügt wurden.

Sie können beliebig viele Paketverweise in einem Skript angeben.

> [!NOTE]
> Es gibt zurzeit eine Einschränkung für Skripts, die Frameworkverweise verwenden (z. B. `Microsoft.NET.Sdk.Web` oder `Microsoft.NET.Sdk.WindowsDesktop`). Pakete wie Saturn, Giraffe und WinForms sind nicht verfügbar. Dies wird in Issue [#9417](https://github.com/dotnet/fsharp/issues/9417) nachverfolgt.

Erfahren Sie mehr über die [Paketverwaltungserweiterbarkeit und andere Erweiterungen](https://github.com/dotnet/fsharp/tree/main/src/fsharp/Microsoft.DotNet.DependencyManager).

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a>Verweisen auf Assemblys auf einem Datenträger mit F# Interactive

Wenn Sie über eine Assembly auf einem Datenträger verfügen und in einem Skript auf diese Assembly verweisen möchten, können Sie sie mit der `#r`-Syntax angeben. Gehen wir von folgendem Code in einem Projekt aus, der in `MyAssembly.dll` kompiliert wird:

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

Nach der Kompilierung können Sie in einer Datei `Script.fsx` wie folgt darauf verweisen:

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

Die Ausgabe lautet wie folgt:

```console
dotnet fsi Script.fsx
90
```

Sie können beliebig viele Assemblyverweise in einem Skript angeben.

## <a name="loading-other-scripts"></a>Laden anderer Skripts

Bei der Skripterstellung ist es häufig nützlich, unterschiedliche Skripts für unterschiedliche Aufgaben zu verwenden. In einigen Fällen bietet es sich an, Code aus einem Skript in einem anderen Skript wiederzuverwenden. Anstatt die Skriptinhalte zu kopieren und in Ihrer Datei einzufügen, können Sie sie ganz einfach mit `#load` laden und auswerten.

Angenommen, Sie verfügen über die Datei `Script1.fsx`:

```fsharp
let square x = x * x
```

Außerdem über die verbrauchende Datei `Script2.fsx`:

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

Beachten Sie, dass die Deklaration `open Script1` erforderlich ist. Der Grund dafür ist, dass Konstrukte in einem F#-Skript in einem Modul der obersten Ebene kompiliert werden, das dem Namen der Skriptdatei entspricht, in dem es sich befindet.

Sie können `Script2.fsx` wie folgt auswerten:

```console
dotnet fsi Script2.fsx
144
```

Sie können beliebig viele `#load`-Anweisungen in einem Skript angeben.

## <a name="using-the-fsi-object-in-f-code"></a>Verwenden des `fsi`-Objekts in F#-Code

F#-Skripts können auf ein benutzerdefiniertes `fsi`-Objekt zugreifen, das die F# Interactive-Sitzung darstellt. Mit diesem Objekt können Aspekte wie die Ausgabeformatierung angepasst werden. Darüber hinaus können Sie auf diese Weise auf Befehlszeilenargumente zugreifen.

Im folgenden Beispiel wird gezeigt, wie Befehlszeilenargumente abgerufen und verwendet werden:

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

Bei der Auswertung werden alle Argumente ausgegeben. Das erste Argument ist immer der Name des Skripts, das ausgewertet wird:

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

Sie können auch mit `System.Environment.GetCommandLineArgs()` auf diese Argumente zugreifen.

## <a name="f-interactive-directive-reference"></a>Referenz zu F# Interactive-Anweisungen

Die zuvor erwähnten Anweisungen `#r` und `#load` sind nur in F# Interactive verfügbar. Eine Reihe weiterer Anweisungen sind ebenfalls nur in F# Interactive verfügbar:

|Anweisung|Beschreibung|
|---------|-----------|
|`#r "nuget:..."`|Verweist auf ein Paket aus NuGet.|
|`#r "assembly-name.dll"`|Verweist auf eine Assembly auf einem Datenträger|
|`#load "file-name.fsx"`|Liest eine Quelldatei, kompiliert sie und führt sie aus.|
|`#help`|Zeigt Informationen über verfügbare Anweisungen an.|
|`#I`|Gibt einen Assemblysuchpfad an (in Anführungszeichen).|
|`#quit`|Beendet eine F# Interactive-Sitzung.|
|`#time "on"` oder `#time "off"`|Einzeln angegeben aktiviert bzw. deaktiviert `#time` die Anzeige von Leistungsinformationen. Wenn `"on"` festgelegt ist, überwacht F# Interactive die reale Zeit, die CPU-Zeit sowie Garbage Collection-Informationen für jeden Codeabschnitt, der interpretiert und ausgeführt wird.|

Wenn Sie Dateien oder Pfade in F# Interactive angeben, wird ein Zeichenfolgenliteral erwartet. Daher müssen Dateien und Pfade in Anführungszeichen stehen. Es gelten die üblichen Escapezeichen. Sie können das Zeichen `@` verwenden, damit F# Interactive eine Zeichenfolge mit einem Pfad als ausführliche Zeichenfolge interpretiert. F# Interactive ignoriert in diesem Fall alle Escapezeichen.

## <a name="interactive-and-compiled-preprocessor-directives"></a>Interaktive und kompilierte Präprozessordirektiven

Wenn Sie Code in F# Interactive kompilieren (unabhängig davon, ob die Ausführung interaktiv oder über ein Skript erfolgt), ist das Symbol **INTERACTIVE** definiert. Beim Kompilieren von Code im Compiler ist das Symbol **COMPILED** definiert. Wenn Code im Kompilierungsmodus und im interaktiven Modus unterschiedlich sein muss, können Sie mithilfe von Präprozessordirektiven für die bedingte Kompilierung bestimmen, welche Variante verwendet werden soll. Beispiel:

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a>Verwenden von F# Interactive in Visual Studio

Zum Ausführen von F# Interactive über Visual Studio können Sie auf die entsprechende Symbolleistenschaltfläche **F# Interactive** klicken oder die Tastenkombination **Strg+Alt+F** verwenden. Dadurch wird das Interactive-Fenster geöffnet, ein Toolfenster, in dem eine F# Interactive-Sitzung ausgeführt wird. Sie können auch Code auswählen, den Sie im interaktiven Fenster ausführen möchten, und die Tastenkombination **ALT+EINGABETASTE** drücken. F# Interactive wird in einem Toolfenster mit der Bezeichnung **F# Interactive** gestartet. Wenn Sie diese Tastenkombination verwenden, überprüfen Sie, ob das Editorfenster den Fokus besitzt.

Unabhängig davon, ob Sie die Konsole oder Visual Studio verwenden, wird eine Eingabeaufforderung angezeigt, und der Interpreter erwartet Ihre Eingabe. Sie können Code auf die gleiche Weise wie in einer Codedatei eingeben. Geben Sie zum Kompilieren und Ausführen des Codes zwei Semikolons (**;;**) ein, um eine oder mehrere Zeilen der Eingabe zu beenden.

F# Interactive beginnt mit der Kompilierung des Codes, und wenn der Code erfolgreich kompiliert wurde, führt F# Interactive den Code aus und gibt die Signatur der kompilierten Typen und Werte aus. Wenn Fehler auftreten, gibt der Interpreter die Fehlermeldungen aus.

In der gleichen Sitzung eingegebener Code kann auf alle zuvor eingegebenen Konstrukte zugreifen. Daher können Sie Programme erstellen. Ein umfangreicher Puffer im Toolfenster ermöglicht es Ihnen, den Code bei Bedarf in eine Datei zu kopieren.

In Visual Studio wird F# Interactive unabhängig vom Projekt ausgeführt. Daher können Sie im Projekt definierte Konstrukte nur dann in F# Interactive verwenden, wenn Sie den Code für die Funktion in das Interactive-Fenster kopieren.

Sie können die Befehlszeilenargumente (Optionen) von F# Interactive steuern, indem Sie die Einstellungen anpassen. Wählen Sie im Menü **Extras** den Eintrag **Optionen** aus, und erweitern Sie anschließend **F#-Tools**. Die beiden Einstellungen, die Sie ändern können, sind die F# Interactive-Optionen und die Einstellung **64-Bit-F# Interactive**, die nur relevant ist, wenn Sie F# Interactive auf einem 64-Bit-Computer ausführen. Mit dieser Einstellung legen Sie fest, ob Sie die dedizierte 64-Bit-Version von **fsi.exe** oder aber **fsianycpu.exe** ausführen möchten, die anhand der Computerarchitektur ermittelt, ob sie als 32-Bit- oder 64-Bit-Prozess ausgeführt werden soll.

## <a name="related-articles"></a>Verwandte Artikel

|Titel|BESCHREIBUNG|
|-----|-----------|
|[F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md)|Beschreibt die Befehlszeilensyntax und Optionen für F# Interactive (fsi.exe)|
