---
title: Erste Schritte mit f# in Visual Studio-Code
description: Informationen Sie zum Verwenden von f# mit Visual Studio-Code und der Ionide-Plug-in-Suite.
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728627"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Erste Schritte mit f# in Visual Studio-Code

Sie können schreiben f# [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-in](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), um eine hervorragende plattformübergreifende, einfache (Integrated Development Environment, IDE) Erfahrung mit IntelliSense und basic-Code Refactorings. Besuchen Sie [Ionide.io](http://ionide.io) Weitere Informationen zu den Plug-in-Suite.

## <a name="prerequisites"></a>Erforderliche Komponenten

Benötigen Sie [Git installiert](https://git-scm.com/download) und verfügbar in Ihrem Pfad zu der Projektvorlagen im Ionide verwenden. Sie können überprüfen, ob es ordnungsgemäß, durch Eingabe installiert ist `git --version` an der Eingabeaufforderung ein und drücken **EINGABETASTE**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Ionide verwendet [Mono](http://www.mono-project.com). Die einfachste Möglichkeit zum Installieren von Mono auf MacOS erfolgt über Homebrew. Geben Sie einfach die folgenden in Ihrem Terminal:

```
brew install mono
```

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

Unter Linux verwendet Ionide auch [Mono](https://www.mono-project.com). Wenn Sie auf Debian oder Ubuntu nutzen, können Sie Folgendes verwenden:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Wenn Sie auf Windows nutzen, müssen Sie [Installieren von Visual Studio mit Unterstützung für f#](get-started-visual-studio.md#installing-f). Hiermit werden die erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von f#-Code installiert.

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download/).

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>Installieren von Visual Studio-Code und die Ionide-Plug-in

Sie können Visual Studio-Code aus der [code.visualstudio.com](https://code.visualstudio.com) Website.

Klicken Sie dann auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":

Nur-Plug-In für f#-Unterstützung in Visual Studio-Code ist erforderlich [Ionide Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sie können jedoch auch installieren [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) abzurufenden [gefälschte](https://fsharp.github.io/FAKE/) unterstützen und [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket](https://fsprojects.github.io/Paket/) unterstützen. GEFÄLSCHTE und Paket werden zusätzliche F#-Community Tools zum Erstellen von Projekten und Verwalten von Abhängigkeiten, bzw.

## <a name="creating-your-first-project-with-ionide"></a>Erstellen eines ersten Projekts mit Ionide

Um ein neues F#-Projekt zu erstellen, öffnen Sie Visual Studio-Code in einen neuen Ordner (Sie können diese Namen einen beliebigen Namen).

Öffnen Sie dann den Befehl Palette (**Ansicht > Befehl Palette**), und geben Sie Folgendes ein:

```
> F# new project
```

Dies beruht die [FORGE](https://github.com/fsharp-editing/Forge) Projekt.

> [!NOTE]
Wenn Optionen nicht angezeigt wird, versuchen Sie es Aktualisieren von Vorlagen von den folgenden Befehl in der Palette Befehl ausführen: `>F#: Refresh Project Templates`.

Wählen Sie "f#: Neues Projekt" durch erreichen **EINGABETASTE**. Dadurch gelangen Sie mit dem nächsten Schritt, die für das Auswählen einer Projektvorlage.

Wählen Sie die `classlib` Vorlage, und drücken **EINGABETASTE**.

Als nächstes wählen Sie ein Verzeichnis zum Erstellen des Projekts in ein. Wenn Sie sie leer lassen, wird das aktuelle Verzeichnis verwendet.

Geben Sie schließlich Ihr Projekt im letzten Schritt. F# verwendet [Pascal-Schreibweise](http://c2.com/cgi/wiki?PascalCase) für Projektnamen. In diesem Artikel verwendet `ClassLibraryDemo` als Namen. Nachdem Sie den Namen eingegeben haben, für das Projekt erstellt werden sollen, erreicht **EINGABETASTE**.

Wenn Sie den vorherigen Schritt ausgeführt haben, sollten Sie Visual Studio Code-Arbeitsbereich auf der linken Seite mit den folgenden angezeigt abrufen:

1. Die f#-Projekt selbst, darunter die `ClassLibraryDemo` Ordner.
2. Die richtige Verzeichnisstruktur für das Hinzufügen von Paketen über [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Ein plattformübergreifendes Buildskript mit [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. Die `paket.exe` ausführbare Datei, fetch Pakete und Abhängigkeiten für Sie beheben kann.
5. Ein `.gitignore` Datei, wenn Sie dieses Projekt Git-basierten Datenquellen-Steuerelement hinzufügen möchten.

## <a name="writing-some-code"></a>Schreiben von code

Öffnen der *ClassLibraryDemo* Ordner.  Daraufhin sollte die folgenden Dateien:

1. `ClassLibraryDemo.fs`, ein f#-Implementierungsdatei mit einer Klasse definiert.
2. `ClassLibraryDemo.fsproj`, ein f#-Projektdatei verwendet, um dieses Projekt zu erstellen.
3. `Script.fsx`, ein F#-Skriptdatei, die die Quelldatei lädt.
4. `paket.references`, ein Paket-Datei, die projektabhängigkeiten angibt.

Open `Script.fsx`, und fügen Sie den folgenden Code am Ende des Zertifikats:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Diese Funktion konvertiert ein Wort in eine Form der [Pig-Lateinisch](https://en.wikipedia.org/wiki/Pig_Latin). Der nächste Schritt ist das mithilfe von f# Interactive (FSI) bewerten.

Markieren Sie die gesamte Funktion (er sollte 11 Zeilen lang sein). Sobald er hervorgehoben wird, halten die **Alt** Schlüssel, und klicken Sie **EINGABETASTE**. Sehen Sie ein Fenster diagnosepopup unten, und es sollte etwa wie folgt anzeigen:

![Beispiel für die Ausgabe von f# Interactive mit Ionide](media/getting-started-vscode/vscode-fsi.png)

Dies hat drei Dinge:

1. Es werden die FSI-Prozess wurde gestartet.
2. Er den Code für die markierte über den FSI-Prozess gesendet wurden.
3. Der Prozess FSI ausgewertet den Code, dem Sie über gesendet.

Was Sie über gesendet wurde eine [Funktion](../language-reference/functions/index.md), Sie können nun Aufrufe dieser Funktion mit FSI! Geben Sie im interactive-Fenster Folgendes ein:

```fsharp
toPigLatin "banana";;
```

Daraufhin sollte das folgende Ergebnis:

```fsharp
val it : string = "ananabay"
```

Jetzt sehen wir versuchen Sie es mit einem Vokal als der erste Buchstabe. Geben Sie Folgendes ein:

```fsharp
toPigLatin "apple";;
```

Daraufhin sollte das folgende Ergebnis:

```fsharp
val it : string = "appleyay"
```

Die Funktion kommt es zu wie erwartet funktionieren. Herzlichen Glückwunsch, Sie gerade geschrieben haben Ihre erste F#-Funktion in Visual Studio-Code, und es mit FSI ausgewertet.

>[!NOTE]
Wie Sie bemerkt haben, können die Zeilen im FSI enden mit `;;`. Dies ist da FSI Sie mehrere Zeilen eingeben kann. Die `;;` können Sie am Ende FSI kennen, wenn der Code beendet wird.

## <a name="explaining-the-code"></a>Erläuterung des Codes

Wenn Sie nicht sicher zur was tatsächlich der Code ausführt sind, wird hier eine schrittweise.

Wie Sie sehen können, `toPigLatin` ist eine Funktion, ein Wort als Eingabe akzeptiert und konvertiert ihn in ein Pig-Latin-Darstellung des Begriffs. Die Regeln dafür sind wie folgt aus:

Wenn das erste Zeichen in einem Wort mit einer Vokal beginnt, fügen Sie am Ende des Worts "Yay" hinzu. Wenn sie mit einem Vokal nicht gestartet, verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.

Sie haben möglicherweise in FSI Folgendes festgestellt:

```fsharp
val toPigLatin : word:string -> string
```

Dies gibt an, dass `toPigLatin` ist eine Funktion, die in akzeptiert eine `string` als Eingabe (aufgerufen `word`), und gibt eine andere `string`. Dies bezeichnet man die [Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil der f#, die Schlüssel zum Verständnis von f#-Code ist. Dies ist auch sehen, wenn Sie auf die Funktion in Visual Studio Code zeigen.

Im Text der Funktion sehen Sie zwei verschiedene Teilen:

1. Eine interne Funktion namens `isVowel`, die bestimmt, ob ein angegebenes Zeichen (`c`) überprüft, ob sie eine der über die angegebenen Muster übereinstimmt, besteht ein Vokal [Mustervergleich](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Ein [`if.then.else`](../language-reference/conditional-expressions-if-then-else.md) Ausdruck, der überprüft, ob das erste Zeichen ein Vokal ist und Konstrukte, die einen Rückgabewert aus der Eingabezeichen nach dem ersten Zeichen je wurde ein Vokal oder nicht:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Der Fluss der `toPigLatin` daher:

Überprüfen Sie, ob das erste Zeichen des eingegebenen Worts ein Vokal ist. Wenn dies der Fall, fügen Sie am Ende des Worts "Yay". Andernfalls verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.

Letzte Gemeinsamkeit zu diesem Beachten Sie: Es ist keine explizite Anweisung Rückgabe aus der Funktion im Gegensatz zu vielen weiteren Sprachen an es. Dies liegt daran f# ausdrucksbasiert ist, und der letzte Ausdruck im Text einer Funktion der Rückgabewert ist. Da `if.then.else` ist selbst ein Ausdruck, der Hauptteil der `then` Block oder im Textteil der `else` Block wird je nach den Eingabewert zurückgegeben werden.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Verschieben Sie den Skriptcode in der Implementierungsdatei

In den vorherigen Abschnitten in diesem Artikel veranschaulicht einen allgemeine ersten Schritt beim Schreiben von f#-Code: Schreiben einer anfänglichen Funktion und anschließend interaktiv mit FSI ausgeführt. Dies bezeichnet man REPL-driven Development, in denen [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) steht für "Lesen-auswerten-drucken-Schleife". Es ist eine hervorragende Möglichkeit zum Experimentieren mit Funktionalität, bis Sie etwas Arbeit haben.

Der nächste Schritt im REPL-driven Development ist für das Verschieben von Arbeitscode in einer f#-Implementierungsdatei. Sie können dann von f#-Compiler in eine Assembly kompiliert werden, die ausgeführt werden können.

Um zu beginnen, öffnen Sie `ClassLibraryDemo.fs`.  Sie werden bemerken, dass Code dort bereits in vorhanden ist. Fahren Sie fort und löschen Sie die Definition der Klasse, aber belassen Sie unbedingt die [ `namespace` ](../language-reference/namespaces.md) Deklaration oben.

Als Nächstes erstellen Sie ein neues [ `module` ](../language-reference/modules.md) aufgerufen `PigLatin` , und kopieren Sie die `toPigLatin` Funktion als solche hinein:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Öffnen Sie als Nächstes die `Script.fsx` Datei erneut, und löschen Sie das gesamte `toPigLatin` funktionsfähig, aber stellen Sie sicher, dass die folgenden zwei Zeilen in der Datei:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Die erste Zeile wird benötigt, um FSI scripting zum Laden `ClassLibraryDemo.fs`. Die zweite Zeile ist eine Annehmlichkeit: Typrückschlussmodul ist optional, aber Sie benötigen, geben Sie `open ClassLibraryDemo` in einem FSI-Fenster, wenn Sie schalten möchten die `ToPigLatin` Moduls einbinden.

Rufen Sie als Nächstes im Fenster FSI-Funktion mit dem `PigLatin` -Modul, das Sie zuvor definiert:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Erfolgreich! Sie erhalten die gleichen Ergebnisse wie vor, aber nun aus einer f#-Implementierungsdatei geladen. Der Hauptunterschied ist, dass f#-Quelldateien in Assemblys kompiliert werden, die an einer beliebigen Stelle, nicht nur in FSI ausgeführt werden kann.

## <a name="summary"></a>Zusammenfassung

In diesem Artikel haben Sie gelernt:

1. Wie Sie Visual Studio-Code mit Ionide einrichten.
2. Vorgehensweise: erstellen ein erste F#-Projekts mit Ionide.
3. Vorgehensweise zum Verwenden von F#-Skripts schreiben Ihrer ersten F#-Funktionen in Ionide, und führen Sie es in FSI.
4. Informationen zum Migrieren von Skriptcode in F#-Quelle und rufen Sie dann diesen Code aus FSI.

Sie sind jetzt ausgestattet, viel mehr F#-Code mithilfe von Visual Studio-Code und Ionide zu schreiben.

## <a name="troubleshooting"></a>Problembehandlung

Hier sind einige Möglichkeiten, die bestimmte Probleme können Sie Probleme beheben, denen auftreten kann:

1. Um die Bearbeitungsfunktionen der Ionide Code zu erhalten, müssen die f#-Dateien gespeichert werden sollen, auf den Datenträger und in einen Ordner, der in der Visual Studio Code-Arbeitsbereich geöffnet ist.
2. Wenn Sie Änderungen am System vorgenommen oder Ionide erforderlichen Komponenten installiert, mit Visual Studio-Code geöffnet haben, starten Sie Visual Studio Code neu.
3. Überprüfen Sie, dass Sie den f#-Compiler und f# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können. Können Sie dies tun, indem Sie Folgendes eingeben `fsc` in einer Befehlszeile für den f#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono auf Mac/Linux, bzw.
4. Wenn Sie ungültige Zeichen in Ihre Projektverzeichnisse haben, funktionieren möglicherweise nicht Ionide.  Benennen Sie Ihre Projektverzeichnisse aus, wenn dies der Fall ist.
5. Wenn keiner der Befehle Ionide arbeiten, überprüfen Sie Ihre [Visual Studio Code schlüsselbindungen](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) um festzustellen, ob Sie sie versehentlich überschreiben möchten.
6. Versuchen Sie es entfernen, wenn Ionide auf Ihrem Computer unterbrochen wird und keines der oben genannten wurde das Problem behoben, die `ionide-fsharp` -Verzeichnisses auf dem Computer und installieren Sie die Plug-in-Suite.

Ionide ist ein open Source-Projekt durch Mitglieder der f#-Community erstellt und verwaltet. Bitte Probleme mitzuteilen und gerne an beitragen der [Ionide-von VSCode: FSharp-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp).

Wenn Sie ein Problem beim Bericht haben, führen Sie die [die Anweisungen zum Abrufen der Protokolle zu verwenden, wenn Sie ein Problem melden](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

Sie können auch weitere Hilfe benötigen bitten, aus dem Ionide Entwickler und F#-Community in der [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu F#- und die Funktionen der Programmiersprache Auschecken [Tour von F#-](../tour.md).
