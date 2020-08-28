---
title: Referenz zu F# Interactive (dotnet)
description: Hier erfahren Sie, wie F# Interactive (dotnet fsi) zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts verwendet wird.
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 760b096c8a3ee0d495b893ab66fa6f9007cdbbf9
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867619"
---
# <a name="interactive-programming-with-f"></a>Interaktive Programmierung mit F\#

F# Interactive (dotnet fsi) dient zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts. Dies bedeutet, dass F# Interactive eine REPL (Read, Evaluate, Print Loop = Lesen-Auswerten-Drucken-Schleife) für F# ausführt.

Führen Sie `dotnet fsi` aus, um F# Interactive in der Konsole auszuführen. Sie finden `dotnet fsi` in einem beliebigen .NET SDK.

Informationen zu verfügbaren Befehlszeilenoptionen finden Sie unter [F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md).

Zum Ausführen von F# Interactive über Visual Studio können Sie auf die entsprechende Symbolleistenschaltfläche **F# Interactive** klicken oder die Tastenkombination **Strg+Alt+F** verwenden. Dadurch wird das Interactive-Fenster geöffnet, ein Toolfenster, in dem eine F# Interactive-Sitzung ausgeführt wird. Sie können auch Code auswählen, den Sie im interaktiven Fenster ausführen möchten, und die Tastenkombination **ALT+EINGABETASTE** drücken. F# Interactive wird in einem Toolfenster mit der Bezeichnung **F# Interactive** gestartet. Wenn Sie diese Tastenkombination verwenden, überprüfen Sie, ob das Editorfenster den Fokus besitzt.

Unabhängig davon, ob Sie die Konsole oder Visual Studio verwenden, wird eine Eingabeaufforderung angezeigt, und der Interpreter erwartet Ihre Eingabe. Sie können Code auf die gleiche Weise wie in einer Codedatei eingeben. Geben Sie zum Kompilieren und Ausführen des Codes zwei Semikolons (**;;**) ein, um eine oder mehrere Zeilen der Eingabe zu beenden.

F# Interactive beginnt mit der Kompilierung des Codes, und wenn der Code erfolgreich kompiliert wurde, führt F# Interactive den Code aus und gibt die Signatur der kompilierten Typen und Werte aus. Wenn Fehler auftreten, gibt der Interpreter die Fehlermeldungen aus.

In der gleichen Sitzung eingegebener Code kann auf alle zuvor eingegebenen Konstrukte zugreifen. Daher können Sie Programme erstellen. Ein umfangreicher Puffer im Toolfenster ermöglicht es Ihnen, den Code bei Bedarf in eine Datei zu kopieren.

In Visual Studio wird F# Interactive unabhängig vom Projekt ausgeführt. Daher können Sie im Projekt definierte Konstrukte nur dann in F# Interactive verwenden, wenn Sie den Code für die Funktion in das Interactive-Fenster kopieren.

Wenn Sie ein Projekt geöffnet haben, das auf einige Bibliotheken verweist, können Sie auf diese über den **Projektmappen-Explorer** in F# Interactive verweisen. Um auf eine Bibliothek in F# Interactive zu verweisen, erweitern Sie den Knoten **Verweise**, öffnen Sie das Kontextmenü für die Bibliothek, und wählen Sie **An F# Interactive senden** aus.

Sie können die Befehlszeilenargumente (Optionen) von F# Interactive steuern, indem Sie die Einstellungen anpassen. Wählen Sie im Menü **Extras** den Eintrag **Optionen** aus, und erweitern Sie anschließend **F#-Tools**. Die beiden Einstellungen, die Sie ändern können, sind die F# Interactive-Optionen und die Einstellung **64-Bit-F# Interactive**, die nur relevant ist, wenn Sie F# Interactive auf einem 64-Bit-Computer ausführen. Mit dieser Einstellung legen Sie fest, ob Sie die dedizierte 64-Bit-Version von fsi.exe oder aber fsianycpu.exe ausführen möchten, die anhand der Computerarchitektur ermittelt, ob sie als 32-Bit- oder 64-Bit-Prozess ausgeführt werden soll.

## <a name="scripting-with-f"></a>Skripterstellung mit F\#

Für Skripts wird die Dateierweiterung **.fsx** oder **.fsscript** verwendet. Statt Quellcode zu kompilieren und später die kompilierte Assembly auszuführen, können Sie einfach **dotnet fsi** ausführen und den Dateinamen des Skripts mit dem F#-Quellcode angeben. F# Interactive liest dann den Code und führt ihn in Echtzeit aus.

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a>Unterschiede zwischen interaktiven Umgebungen, kompilierten Umgebungen und Skripterstellungsumgebungen

