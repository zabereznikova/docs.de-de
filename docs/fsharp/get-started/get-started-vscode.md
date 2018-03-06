---
title: Erste Schritte mit f# in Visual Studio-Code mit Ionide
description: Informationen Sie zum Verwenden von f# mit Visual Studio-Code und der Ionide-Plug-in-Suite.
keywords: Visual f#, f#, funktionalen Programmierung, .NET, Visual Studio-Code von Vscode, Ionide
author: cartermp
ms.author: phcart
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 49775139-082e-442f-b5a2-dd402399b5d2
ms.openlocfilehash: 83099005074ea273eae5319edacd2e2ee0f7145f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="getting-started-with-f-in-visual-studio-code-with-ionide"></a>Erste Schritte mit f# in Visual Studio-Code mit Ionide

Sie können schreiben f# [Visual Studio Code](https://code.visualstudio.com) mit der [Ionide-Plug-Ins](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), um eine plattformübergreifende, einfache IDE problembehandlungserlebnis mit IntelliSense und grundlegenden Code Refactorings abzurufen.  Besuchen Sie [Ionide.io](https://ionide.io) Weitere Informationen zu den Plug-in-Suite.

## <a name="prerequisites"></a>Erforderliche Komponenten

F#-4.0 oder höher muss auf dem Computer mit Ionide installiert sein.

