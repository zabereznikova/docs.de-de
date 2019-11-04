---
title: F# Interactive-Referenz (fsi.exe)
description: Erfahren Sie F# , wie interaktiv (FSI. exe) zum interaktiven F# Ausführen von Code in der Konsole oder zum F# Ausführen von Skripts verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: 9f4b5c0e7527d29e375265bb31a5de2df098f8e1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419907"
---
# <a name="interactive-programming-with-f"></a>Interaktive Programmierung mit F-\#

> [!NOTE]
> Dieser Artikel beschreibt derzeit nur das Erlebnis für Windows.  Er wird neu geschrieben.

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

F# Interactive (fsi.exe) wird zum interaktiven Ausführen von F#-Code in der Konsole oder zum Ausführen von F#-Skripts verwendet. Dies bedeutet, dass F# Interactive eine REPL (Read, Evaluate, Print Loop = Lesen-Auswerten-Drucken-Schleife) für F# ausführt.

Starten Sie "fsi.exe", um F# Interactive in der Konsole auszuführen.  Sie finden "FSI. exe" in:

```console
C:\Program Files (x86)\Microsoft Visual Studio\2019\<sku>\Common7\IDE\CommonExtensions\Microsoft\FSharp
```

Dabei ist `sku` entweder `Community`, `Professional`oder `Enterprise`.

Informationen zu verfügbaren Befehlszeilenoptionen finden Sie unter [F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md).

Zum Ausführen von F# Interactive über Visual Studio können Sie auf die entsprechende Symbolleistenschaltfläche **F# Interactive** klicken oder die Tastenkombination **Strg+Alt+F** verwenden. Dadurch wird das Interactive-Fenster geöffnet, ein Toolfenster, in dem eine F# Interactive-Sitzung ausgeführt wird. Sie können auch Code auswählen, den Sie im Interactive-Fenster ausführen möchten, und die Tastenkombination **ALT+EINGABE** drücken. F# Interactive wird in einem Toolfenster mit der Bezeichnung **F# Interactive** gestartet. Wenn Sie diese Tastenkombination verwenden, überprüfen Sie, ob das Editorfenster den Fokus besitzt.

Unabhängig davon, ob Sie die Konsole oder Visual Studio verwenden, wird eine Eingabeaufforderung angezeigt, und der Interpreter erwartet Ihre Eingabe. Sie können Code auf die gleiche Weise wie in einer Codedatei eingeben. Geben Sie zum Kompilieren und Ausführen des Codes zwei Semikolons ( **;;** ) ein, um eine oder mehrere Zeilen der Eingabe zu beenden.

F# Interactive beginnt mit der Kompilierung des Codes, und wenn der Code erfolgreich kompiliert wurde, führt F# Interactive den Code aus und gibt die Signatur der kompilierten Typen und Werte aus. Wenn Fehler auftreten, gibt der Interpreter die Fehlermeldungen aus.

In der gleichen Sitzung eingegebener Code kann auf alle zuvor eingegebenen Konstrukte zugreifen. Daher können Sie Programme erstellen. Ein umfangreicher Puffer im Toolfenster ermöglicht es Ihnen, den Code bei Bedarf in eine Datei zu kopieren.

In Visual Studio wird F# Interactive unabhängig vom Projekt ausgeführt. Daher können Sie im Projekt definierte Konstrukte nur dann in F# Interactive verwenden, wenn Sie den Code für die Funktion in das Interactive-Fenster kopieren.

Wenn Sie ein Projekt geöffnet haben, das auf einige Bibliotheken verweist, können Sie auf diese über den **Projektmappen-Explorer** in F# Interactive verweisen. Um auf eine Bibliothek in F# Interactive zu verweisen, erweitern Sie den Knoten **Verweise**, öffnen Sie das Kontextmenü für die Bibliothek, und wählen Sie **An F# Interactive senden** aus.

Sie können die Befehlszeilenargumente (Optionen) von F# Interactive steuern, indem Sie die Einstellungen anpassen. Wählen Sie im Menü **Extras** den Eintrag **Optionen** aus, und erweitern Sie anschließend **F#-Tools**. Die beiden Einstellungen, die Sie ändern können, sind die F# Interactive-Optionen und die Einstellung **64-Bit-F# Interactive**, die nur relevant ist, wenn Sie F# Interactive auf einem 64-Bit-Computer ausführen. Mit dieser Einstellung legen Sie fest, ob Sie die dedizierte 64-Bit-Version von fsi.exe oder aber fsianycpu.exe ausführen möchten, die anhand der Computerarchitektur ermittelt, ob sie als 32-Bit- oder 64-Bit-Prozess ausgeführt werden soll.

## <a name="scripting-with-f"></a>Skripterstellung mit F\#

Für Skripts wird die Dateierweiterung **.fsx** oder **.fsscript** verwendet. Statt Quellcode zu kompilieren und später die kompilierte Assembly auszuführen, können Sie einfach **fsi.exe** ausführen und den Dateinamen des Skripts mit dem F#-Quellcode angeben. F# Interactive liest dann den Code und führt ihn in Echtzeit aus.

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a>Unterschiede zwischen interaktiven, Skripterstellungs- und Kompilierungsumgebungen

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

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[F# Interactive-Optionen](../../language-reference/fsharp-interactive-options.md)|Beschreibt die Befehlszeilen Syntax und-Optionen für F# die interaktive FSI. exe-Anwendung.|
|[Referenz zur F# Interactive-Bibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|Beschreibt die beim Ausführen von Code in F# Interactive verfügbare Bibliotheksfunktion.|
