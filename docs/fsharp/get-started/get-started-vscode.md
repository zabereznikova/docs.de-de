---
title: Erste Schritte mit F# in Visual Studio Code
description: 'Erfahren Sie, wie Sie F # mit Visual Studio Code und der ionide-Plug-in-Suite verwenden.'
ms.date: 12/23/2018
ms.openlocfilehash: 11fb0d443fb7c2b3f270d45bfeaa91102ba28efd
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739801"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Erste Schritte mit F# in Visual Studio Code

Sie können F # in [Visual Studio Code](https://code.visualstudio.com) mit dem [ionide-Plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in schreiben, um eine hervorragend plattformübergreifende, einfache integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) mit IntelliSense und coderegierungen zu erhalten. Besuchen Sie [Ionide.IO](https://ionide.io) , um mehr über das Plug-in zu erfahren.

Stellen Sie zunächst sicher, dass [F # und das ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code)sind.

## <a name="create-your-first-project-with-ionide"></a>Erstellen Ihres ersten Projekts mit ionide

Um ein neues F #-Projekt zu erstellen, öffnen Sie eine Befehlszeile, und erstellen Sie ein neues Projekt mit dem .net Core-CLI:

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

Ändern Sie nach Abschluss des Vorgangs das Verzeichnis in das Projekt, und öffnen Sie Visual Studio Code:

```console
cd FirstIonideProject
code .
```

Nachdem das Projekt Visual Studio Code geladen wurde, sollte der Bereich F # Projektmappen-Explorer auf der linken Seite des Fensters geöffnet angezeigt werden. Dies bedeutet, dass ionide das soeben erstellte Projekt erfolgreich geladen hat. Vor diesem Zeitpunkt können Sie Code im Editor schreiben, aber sobald dies geschieht, ist das Laden vollständig abgeschlossen.

## <a name="configure-f-interactive"></a>Konfigurieren von F # Interactive

Stellen Sie zunächst sicher, dass die .net Core-Skripterstellung Ihre standardmäßige Skript Umgebung ist:

1. Öffnen Sie die Visual Studio Code Einstellungen (Einstellungen für die **Code**  >  **Einstellungen**  >  **Settings**).
1. Suchen Sie nach dem Begriff **F #-Skript**.
1. Klicken Sie auf das Kontrollkästchen **FSharp: SDK-Skripts verwenden**.

Dies ist zurzeit aufgrund von Legacy Verhaltensweisen in .NET Framework basierten Skripts notwendig, die nicht mit der .net Core-Skripterstellung funktionieren, und der ionide-Wert ist zurzeit für diese Abwärtskompatibilität geeignet. In Zukunft wird die .net Core-Skripterstellung zum Standard.

### <a name="write-your-first-script"></a>Schreiben Ihres ersten Skripts

Nachdem Sie Visual Studio Code für die Verwendung der .net Core-Skripterstellung konfiguriert haben, navigieren Sie in Visual Studio Code zur Explorer-Ansicht, und erstellen Sie eine neue Datei. Nennen Sie Sie *myfirstscript. FSX*.

Fügen Sie nun den folgenden Code hinzu:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Diese Funktion konvertiert ein Wort in eine Form von [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Der nächste Schritt besteht darin, ihn mit F# Interactive (FSI) zu evaluieren.

Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein). Halten Sie die **alt** -Taste gedrückt, und drücken Sie die **Eingabe** Taste. Unten auf dem Bildschirm wird ein Terminalfenster angezeigt, das in etwa wie folgt aussehen sollte:

![Beispiel für F# Interactive Ausgabe mit ionide](./media/getting-started-vscode/vscode-fsi.png)

Dies hat drei Dinge getan:

1. Der FSI-Prozess wurde gestartet.
2. Der Code, den Sie über den FSI-Prozess hervorgehoben haben, wurde gesendet.
3. Der FSI-Prozess hat den Code ausgewertet, den Sie gesendet haben.

Da das, was Sie gesendet haben, eine [Funktion](../language-reference/functions/index.md)war, können Sie diese Funktion jetzt mit FSI abrufen! Geben Sie im interaktiven Fenster Folgendes ein:

```fsharp
toPigLatin "banana";;
```

Das folgende Ergebnis wird angezeigt:

```fsharp
val it : string = "ananabay"
```

Nun versuchen wir, einen Vokal als ersten Buchstaben zu verwenden. Geben Sie Folgendes ein:

```fsharp
toPigLatin "apple";;
```

Das folgende Ergebnis wird angezeigt:

```fsharp
val it : string = "appleyay"
```

Die Funktion scheint erwartungsgemäß zu funktionieren. Herzlichen Glückwunsch, Sie haben ihre erste F #-Funktion in Visual Studio Code geschrieben und mit FSI ausgewertet!

> [!NOTE]
> Wie Sie vielleicht bemerkt haben, werden die Zeilen in FSI mit beendet `;;` . Dies liegt daran, dass Sie mithilfe von FSI mehrere Zeilen eingeben können. Der `;;` am Ende ermöglicht FSI, wenn der Code abgeschlossen ist.

## <a name="explaining-the-code"></a>Erläutern des Codes

Wenn Sie nicht sicher sind, was der Code tatsächlich macht, finden Sie hier eine Schritt-für-Schritt-Anleitung.

Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe annimmt und Sie in eine Pig-Latin Darstellung dieses Worts konvertiert. Dies sind die folgenden Regeln:

Wenn das erste Zeichen in einem Wort mit einem vowel beginnt, fügen Sie am Ende des Worts "yay" hinzu. Wenn er nicht mit einem vowel beginnt, verschieben Sie das erste Zeichen an das Ende des Worts, und fügen Sie ihm "ay" hinzu.

Möglicherweise haben Sie Folgendes in FSI bemerkt:

```fsharp
val toPigLatin : word:string -> string
```

Dies `toPigLatin` ist eine Funktion, die eine `string` als Eingabe annimmt (aufgerufen `word` ) und eine andere zurückgibt `string` . Dies wird als die [Typsignatur](https://fsharpforfunandprofit.com/posts/function-signatures/)der-Funktion bezeichnet. Dies ist ein grundlegendes Element von f #, das zum Verständnis von f #-Code wichtig ist. Sie bemerken dies auch, wenn Sie in Visual Studio Code auf die Funktion zeigen.

Im Hauptteil der Funktion werden zwei unterschiedliche Teile feststellen:

1. Eine innere Funktion namens `isVowel` , die bestimmt, ob ein bestimmtes Zeichen ( `c` ) ein Vokal ist, indem überprüft wird, ob Sie mit einem der angegebenen Muster über den [Muster](../language-reference/pattern-matching.md)Abgleich übereinstimmt:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Ein [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Ausdruck, der überprüft, ob das erste Zeichen ein Vokal ist, und einen Rückgabewert aus den Eingabezeichen erstellt, basierend auf, wenn das erste Zeichen ein Vokal ist oder nicht:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Der Ablauf von `toPigLatin` ist daher:

Überprüfen Sie, ob das erste Zeichen des Eingabe Worts ein vowel ist. Wenn dies der Fall ist, fügen Sie "yay" an das Ende des Worts an. Verschieben Sie andernfalls das erste Zeichen an das Ende des Worts, und fügen Sie es hinzu.

Folgendes ist zu beachten: in F # gibt es keine explizite Anweisung, die von der Funktion zurückgegeben wird. Dies liegt daran, dass F # Ausdrucks basiert ist und der letzte Ausdruck, der im Text einer Funktion ausgewertet wurde, den Rückgabewert dieser Funktion bestimmt. Da `if..then..else` selbst ein Ausdruck ist, wird der `then` `else` von der Funktion zurückgegebene Wert durch Auswerten des Textblocks oder des Textblocks bestimmt `toPigLatin` .

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a>Umwandeln der Konsolen-app in einen Pig Latin-Generator

In den vorherigen Abschnitten dieses Artikels wurden die ersten Schritte zum Schreiben von F #-Code veranschaulicht: das Schreiben einer anfänglichen Funktion und das interaktive ausführen mit FSI. Dies wird als repl-gesteuerte Entwicklung bezeichnet, wobei [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) für "Read-Evaluation-Print Loop" steht. Es ist eine gute Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie etwas funktionieren.

Der nächste Schritt bei der repl-gesteuerten Entwicklung besteht darin, den funktionierenden Code in eine F #-Implementierungs Datei zu verschieben. Sie kann dann vom F #-Compiler in eine Assembly kompiliert werden, die ausgeführt werden kann.

Öffnen Sie zunächst die Datei " *Program. FS* ", die Sie zuvor mit dem .net Core-CLI erstellt haben. Sie werden feststellen, dass der Code bereits vorhanden ist.

Erstellen Sie als nächstes eine neue mit [`module`](../language-reference/modules.md) dem Namen, `PigLatin` und kopieren `toPigLatin` Sie die zuvor erstellte Funktion in diese:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

Dieses Modul sollte oberhalb der `main` Funktion und unterhalb der `open System` Deklaration liegen. Die Reihenfolge der Deklarationen ist in F # wichtig, daher müssen Sie die Funktion definieren, bevor Sie Sie in einer Datei abrufen.

Nennen Sie nun in der- `main` Funktion die Pig Latin Generator-Funktion für die Argumente:

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn %"{name} in Pig Latin is: {newName}"

    0
```

Nun können Sie Ihre Konsolen-App über die Befehlszeile ausführen:

```dotnetcli
dotnet run apple banana
```

Und Sie sehen, dass Sie das gleiche Ergebnis wie Ihre Skriptdatei ausgeben, aber dieses Mal als laufendes Programm!

## <a name="troubleshooting-ionide"></a>Problembehandlung bei ionide

Hier sind einige Möglichkeiten, wie Sie bestimmte Probleme beheben können, die möglicherweise auftreten können:

1. Um die Code Bearbeitungs Features von ionide zu erhalten, müssen die F #-Dateien auf dem Datenträger und in einem Ordner gespeichert werden, der im Arbeitsbereich Visual Studio Code geöffnet ist.
1. Wenn Sie Änderungen an Ihrem System vorgenommen oder die erforderlichen ionide-Komponenten mit Visual Studio Code Open installiert haben, starten Sie Visual Studio Code neu.
1. Wenn Ihre Projekt Verzeichnisse ungültige Zeichen enthalten, funktioniert ionide möglicherweise nicht.  Benennen Sie die Projekt Verzeichnisse um, wenn dies der Fall ist.
1. Wenn keiner der ionide-Befehle funktioniert, überprüfen Sie Ihre [Visual Studio Code Key-Bindungen](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) , um festzustellen, ob Sie Sie versehentlich überschreiben.
1. Wenn ionide auf dem Computer beschädigt ist und keines der oben genannten Probleme das Problem behoben hat, entfernen Sie das `ionide-fsharp` Verzeichnis auf Ihrem Computer, und installieren Sie die Plug-in-Suite erneut.
1. Wenn ein Projekt nicht geladen werden konnte (in F # Projektmappen-Explorer wird dies angezeigt), klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Details** anzeigen, um weitere Diagnoseinformationen zu erhalten.

Ionide ist ein Open Source-Projekt, das von Mitgliedern der F #-Community erstellt und verwaltet wird. Melden Sie sich mit Problemen an, und melden Sie sich gerne am " [ionide-vscode-FSharp"-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp)an.

Weitere Hilfe erhalten Sie von den ionide-Entwicklern und von der F #-Community im [ionide Gitter Channel](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu f # und den Funktionen der Sprache finden Sie unter Einführung in [f #](../tour.md).
