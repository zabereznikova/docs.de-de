---
title: Erstellen einer .NET-Klassenbibliothek in Visual Studio für Mac
description: Hier erfahren Sie, wie Sie eine .NET-Klassenbibliothek mit Visual Studio für Mac erstellen.
ms.date: 11/30/2020
ms.openlocfilehash: 1b6b26de06d18d505fa6dde3ff9779a3dab3f1e6
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599300"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-for-mac"></a>Tutorial: Erstellen einer .NET-Klassenbibliothek in Visual Studio für Mac

In diesem Tutorial erstellen Sie eine einfache Klassenbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.

Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Wenn die Bibliothek auf .NET Standard 2.0 ausgelegt ist, kann sie von jeder .NET-Implementierung (einschließlich .NET Framework) aufgerufen werden, die .NET Standard 2.0 unterstützt. Wenn die Bibliothek auf .NET 5 ausgelegt ist, kann sie von jeder Anwendung aufgerufen werden, die auf .NET 5 ausgerichtet ist. In diesem Tutorial erfahren Sie, wie Sie .NET 5 als Zielversion verwenden.

> [!NOTE]
> Ihr Feedback ist uns sehr wichtig. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
>
> - Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Einreichen eines Fehlerberichts geöffnet. Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://aka.ms/feedback/report?space=41) verfolgen.
> - Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://aka.ms/feedback/suggest?space=41).

## <a name="prerequisites"></a>Voraussetzungen

* [Installieren von Visual Studio für Mac Version 8.8 oder höher](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Wählen Sie die Option zum Installieren von .NET Core aus. Die Installation von Xamarin ist für die Entwicklung mit .NET optional. Weitere Informationen finden Sie in den folgenden Ressourcen:

  * [Tutorial: Installieren von Visual Studio für Mac](/visualstudio/mac/installation).
  * [Unterstützte macOS-Versionen](../install/macos.md)
  * [Von Visual Studio für Mac unterstützte .NET-Versionen](/visualstudio/mac/net-core-support).

## <a name="create-a-solution-with-a-class-library-project"></a>Erstellen einer Projektmappe mit einem Klassenbibliotheksprojekt

Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt. Erstellen Sie eine Projektmappe und darin ein Klassenbibliotheksprojekt. Sie fügen später der gleichen Projektmappe weitere verwandte Projekte hinzu.

1. Starten Sie Visual Studio für Mac.

1. Wählen Sie im Startfenster **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Vorlage für neues Projekt auswählen** die Option **Web und Konsole** > **Bibliothek** > **Klassenbibliothek** aus, und wählen Sie dann **Weiter** aus.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Dialogfeld Neues Projekt":::

1. Wählen Sie im Dialogfeld **Neue Klassenbibliothek konfigurieren** die Option **NET 5.0** und dann **Weiter** aus.

1. Nennen Sie die Projektmappe „StringLibrary“ und die Projektmappe „ClassLibraryProjects“. Lassen Sie **Projektverzeichnis im Projektmappenverzeichnis erstellen** aktiviert. Wählen Sie **Erstellen** aus.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Visual Studio für Mac, Optionen im Dialogfeld „Neues Projekt“":::

1. Wählen Sie im Hauptmenü **Ansicht** > **Projektmappe** und dann das Andocksymbol aus, um das Pad geöffnet zu halten.

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Andocksymbol für Pad „Projektmappe“":::

1. Erweitern Sie im Pad **Projektmappe** den `StringLibrary`-Knoten, um die von der Vorlage bereitgestellte Klassendatei *Class1.cs* anzuzeigen. Klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Datei. Wählen Sie im Kontextmenü **Umbenennen** aus, und benennen Sie die Datei in *StringLibrary.cs* um. Öffnen Sie die Datei und ersetzen Sie den Inhalt durch den folgenden Code:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. Drücken Sie <kbd>⌘</kbd><kbd>S</kbd> (<kbd>BEFEHL</kbd>+<kbd>S</kbd>), um die Datei zu speichern.

1. Wählen Sie am unteren Rand des IDE-Fensters **Fehler** aus, um den Bereich **Fehler** zu öffnen. Wählen Sie die Schaltfläche **Buildausgabe** aus.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Unterer Rand der IDE mit Schaltfläche „Fehler“ in Visual Studio für Mac":::

1. Klicken Sie im Menü auf **Build** > **Build All** (Erstellen > Alle erstellen).

   Die Projektmappe wird erstellt. Im Bereich „Buildausgabe“ wird angezeigt, dass der Build erfolgreich erstellt wurde.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Visual Studio für Mac, Buildausgabebereich im Bereich „Fehler“ mit Meldung, dass der Build erfolgreich war":::

## <a name="add-a-console-app-to-the-solution"></a>Hinzufügen einer Konsolen-App zur Projektmappe

Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet. Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.

1. Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Projektmappe `ClassLibraryProjects`. Fügen Sie ein neues **Konsolenanwendungsprojekt** hinzu, indem Sie die Vorlage aus den Vorlagen unter **Web und Konsole** > **App** und dann **Weiter** auswählen.

1. Wählen Sie **.NET 5.0** als **Zielframework** und anschließend **Weiter** aus.

1. Geben Sie dem Projekt den Namen **ShowCase**. Wählen Sie **Erstellen** aus, um das Projekt in der Projektmappe zu erstellen.

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Projekt „ShowCase“ hinzufügen":::

1. Öffnen Sie die Datei *Program.cs*. Ersetzen Sie den Code durch den folgenden Code:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

## <a name="add-a-project-reference"></a>Hinzufügen eines Projektverweises

Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek. Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.

1. Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> im neuen Projekt **ShowCase** auf den Knoten **Abhängigkeiten**. Wählen Sie im Kontextmenü **Verweis hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Verweise** das Projekt **StringLibrary** und dann **OK** aus.

## <a name="run-the-app"></a>Ausführen der App

1. Klicken Sie bei gedrückter <kbd>STRG-TASTE</kbd> auf das Projekt **ShowCase**, und wählen Sie im Kontextmenü **Projekt ausführen** aus.

1. Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken. Drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Visual Studio für Mac-Konsolenfenster, das Ihre App bei der Ausführung zeigt":::

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Entwickeln von Bibliotheken mit der .NET-CLI](libraries.md)
* [Versionsanmerkungen für Visual Studio 2019 für Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)
* [.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Projektmappe und ein Bibliotheksprojekt erstellt sowie ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet. Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.

> [!div class="nextstepaction"]
> [Testen einer .NET-Klassenbibliothek in Visual Studio für Mac](testing-library-with-visual-studio-mac.md)