Wenn Sie Code in F# Interactive kompilieren, unabhängig davon, ob die Ausführung interaktiv oder über ein Skript erfolgt, ist das Symbol **INTERACTIVE** definiert. Beim Kompilieren von Code im Compiler ist das Symbol **COMPILED** definiert. Wenn Code im Kompilierungsmodus und interaktiven Modus unterschiedlich sein muss, können Sie mithilfe von Präprozessoranweisungen für die bedingte Kompilierung bestimmen, welcher Code verwendet werden soll.

Beim Ausführen von Skripts in F# Interactive sind einige Direktiven verfügbar, die beim Ausführen des Compilers nicht verfügbar sind. In der folgenden Tabelle sind die Direktiven zusammengefasst, die verfügbar sind, wenn Sie F# Interactive verwenden.

|Anweisung|Beschreibung|
|---------|-----------|
|**#help**|Zeigt Informationen über verfügbare Anweisungen an.|
|**#I**|Gibt einen Assemblysuchpfad an (in Anführungszeichen).|
|**#load**|Liest eine Quelldatei, kompiliert sie und führt sie aus.|
|**#quit**|Beendet eine F# Interactive-Sitzung.|
|**#r**|Verweist auf eine Assembly.|
|**#time ["on"&#124;"off"]**|Einzeln angegeben aktiviert bzw. deaktiviert **#time** die Anzeige von Leistungsinformationen. Wenn die Option aktiviert ist, überwacht F# Interactive die reale Zeit, die CPU-Zeit sowie Garbage Collection-Informationen für jeden Codeabschnitt, der interpretiert und ausgeführt wird.|

Wenn Sie Dateien oder Pfade in F# Interactive angeben, wird ein Zeichenfolgenliteral erwartet. Daher müssen Dateien und Pfade in Anführungszeichen stehen. Es gelten die üblichen Escapezeichen. Zusätzlich können Sie das Zeichen @ verwenden. F# Interactive wird damit angewiesen, eine Zeichenfolge mit einem Pfad als wörtliche Zeichenfolge zu interpretieren. F# Interactive ignoriert in diesem Fall alle Escapezeichen.

Der Kompilierungsmodus und der interaktive Modus unterscheiden sich u. a. durch die Art des Zugriffs auf Befehlszeilenargumente. Verwenden Sie im Kompilierungsmodus **System.Environment.GetCommandLineArgs**. Verwenden Sie in Skripts **fsi.CommandLineArgs**.

Im folgenden Code wird das Erstellen einer Funktion veranschaulicht, die die Befehlszeilenargumente in einem Skript liest, und es wird außerdem gezeigt, wie aus einem Skript auf eine andere Assembly verwiesen wird. Die erste Codedatei **MyAssembly.fs** ist der Code für die Assembly, auf die verwiesen wird. Kompilieren Sie diese Datei mit der Befehlszeile: **fsc -a MyAssembly.fs** und führen Sie dann die zweite Datei mit der Befehlszeile: **fsi --exec file1.fsx** testen

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

Die Ausgabe lautet wie folgt:

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a>Paketverwaltung in F# Interactive

[!NOTE] Die Paketverwaltung ist als Previewfunktion in Versionen von `dotnet fsi`, die in `3.1.300` und höheren Versionen des .NET SDK enthalten sind, sowie in allen `5.*`-Versionen des .NET SDK verfügbar. Führen Sie `dotnet fsi` mit dem Argument `--langversion:preview` aus, um es in dieser Vorschauversion zu aktivieren.

Die `#r`-Syntax für das Verweisen auf eine DLL in F# Interactive kann auch verwendet werden, um auf ein NuGet-Paket über die folgende Syntax zu verweisen:

```fsharp
#r "nuget: <package name>
```

Um beispielsweise auf das Paket `FSharp.Data` zu verweisen, verwenden Sie den folgenden `#r`-Verweis:

```fsharp
#r "nuget: FSharp.Data"
```

Nach Ausführung dieser Zeile wird die neueste Version des Pakets `FSharp.Data` in Ihren NuGet-Cache heruntergeladen, auf die in der aktuellen F# Interactive-Sitzung verwiesen wird.

Zusätzlich zum Paketnamen kann über eine Kurzsyntax auf bestimmte Versionen eines Pakets verwiesen werden:

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

oder auf explizitere Weise:

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a>Verwandte Artikel

|Titel|BESCHREIBUNG|
|-----|-----------|
|[F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md)|Beschreibt die Befehlszeilensyntax und Optionen für F# Interactive (fsi.exe)|
|[Referenz zur F# Interactive-Bibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|Beschreibt die beim Ausführen von Code in F# Interactive verfügbare Bibliotheksfunktion.|
