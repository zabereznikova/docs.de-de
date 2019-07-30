---
title: Erste Schritte mit F# in Visual Studio Code
description: Erfahren Sie, wie Sie F# mit Visual Studio Code und Ionide-Plug-Ins Suite verwenden.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629976"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Erste Schritte mit F# in Visual Studio Code

Können Sie F# in schreiben [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) um plattformübergreifende, einfache (Integrated Development Environment, IDE) Erfahrung mit IntelliSense und basic-Code zu erhalten. Refactorings. Besuchen Sie [Ionide.IO](http://ionide.io) , um mehr über das Plug-in zu erfahren.

Um zu beginnen, stellen Sie sicher, dass man [F# und Ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code).

> [!NOTE]
> Ionide generiert .NET Framework F# Projekte, nicht dotnet Core, die plattformübergreifende Kompatibilitätsprobleme aufweisen können. Wenn Sie **Linux** oder **OSX**ausführen, können Sie mit den [Befehlszeilen Tools](get-started-command-line.md)einfacher loslegen.

## <a name="creating-your-first-project-with-ionide"></a>Erstellen Ihres ersten Projekts mit ionide

Um ein neues F# Projekt zu erstellen, öffnen Sie Visual Studio Code in einem neuen Ordner (Sie können den Namen beliebig benennen).

Öffnen Sie als nächstes die Befehls Palette (zeigen Sie **> Befehls Palette**an), und geben Sie Folgendes ein:

```
> F# new project
```

Dies wird durch das Projekt " [Schmieden](https://github.com/fsharp-editing/Forge) " unterrichtet.

> [!NOTE]
> Wenn Sie keine Vorlagen Optionen sehen, versuchen Sie, Vorlagen zu aktualisieren, indem Sie den folgenden Befehl in `>F#: Refresh Project Templates`der Befehls Palette ausführen:.

Wählen SieF#": Neues Projekt "durch Drücken der **Eingabe**Taste. Dadurch gelangen Sie zum nächsten Schritt, in dem Sie eine Projektvorlage auswählen.

Wählen Sie `classlib` die Vorlage, und drücken **Sie die Eingabe**Taste.

Wählen Sie als nächstes ein Verzeichnis aus, in dem Sie das Projekt erstellen möchten. Wenn Sie das Feld leer lassen, wird das aktuelle Verzeichnis verwendet.

Benennen Sie Ihr Projekt abschließend im letzten Schritt. F#verwendet die [Pascal](http://c2.com/cgi/wiki?PascalCase) -Schreibweise für Projektnamen. In diesem Artikel `ClassLibraryDemo` wird als Name verwendet. Wenn Sie den gewünschten Namen für Ihr Projekt eingegeben haben, drücken Sie die **Eingabe**Taste.

Wenn Sie den vorherigen Schritt befolgt haben, sollte der Visual Studio Code Arbeitsbereich auf der linken Seite angezeigt werden, um Folgendes anzuzeigen:

1. Das F# Projekt selbst unterhalb des `ClassLibraryDemo` Ordners.
2. Die richtige Verzeichnisstruktur zum Hinzufügen von [`Paket`](https://fsprojects.github.io/Paket/)Paketen über.
3. Ein plattformübergreifendes Buildskript mit [`FAKE`](https://fsharp.github.io/FAKE/).
4. Die `paket.exe` ausführbare Datei, die Pakete abrufen und Abhängigkeiten für Sie auflösen kann.
5. Eine `.gitignore` Datei, wenn Sie dieses Projekt der git-basierten Quell Code Verwaltung hinzufügen möchten.

## <a name="writing-some-code"></a>Schreiben von Code

Öffnen Sie den Ordner *classlibrarydemo* .  Die folgenden Dateien sollten angezeigt werden:

1. `ClassLibraryDemo.fs`, eine F# Implementierungs Datei, für die eine Klasse definiert ist.
2. `ClassLibraryDemo.fsproj`, eine F# Projektdatei, die zum Erstellen dieses Projekts verwendet wird.
3. `Script.fsx`, eine F# Skriptdatei, die die Quelldatei lädt.
4. `paket.references`, eine Paket Datei, die die Projekt Abhängigkeiten angibt.

Öffnen `Script.fsx`Sie, und fügen Sie den folgenden Code am Ende der Datei hinzu:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Diese Funktion konvertiert ein Wort in eine Form von [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Der nächste Schritt ist mit F# Interactive (FSI) ausgewertet.

Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein). Halten Sie die **alt** -Taste gedrückt, und drücken **Sie die Eingabe**Taste. Sie sehen, dass ein Fenster unten angezeigt wird, und es sollte etwa wie folgt aussehen:

![Beispiel für F# Interactive-Ausgabe mit Ionide](./media/getting-started-vscode/vscode-fsi.png)

Dies hat drei Dinge getan:

1. Der FSI-Prozess wurde gestartet.
2. Der Code, den Sie über den FSI-Prozess hervorgehoben haben, wurde gesendet.
3. Der FSI-Prozess hat den Code ausgewertet, den Sie gesendet haben.

Da das, was Sie gesendet haben, eine [Funktion](../language-reference/functions/index.md)war, können Sie diese Funktion jetzt mit FSI abrufen! Geben Sie im interaktiven Fenster Folgendes ein:

```fsharp
toPigLatin "banana";;
```

Das folgende Ergebnis sollte angezeigt werden:

```fsharp
val it : string = "ananabay"
```

Nun versuchen wir, einen Vokal als ersten Buchstaben zu verwenden. Geben Sie Folgendes ein:

```fsharp
toPigLatin "apple";;
```

Das folgende Ergebnis sollte angezeigt werden:

```fsharp
val it : string = "appleyay"
```

Die Funktion scheint erwartungsgemäß zu funktionieren. Herzlichen Glückwunsch, Sie haben Ihre F# erste Funktion in Visual Studio Code geschrieben und mit FSI ausgewertet!

> [!NOTE]
> Wie Sie vielleicht bemerkt haben, werden die Zeilen in FSI mit `;;`beendet. Dies liegt daran, dass Sie mithilfe von FSI mehrere Zeilen eingeben können. Der `;;` am Ende ermöglicht FSI, wenn der Code abgeschlossen ist.

## <a name="explaining-the-code"></a>Erläutern des Codes

Wenn Sie nicht sicher sind, was der Code tatsächlich macht, finden Sie hier eine Schritt-für-Schritt-Anleitung.

Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe annimmt und in eine Pig-Latin-Darstellung dieses Worts konvertiert. Dies sind die folgenden Regeln:

Wenn das erste Zeichen in einem Wort mit einem vowel beginnt, fügen Sie am Ende des Worts "yay" hinzu. Wenn er nicht mit einem vowel beginnt, verschieben Sie das erste Zeichen an das Ende des Worts, und fügen Sie ihm "ay" hinzu.

Möglicherweise haben Sie Folgendes in FSI bemerkt:

```fsharp
val toPigLatin : word:string -> string
```

Dies ist eine Funktion, die eine `string` als Eingabe annimmt (aufgerufen `word`) und eine andere `string`zurückgibt. `toPigLatin` Dies bezeichnet man als den [der Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil von F#, die Schlüssel zum Verständnis der F#-Code ist. Sie bemerken dies auch, wenn Sie in Visual Studio Code auf die Funktion zeigen.

Im Hauptteil der Funktion werden zwei unterschiedliche Teile feststellen:

1. Eine innere Funktion namens `isVowel`, die bestimmt, ob ein bestimmtes Zeichen (`c`) ein Vokal ist, indem überprüft wird, ob Sie mit einem der angegebenen Muster über den [Muster](../language-reference/pattern-matching.md)Abgleich übereinstimmt:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Ein [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Ausdruck, der überprüft, ob das erste Zeichen ein Vokal ist, und einen Rückgabewert aus den Eingabezeichen erstellt, basierend auf, wenn das erste Zeichen ein Vokal ist oder nicht:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Der Ablauf von `toPigLatin` ist daher:

Überprüfen Sie, ob das erste Zeichen des Eingabe Worts ein vowel ist. Wenn dies der Fall ist, fügen Sie "yay" an das Ende des Worts an. Verschieben Sie andernfalls das erste Zeichen an das Ende des Worts, und fügen Sie es hinzu.

Es gibt noch ein letztes, was zu beachten ist: Es gibt keine explizite Anweisung, von der Funktion zurückzugeben, anders als bei vielen anderen Sprachen. Dies ist da F# ausdrucksbasiert ist, und der letzte Ausdruck in den Hauptteil einer Funktion der Rückgabewert ist. Da `if..then..else` selbst ein Ausdruck ist, wird der Text `then` des Blocks `else` oder der Textkörper des Blocks abhängig vom Eingabe Wert zurückgegeben.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Verschieben des Skriptcodes in die Implementierungs Datei

In den vorherigen Abschnitten dieses Artikels wurden die ersten Schritte zum Schreiben F# von Code veranschaulicht: das Schreiben einer anfänglichen Funktion und die interaktive Ausführung mit FSI. Dies wird als repl-gesteuerte Entwicklung bezeichnet, wobei [repl](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) für "Read-Evaluation-Print Loop" steht. Es ist eine gute Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie etwas funktionieren.

Der nächste Schritt bei der repl-gesteuerten Entwicklung besteht darin, den funktionierenden Code F# in eine Implementierungs Datei zu verschieben. Er kann dann vom F# Compiler in eine Assembly kompiliert werden, die ausgeführt werden kann.

Öffnen `ClassLibraryDemo.fs`Sie zunächst.  Sie werden feststellen, dass der Code bereits vorhanden ist. Löschen Sie die Klassendefinition, und übernehmen Sie [`namespace`](../language-reference/namespaces.md) die Deklaration im oberen Bereich.

Erstellen Sie als nächstes eine [`module`](../language-reference/modules.md) neue `PigLatin` mit dem Namen `toPigLatin` , und kopieren Sie die Funktion in die folgende Funktion:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Öffnen Sie als nächstes `Script.fsx` die Datei erneut, und löschen Sie `toPigLatin` die gesamte Funktion. Stellen Sie jedoch sicher, dass die folgenden beiden Zeilen in der Datei beibehalten werden:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Wählen Sie beide Textzeilen aus, und drücken Sie Alt + Eingabe, um diese Zeilen in FSI auszuführen. Diese werden den Inhalt der Pig Latin-Bibliothek in den FSI-Prozess und `open` den `ClassLibraryDemo` -Namespace laden, damit Sie auf die-Funktionalität zugreifen können.

Anschließend wird im FSI-Fenster die Funktion mit dem `PigLatin` Modul aufgerufen, das Sie zuvor definiert haben:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Erfolgreich! Sie erhalten dieselben Ergebnisse wie zuvor, werden aber nun aus einer F# Implementierungs Datei geladen. Der Hauptunterschied besteht darin, F# dass Quelldateien in Assemblys kompiliert werden, die an einer beliebigen Stelle ausgeführt werden können, nicht nur in FSI.

## <a name="summary"></a>Zusammenfassung

In diesem Artikel haben Sie Folgendes gelernt:

1. So richten Sie Visual Studio Code mit ionide ein
2. Erstellen Ihres ersten F# Projekts mit ionide
3. Verwenden F# der Skripterstellung zum Schreiben Ihrer ersten F# Funktion in ionide und deren Ausführung in FSI.
4. Migrieren Ihres Skriptcodes zu F# einer Quelle und anschließendes Abrufen des Codes von FSI.

Nun können Sie mit Visual Studio Code und ionide F# viel mehr Code schreiben.

## <a name="troubleshooting"></a>Problembehandlung

Hier sind einige Möglichkeiten, wie Sie bestimmte Probleme beheben können, die möglicherweise auftreten können:

1. Um die Code Bearbeitungs Features von ionide zu erhalten, F# müssen die Dateien auf dem Datenträger und innerhalb eines Ordners, der im Arbeitsbereich Visual Studio Code geöffnet ist, gespeichert werden.
2. Wenn Sie Änderungen an Ihrem System vorgenommen oder die erforderlichen ionide-Komponenten mit Visual Studio Code Open installiert haben, starten Sie Visual Studio Code neu.
3. Überprüfen Sie, dass Sie die F#-Compiler und F# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können. Sie können dazu eingeben `fsc` in einer Befehlszeile für den F#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono unter Mac/Linux, bzw.
4. Wenn Ihre Projekt Verzeichnisse ungültige Zeichen enthalten, funktioniert ionide möglicherweise nicht.  Benennen Sie die Projekt Verzeichnisse um, wenn dies der Fall ist.
5. Wenn keiner der ionide-Befehle funktioniert, überprüfen Sie die [Visual Studio Code keybindungen](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) , um festzustellen, ob Sie Sie versehentlich überschreiben.
6. Wenn ionide auf dem Computer beschädigt ist und keines der oben genannten Probleme das Problem behoben hat, entfernen Sie `ionide-fsharp` das Verzeichnis auf Ihrem Computer, und installieren Sie die Plug-in-Suite erneut.

Ionide ist ein Open Source-Projekt, das F# von Mitgliedern der Community erstellt und verwaltet wird. Melden Sie sich Probleme an, und nehmen Sie an [der "ionide-vscode" Teil: FSharp-GitHub](https://github.com/ionide/ionide-vscode-fsharp)-Repository.

Wenn Sie ein Problem melden müssen, befolgen Sie [die Anweisungen zum erhalten von Protokollen, die beim Melden eines Problems verwendet werden sollen](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

Sie können auch weitere Hilfe bitten, aus der Ionide-Entwickler und F#-Community in den [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu F# und die Funktionen der Sprache, sehen Sie sich [Einführung in F#](../tour.md).