Darüber hinaus benötigen Sie [Git installiert](https://git-scm.com/download) und verfügbar in Ihrem Pfad zu der Projektvorlagen im Ionide verwenden.  Sie können überprüfen, ob es ordnungsgemäß, durch Eingabe installiert ist `git` an einen Befehl prompt.and drücken **EINGABETASTE**.

### <a name="windows"></a>Windows

Wenn Sie auf Windows nutzen, haben Sie zwei Optionen für die Installation von f#.

Wenn Sie Visual Studio bereits installiert haben und keine f#, können Sie [Installieren von Visual F#-Tools](get-started-visual-studio.md#installing-f).  Dadurch werden die erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von f#-Code installiert.

Wenn Sie nicht Visual Studio installieren möchten, gehen Sie folgendermaßen vor:

1. Installieren Sie [.NET Framework 4.5 oder höher](https://www.microsoft.com/en-US/download/details.aspx?id=30653) , wenn Sie Windows 7 ausführen.  Wenn Sie Windows 8 oder höher verwenden, müssen Sie nicht dies tun.

2. Installieren Sie das Windows SDK für Ihr Betriebssystem aus:

    * [Windows 10 SDK](https://dev.windows.com/en-US/downloads/windows-10-sdk)
    * [Windows 8.1 SDK](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [Windows 8 SDK](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [Windows 7 SDK](https://www.microsoft.com/download/details.aspx?id=8279)

3. Installieren der [Microsoft Build 2015-Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48159).  Sie müssen möglicherweise auch installieren [Microsoft Build Tools 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40760).

4. Installieren der [Visual f#-Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48179).

Auf 64-Bit-Windows befinden, dem Compiler und Tools hier:

```
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

Auf 32-Bit-Windows befinden sich die Compilertools hier:

```
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

Ionide erkennt automatisch dem Compiler und Tools, aber wenn aus irgendeinem Grund nicht (z. B. Visual f#-Tools in einem anderen Verzeichnis installiert wurden), können Sie manuell den enthaltenden Ordner hinzufügen (`...\Microsoft SDKs\F#\4.0`) zu Ihrem Pfad.

### <a name="macos"></a>macOS

Auf MacOS, Ionide verwendet [Mono](https://www.mono-project.com).  Die einfachste Möglichkeit zum Installieren von Mono auf MacOS erfolgt über Homebrew.  Geben Sie einfach die folgenden in Ihrem Terminal:

```
brew install mono
```

### <a name="linux"></a>Linux

Unter Linux verwendet Ionide auch [Mono](https://www.mono-project.com).  Wenn Sie auf Debian oder Ubuntu nutzen, können Sie Folgendes verwenden:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>Installieren von Visual Studio-Code und die Ionide-Plug-in

Sie können Visual Studio-Code aus der [code.visualstudio.com](https://code.visualstudio.com) Website.  Es gibt zwei Möglichkeiten, um das Plug-in Ionide finden, danach:

1. Verwenden Sie die Palette-Befehl (STRG + UMSCHALT + P ist die unter Windows, ⌘ + UMSCHALT + P auf MacOS, STRG + UMSCHALT + P unter Linux), und geben Sie Folgendes:

    ```
    >ext install Ionide
    ```

2. Klicken Sie auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":

    ![](media/getting-started-vscode/vscode-ext.png)

Nur-Plug-In für f#-Unterstützung in Visual Studio-Code ist erforderlich [Ionide Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).  Sie können jedoch auch installieren [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) und die abzurufenden [gefälschte](https://fake.build/) unterstützen und [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket](https://fsprojects.github.io/Paket/) unterstützen.  GEFÄLSCHTE und Paket zusätzliche F#-Community-Tools zum Erstellen von Projekten und Verwalten von Abhängigkeiten, bzw. sind.

## <a name="creating-your-first-project-with-ionide"></a>Erstellen eines ersten Projekts mit Ionide

Um ein neues F#-Projekt zu erstellen, öffnen Sie Visual Studio-Code in einen neuen Ordner (Sie können diese Namen einen beliebigen Namen).

![](media/getting-started-vscode/vscode-open-dir.png)

Als Nächstes öffnen Sie den Befehl Palette (STRG + UMSCHALT + P ist die unter Windows, ⌘ + UMSCHALT + P auf MacOS, STRG + UMSCHALT + P unter Linux), und geben Sie Folgendes ein:

```
>f#: New Project
```

Dies beruht die [FORGE](https://github.com/fsharp-editing/Forge) Projekt.  Folgendes sollte angezeigt werden:

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
Wenn Sie die oben nicht angezeigt wird, versuchen Sie es Aktualisieren von Vorlagen von den folgenden Befehl in der Palette Befehl ausführen: `>F#: Refresh Project Templates`.

Wählen Sie "f#: Neues Projekt" durch erreichen **EINGABETASTE**, dem gelangen Sie zu diesem Schritt:

![](media/getting-started-vscode/vscode-proj-type.png)

Es wird eine Vorlage für einen bestimmten Typ von Projekt ausgewählt.  Es gibt einige Optionen, wie ein [FsLab](https://fslab.org) Vorlage für Data Science oder [Suave](https://suave.io) Vorlage für das Web zu programmieren.  In diesem Artikel verwendet die `classlib` Vorlage so hervorzuheben, und drücken Sie **EINGABETASTE**.  Sie gelangen Sie dann den folgenden Schritt aus:

![](media/getting-started-vscode/vscode-new-dir.png)

Dadurch können Sie das Projekt ggf. in einem anderen Verzeichnis zu erstellen.  Gelassen Sie vorläufig.  Es wird das Projekt im aktuellen Verzeichnis erstellt.  Sobald Sie drücken **EINGABETASTE**, gelangen Sie den folgenden Schritt aus:

![](media/getting-started-vscode/vscode-proj-name.png)

Dadurch können Sie Ihrem Projekt einen Namen geben.  F# verwendet [Pascal-Schreibweise](http://c2.com/cgi/wiki?PascalCase) für Projektnamen.  In diesem Artikel verwendet `ClassLibraryDemo` als Namen.  Nachdem Sie den Namen eingegeben haben, für das Projekt erstellt werden sollen, erreicht **EINGABETASTE**.

Wenn Sie den vorherigen Schritt Schritte befolgt haben, sollten Sie Visual Studio Code-Arbeitsbereich auf der linken Seite um etwa wie folgt aussehen abrufen:

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

Diese Vorlage generiert ein paar Dinge, die Sie hilfreich finden:

1. Die f#-Projekt selbst, darunter die `ClassLibraryDemo` Ordner.
2. Die richtige Verzeichnisstruktur für das Hinzufügen von Paketen über [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Ein plattformübergreifendes Buildskript mit [ `FAKE` ](https://fake.build/).
4. Die `paket.exe` ausführbare Datei die fetch Pakete und Abhängigkeiten für Sie beheben kann.
5. Ein `.gitignore` Datei, wenn Sie dieses Projekt Git-basierten Datenquellen-Steuerelement hinzufügen möchten.

## <a name="writing-some-code"></a>Schreiben von code

Öffnen der *ClassLibraryDemo* Ordner.  Daraufhin sollte die folgenden Dateien:

1. `ClassLibraryDemo.fs`, ein f#-Implementierungsdatei mit einer Klasse definiert.
2. `CassLibraryDemo.fsproj`, ein f#-Projektdatei verwendet, um dieses Projekt zu erstellen.
3. `Script.fsx`, ein F#-Skriptdatei, der die Quelldatei lädt.
4. `paket.references`, eine Paket-Datei, die die projektabhängigkeiten angibt.

Open `Script.fsx`, und fügen Sie den folgenden Code am Ende des Zertifikats:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Diese Funktion konvertiert ein Wort in eine Form der [Pig-Lateinisch](https://en.wikipedia.org/wiki/Pig_Latin).  Der nächste Schritt ist das mithilfe von f# Interactive (FSI) bewerten.

Markieren Sie die gesamte Funktion (er sollte 11 Zeilen lang sein).  Sobald er hervorgehoben wird, halten die **Alt** Schlüssel, und klicken Sie **EINGABETASTE**.  Sehen Sie ein Fenster diagnosepopup unten, und es sollte etwa wie folgt anzeigen:

![](media/getting-started-vscode/vscode-fsi.png)

Dies hat drei Dinge:

1. Es werden die FSI-Prozess wurde gestartet.
2. Er den Code für die markierte über den FSI-Prozess gesendet wurden.
3. Der Prozess FSI ausgewertet den Code, dem Sie über gesendet.

Was Sie über gesendet wurde eine [Funktion](../language-reference/functions/index.md), Sie können nun Aufrufe dieser Funktion mit FSI!  Geben Sie im interactive-Fenster Folgendes ein:

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

Die Funktion kommt es zu wie erwartet funktionieren.  Herzlichen Glückwunsch, Sie gerade geschrieben haben Ihre erste F#-Funktion in Visual Studio-Code, und es mit FSI ausgewertet.

>[!NOTE]
Wie Sie bemerkt haben, können die Zeilen im FSI enden mit `;;`.  Dies ist da FSI Sie mehrere Zeilen eingeben kann.  Die `;;` können Sie am Ende FSI kennen, wenn der Code beendet wird.

## <a name="explaining-the-code"></a>Erläuterung des Codes

Wenn Sie nicht sicher zur was tatsächlich der Code ausführt sind, wird hier eine schrittweise.

Wie Sie sehen können, `toPigLatin` ist eine Funktion, die ein Wort als Eingabe akzeptiert und konvertiert ihn in ein Pig-Latin-Darstellung des Begriffs.  Die Regeln dafür sind wie folgt aus:

Wenn das erste Zeichen in einem Wort mit einer Vokal beginnt, fügen Sie am Ende des Worts "Yay" hinzu.  Wenn sie mit einem Vokal nicht gestartet, verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.

Sie haben möglicherweise in FSI Folgendes festgestellt:

```
val toPigLatin : word:string -> string
```

Dies gibt an, dass `toPigLatin` ist eine Funktion, die nimmt eine `string` als Eingabe (aufgerufen `word`), und gibt eine andere `string`.  Dies bezeichnet man die [Typsignatur der Funktion](https://fsharpforfunandprofit.com/posts/function-signatures/), ein wesentlicher Bestandteil der f#, die Schlüssel zum Verständnis von f#-Code ist.  Dies ist auch sehen, wenn Sie auf die Funktion in Visual Studio Code zeigen.

Im Text der Funktion sehen Sie zwei verschiedene Teilen:

1. Eine interne Funktion namens `isVowel`, die bestimmt, ob ein angegebenes Zeichen (`c`) überprüft, ob sie eine der über die angegebenen Muster übereinstimmt, besteht ein Vokal [Mustervergleich](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Ein [`if.then.else`](../language-reference/conditional-expressions-if-then-else.md) welche überprüft, ob das erste Zeichen ein Vokal, und einen Rückgabewert aus der Eingabezeichen erstellt nach dem ersten Zeichen je Ausdruck wurde ein Vokal oder nicht:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

Der Fluss der `toPigLatin` daher:

Überprüfen Sie, ob das erste Zeichen des eingegebenen Worts ein Vokal ist.  Wenn dies der Fall, fügen Sie am Ende des Worts "Yay".  Andernfalls verschieben Sie das erste Zeichen bis zum Ende des Worts, und fügen Sie "Weg" hinzu.

Letzte Gemeinsamkeit zu diesem Beachten Sie: Es ist keine explizite Anweisung Rückgabe aus der Funktion im Gegensatz zu vielen weiteren Sprachen an es.  Dies liegt daran f# ausdrucksbasiert ist, und der letzte Ausdruck im Text einer Funktion der Rückgabewert ist.  Da `if.then.else` ist selbst ein Ausdruck, der Hauptteil der `then` Block oder im Textteil der `else` Block wird je nach den Eingabewert zurückgegeben werden.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Verschieben Sie den Skriptcode in der Implementierungsdatei

In den vorherigen Abschnitten in diesem Artikel veranschaulicht einen allgemeine ersten Schritt beim Schreiben von f#-Code: Schreiben einer anfänglichen Funktion und anschließend interaktiv mit FSI ausgeführt.  Dies wird als REPL-driven Development bezeichnet, in dem Textgröße für Replikation für "Lesen-auswerten-drucken-Schleife" steht.  Es ist eine hervorragende Möglichkeit zum Experimentieren mit Funktionalität, bis Sie etwas Arbeit haben.

Der nächste Schritt im REPL-driven Development ist für das Verschieben von Arbeitscode in einer f#-Implementierungsdatei.  Es kann dann vom F#-Compiler in eine Assembly kompiliert werden, die ausgeführt werden können.

Um zu beginnen, öffnen Sie `ClassLibraryDemo.fs`.  Sie werden bemerken, dass Code dort bereits in vorhanden ist.  Fahren Sie fort und löschen Sie die Definition der Klasse, aber belassen Sie unbedingt die [ `namespace` ](../language-reference/namespaces.md) Deklaration oben.

Als Nächstes erstellen Sie ein neues [ `module` ](../language-reference/modules.md) aufgerufen `PigLatin` , und kopieren Sie die `toPigLatin` Funktion als solche hinein:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Dies ist eine der vielen Arten, die Sie Funktionen in f#-Code und eine gängige Methode organisieren können, wenn Sie auch den Code von c# oder Visual Basic-Projekte aufrufen möchten.

Öffnen Sie als Nächstes die `Script.fsx` Datei erneut, und löschen Sie das gesamte `toPigLatin` funktionsfähig, aber stellen Sie sicher, dass die folgenden zwei Zeilen in der Datei:

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Die erste Zeile wird benötigt, um FSI scripting zum Laden `ClassLibraryDemo.fs`.  Die zweite Zeile ist eine Annehmlichkeit: Typrückschlussmodul ist optional, aber Sie benötigen, geben Sie `open ClassLibraryDemo` in einem FSI-Fenster, wenn Sie schalten möchten die `ToPigLatin` Moduls einbinden.

Rufen Sie als Nächstes im Fenster FSI-Funktion mit dem `PigLatin` -Modul, das Sie zuvor definiert:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Erfolgreich!  Sie erhalten die gleichen Ergebnisse wie vor, aber nun aus einer f#-Implementierungsdatei geladen.  Der Hauptunterschied ist, dass f#-Quelldateien in Assemblys kompiliert werden, die an einer beliebigen Stelle, nicht nur in FSI ausgeführt werden kann.

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
3. Überprüfen Sie, dass Sie den f#-Compiler und f# interactive über die Befehlszeile ohne einen vollständig qualifizierten Pfad verwenden können.  Können Sie dies tun, indem Sie Folgendes eingeben `fsc` in einer Befehlszeile für den f#-Compiler und `fsi` oder `fsharpi` für die Visual F#-tools für Windows und Mono auf Mac/Linux, bzw.
4. Wenn Sie ungültige Zeichen in Ihre Projektverzeichnisse haben, funktionieren möglicherweise nicht Ionide.  Benennen Sie Ihre Projektverzeichnisse aus, wenn dies der Fall ist.
5. Wenn keiner der Befehle Ionide arbeiten, überprüfen Sie Ihre [Visual Studio Code schlüsselbindungen](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) um festzustellen, ob Sie sie versehentlich überschreiben möchten.
6. Versuchen Sie es entfernen, wenn Ionide auf Ihrem Computer unterbrochen wird und keines der oben genannten wurde das Problem behoben, die `ionide-fsharp` -Verzeichnisses auf dem Computer und installieren Sie die Plug-in-Suite.

Ionide ist ein open Source-Projekt durch Mitglieder der f#-Community erstellt und verwaltet.  Bitte Probleme mitzuteilen und gerne an beitragen der [Ionide-von VSCode: FSharp-GitHub-Repository](https://github.com/ionide/ionide-vscode-fsharp).

Wenn Sie ein Problem beim Bericht haben, führen Sie die [die Anweisungen zum Abrufen der Protokolle zu verwenden, wenn Sie ein Problem melden](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

Sie können auch weitere Hilfe benötigen bitten, aus dem Ionide Entwickler und F#-Community in der [Ionide Gitter Kanal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu F#- und die Funktionen der Programmiersprache Auschecken [Tour von F#-](../tour.md).

## <a name="see-also"></a>Siehe auch

[Einführung in F#](../tour.md)

[F#-Sprachreferenz](../language-reference/index.md)

[Funktionen](../language-reference/functions/index.md)

[Module](../language-reference/modules.md)

[Namespaces](../language-reference/namespaces.md)

[Ionide-VSCode: FSharp](https://github.com/ionide/ionide-vscode-fsharp)
