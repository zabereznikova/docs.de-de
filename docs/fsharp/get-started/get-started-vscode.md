---
title: Erste Schritte mit F# in Visual Studio Code
description: Erfahren Sie, wie Sie F# mit Visual Studio Code und Ionide-Plug-Ins Suite verwenden.
ms.date: 12/23/2018
ms.openlocfilehash: 7c2ecab14b3351d441249e7fc7cb3188a4ee7eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949555"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Erste Schritte mit F# in Visual Studio Code

Können Sie F# in schreiben [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) um plattformübergreifende, einfache (Integrated Development Environment, IDE) Erfahrung mit IntelliSense und basic-Code zu erhalten. Refactorings. Besuchen Sie [Ionide.io](http://ionide.io) Weitere Informationen zu den-Plug-in.

Um zu beginnen, stellen Sie sicher, dass man [F# und Ionide-Plug-in ordnungsgemäß installiert](install-fsharp.md#install-f-with-visual-studio-code).

> [!NOTE]
> Ionide generiert .NET Framework F# Projekte, nicht .NET Core, die plattformübergreifende Kompatibilitätsprobleme verfügen können. Wenn Sie auf Ausführen **Linux** oder **OSX**, eine einfachere Möglichkeit für den Einstieg ist die Verwendung der [Befehlszeilentools](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line).

## <a name="creating-your-first-project-with-ionide"></a>Erstellen Ihres ersten Projekts mit Ionide

Zum Erstellen eines neuen F# Projekt, öffnen Sie Visual Studio Code in einen neuen Ordner (Sie können sie einen beliebigen Namen).

Öffnen Sie als Nächstes die befehlspalette (**Ansicht > Befehlspalette**) und geben Sie Folgendes:

```
> F# new project
```

Dieser Vorgang beruht die [FÄLSCHEN](https://github.com/fsharp-editing/Forge) Projekt.

> [!NOTE]
> Wenn Sie Vorlagenoptionen für die nicht angezeigt wird, versuchen Sie es Aktualisieren von Vorlagen mithilfe des folgenden Befehls in der Befehlspalette: `>F#: Refresh Project Templates`.

Wählen Sie "F#: Neues Projekt"durch Drücken von **EINGABETASTE**. Dadurch gelangen Sie mit dem nächsten Schritt, die für das Auswählen einer Projektvorlage.

Wählen Sie die `classlib` Vorlage und Trefferanzahl **EINGABETASTE**.

Wählen Sie als Nächstes ein Verzeichnis zum Erstellen des Projekts in ein. Wenn Sie sie leer lassen, wird das aktuelle Verzeichnis verwendet.

Zum Schluss benennen Sie Ihr Projekt im letzten Schritt an. F#verwendet [Pascal-Schreibweise](http://c2.com/cgi/wiki?PascalCase) für Projektnamen. In diesem Artikel wird `ClassLibraryDemo` als Namen. Wenn Sie den Namen eingegeben haben, für das Projekt erstellt werden sollen, drücken Sie **EINGABETASTE**.

Wenn Sie den vorherigen Schritt ausgeführt haben, erhalten Sie Visual Studio Code-Arbeitsbereich auf der linken Seite mit den folgenden angezeigt:

1. Die F# Projekt selbst, darunter die `ClassLibraryDemo` Ordner.
2. Zum Hinzufügen von Paketen über die richtige Verzeichnisstruktur [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Eine plattformübergreifende Buildskript mit [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. Die `paket.exe` ausführbare Datei, Abrufen von Paketen und Abhängigkeiten für Sie beheben kann.
5. Ein `.gitignore` Datei, wenn Sie dieses Projekt zur quellcodeverwaltung im Git-basierte hinzufügen möchten.

## <a name="writing-some-code"></a>Schreiben von code

Öffnen der *ClassLibraryDemo* Ordner.  Daraufhin sollte die folgenden Dateien:

1. `ClassLibraryDemo.fs`, eine F# Implementierungsdatei mit einer definierten Klasse.
2. `ClassLibraryDemo.fsproj`, eine F# Projektdatei verwendet, um das Projekt zu erstellen.
3. `Script.fsx`, eine F# -Skriptdatei, die von der Quelldatei geladen.
4. `paket.references`, ein Paket-Abhängigkeits-Datei, die die Abhängigkeiten des Projekts angibt.

Open `Script.fsx`, und fügen Sie den folgenden Code am Ende des Zertifikats:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Diese Funktion konvertiert ein Wort in eine Form der [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). Der nächste Schritt ist mit F# Interactive (FSI) ausgewertet.

Markieren Sie die gesamte Funktion (es sollte 11 Zeilen lang sein). Sobald er hervorgehoben wird, enthalten die **Alt** Schlüssel, und klicken Sie auf **EINGABETASTE**. Sehen Sie ein Fenster angezeigt werden, unten, und es sollte etwa wie folgt angezeigt:

![Beispiel für F# Interactive-Ausgabe mit Ionide](media/getting-started-vscode/vscode-fsi.png)

In diesem Fall drei Dinge:

1. Es werden die FSI-Prozess wurde gestartet.
2. Sie haben den markierten Code über den Prozess FSI gesendet.
3. Der Prozess FSI ausgewertet den Code, dem Sie über gesendet.

Da war gesendeten über eine [Funktion](../language-reference/functions/index.md), Sie können nun Aufrufen dieser Funktion mit FSI! Geben Sie im interactive-Fenster Folgendes ein:

```fsharp
toPigLatin "banana";;
```

Daraufhin sollte das folgende Ergebnis:

```fsharp
val it : string = "ananabay"
```

Jetzt testen wir ein Vokal als den ersten Buchstaben. Geben Sie Folgendes ein:

```fsharp
toPigLatin "apple";;
```

Daraufhin sollte das folgende Ergebnis:

```fsharp
val it : string = "appleyay"
```

Die Funktion wird wie erwartet funktioniert. Herzlichen Glückwunsch, Sie soeben geschrieben haben Ihre erste F# Funktion in Visual Studio Code, und es mit FSI ausgewertet.

> [!NOTE]
> Wie Sie möglicherweise bemerkt haben, werden die Zeilen in FSI mit beendet `;;`. Dies ist da FSI mehrere Zeilen eingeben kann. Die `;;` können Sie am Ende FSI wissen, wann der Code beendet wurde.

## <a name="explaining-the-code"></a>Erläutern den code

Wenn Sie nicht sicher sind, zu der Code tatsächlich Wozu dient, wird eine detaillierte Anleitung.

Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe und konvertiert es in ein Pig-Latin-Darstellung des Begriffs. Die Regeln für diese sind wie folgt aus:

Wenn das erste Zeichen in einem Wort mit einem Vokal beginnt, fügen Sie am Ende des Worts "juhu" hinzu. Wenn sie mit einem Vokal nicht startet, wird verschieben Sie dem ersten Zeichen am Ende des Worts zu, und fügen Sie "Weg" hinzu.

Sie haben möglicherweise im FSI Folgendes festgestellt:

```fsharp
val toPigLatin : word:string -> string
```

Dies gibt an, dass `toPigLatin` ist eine Funktion, die in akzeptiert eine `string` als Eingabe (namens `word`), und wird ein anderes `string`. Dies bezeichnet man als den [der Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil von F#, die Schlüssel zum Verständnis der F#-Code ist. Sie werden dies auch feststellen, wenn Sie darauf zeigen, dass die Funktion in Visual Studio Code.

In den Text der Funktion sehen Sie zwei Teile:

1. Eine innere Funktion namens `isVowel`, die bestimmt, ob ein angegebenes Zeichen (`c`) überprüfen, ob diese einer der über die angegebenen Muster entspricht, besteht ein Vokal [Musterabgleich](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Ein [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) -Ausdruck, der prüft, ob das erste Zeichen ist ein Vokal Konstrukte, die einen Rückgabewert aus der Eingabezeichen abhängig, ob das erste Zeichen wurde ein Vokal oder nicht:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Die ablaufsteuerung `toPigLatin` ist daher:

Überprüfen Sie, ob das erste Zeichen des eingegebenen Worts ein Vokal ist. Wenn es sich handelt, fügen Sie am Ende des Worts "juhu". Andernfalls verschieben Sie dem ersten Zeichen am Ende des Worts zu, und fügen Sie "Weg" hinzu.

Eine letzte Sache dazu bitte beachten Sie: Es gibt keine explizite Anweisung von der Funktion, im Gegensatz zu es viele weitere Sprachen zurückgegeben. Dies ist da F# ausdrucksbasiert ist, und der letzte Ausdruck in den Hauptteil einer Funktion der Rückgabewert ist. Da `if..then..else` ist selbst ein Ausdruck, der Text der der `then` Block oder im Text der der `else` Block wird je nach dem eingegebenen Wert zurückgegeben werden.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Verschieben von Skriptcode in der Implementierungsdatei hinzu

Die vorherigen Abschnitten in diesem Artikel veranschaulicht die allgemeine ersten Schritt bei der Schreiben von F# Code: das Schreiben einer anfänglichen-Funktion und interaktiv mit FSI ausgeführt wird. Dies bezeichnet man als REPL-driven Development, in denen [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) steht für "Lesen-auswerten-ausgeben-Schleife". Es ist eine hervorragende Möglichkeit, mit der Funktionalität zu experimentieren, bis Sie funktioniert haben.

Der nächste Schritt im REPL-driven Development, verschieben Sie den funktionierenden Code in ist eine F# Implementierungsdatei einschließen. Sie können dann kompiliert werden, indem die F# Compiler in eine Assembly, die ausgeführt werden können.

Öffnen Sie zunächst `ClassLibraryDemo.fs`.  Sie werden feststellen, dass der Code bereits vorhanden vorhanden ist. Fahren Sie fort, und löschen Sie die Definition der Klasse, aber stellen Sie sicher, dass die [ `namespace` ](../language-reference/namespaces.md) Deklaration oben.

Als Nächstes erstellen Sie ein neues [ `module` ](../language-reference/modules.md) namens `PigLatin` , und kopieren Sie die `toPigLatin` als solche in diese Funktion:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Öffnen Sie als Nächstes die `Script.fsx` -Datei erneut, und löschen Sie das gesamte `toPigLatin` funktionieren, aber Achten Sie darauf, halten die folgenden zwei Zeilen in der Datei:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Wählen Sie die beiden Textzeilen aus, und drücken Sie Alt + Eingabetaste, um diese Zeilen in FSI auszuführen. Diese lädt den Inhalt der Pig Latin-Bibliothek in den FSI-Prozess und `open` der `ClassLibraryDemo` Namespace, damit Sie Zugriff auf die Funktionalität haben.

Rufen Sie als Nächstes im Fenster FSI-Funktion mit dem `PigLatin` -Modul, das Sie zuvor definiert:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Erfolgreich! Sie erhalten dieselben Ergebnisse wie bisher, aber jetzt aus geladen ein F# Implementierungsdatei einschließen. Der wesentliche Unterschied besteht darin, die F# Quelldateien kompiliert werden, in Assemblys, die nicht nur in FSI überall ausgeführt werden können.

## <a name="summary"></a>Zusammenfassung

In diesem Artikel haben Sie Folgendes gelernt:

1. Wie Sie Visual Studio Code mit Ionide einrichten.
2. Vorgehensweise: Erstellen Ihrer ersten F# -Projekts mit Ionide.
3. Gewusst wie: Verwenden Sie F# Skripterstellung zum Schreiben Ihrer ersten F# im Ionide funktionieren, und führen Sie ihn anschließend in FSI.
4. Gewusst wie: Migrieren zu Skriptcode F# Datenquelle, und rufen Sie dann diesen Code von FSI.

Sie sind jetzt noch viel mehr schreiben ausgestattet F# code mit Visual Studio Code und Ionide.

## <a name="troubleshooting"></a>Problembehandlung

Hier sind einige Möglichkeiten, wie, die Sie bestimmte Probleme beheben können, denen auftreten können:

1. Um den Code Bearbeitungsfunktionen Ionide, erhalten Ihre F# müssen Dateien gespeichert werden, auf dem Datenträger und in einen Ordner, der in der Visual Studio Code-Arbeitsbereich geöffnet ist.
2. Wenn Sie Änderungen an Ihrem System oder Ionide erforderlichen Komponenten installiert, mit Visual Studio Code geöffnet haben, starten Sie Visual Studio Code neu.
3. Überprüfen Sie, dass Sie die F#-Compiler und F# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können. Sie können dazu eingeben `fsc` in einer Befehlszeile für den F#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono unter Mac/Linux, bzw.
4. Wenn Sie ungültige Zeichen in Ihrem Projektverzeichnisse verfügen, funktionieren möglicherweise nicht Ionide.  Benennen Sie Ihre Projektverzeichnisse, wenn dies der Fall ist.
5. Wenn keines der Ionide-Befehle verwenden, überprüfen Sie Ihre [standardtastenzuordnungen von Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) um festzustellen, ob Sie sie versehentlich überschreiben möchten.
6. Versuchen Sie es entfernen, wenn Ionide auf Ihrem Computer aufgeteilt wird und keines der genannten wurde das Problem behoben, die `ionide-fsharp` Verzeichnis auf Ihrem Computer und installieren Sie die Suite-Plug-In erneut.

Ionide ist ein open-Source-Projekt, erstellt und verwaltet, die von einem Mitglied der F# Community. Sie Probleme melden und gerne am beitragen die [Ionide-VSCode: FSharp-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp).

Wenn Sie ein Problem gemeldet haben, führen Sie [die Anweisungen zum Abrufen von Protokollen zu verwenden, wenn ein Problem meldet](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

Sie können auch weitere Hilfe bitten, aus der Ionide-Entwickler und F#-Community in den [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu F# und die Funktionen der Sprache, sehen Sie sich [Einführung in F#](../tour.md).
