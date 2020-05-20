---
title: Verwenden einer .NET Standard-Bibliothek in Visual Studio
description: Erstellen Sie eine .NET Core-Anwendung, die Member einer anderen Klassenbibliothek mit Visual Studio 2019 aufruft.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920458"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a>Verwenden einer .NET Standard-Bibliothek in Visual Studio

Nachdem Sie eine .NET Standard-Klassenbibliothek erstellt und getestet sowie eine Releaseversion der Bibliothek erstellt haben, besteht der nächste Schritt darin, diese für Aufrufer verfügbar zu machen. Dazu gibt es zwei Möglichkeiten:

- Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek als Projekt in Ihre Projektmappe einfügen.
- Wenn die Bibliothek öffentlich verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Fügen Sie der Projektmappe eine Konsolen-App hinzu, die auf ein .NET Standard-Bibliotheksprojekt verweist.
> - Erstellen Sie ein NuGet-Paket, das ein .NET Standard-Bibliotheksprojekt enthält.

## <a name="add-a-console-app-to-your-solution"></a>Hinzufügen einer Konsolen-App zur Projektmappe

Ebenso wie Sie unter [Testen einer .NET Standard-Bibliothek in Visual Studio](testing-library-with-visual-studio.md) Komponententests in dieselbe Projektmappe wie Ihre Klassenbibliothek einbezogen haben, können Sie Ihre Anwendung als Teil dieser Projektmappe einschließen. Angenommen, Sie können Ihre Klassenbibliothek in einer Konsolenanwendung verwenden, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:

1. Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie im Artikel [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.

1. Fügen Sie der Projektmappe eine neue .NET Core-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus. Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.

   1. Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein. Wählen Sie anschließend **Erstellen** aus.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü „Verweis hinzufügen“ in Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code:

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

Sie können die Anwendung, die diese Bibliothek verwendet, debuggen und veröffentlichen, indem Sie die Schritte unter [Debuggen Ihrer C# oder Visual Basic .NET Core Hello World-Anwendung mit Visual Studio](debugging-with-visual-studio.md) und [Veröffentlichen Ihrer .NET Core Hello World-Anwendung mit Visual Studio](publishing-with-visual-studio.md) ausführen.

## <a name="create-a-nuget-package"></a>Erstellen eines NuGet-Pakets

Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen. Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen. Um ein solches Paket zu erstellen, müssen Sie die .NET Core-CLI-Befehle verwenden:

1. Öffnen Sie ein Konsolenfenster.

   Geben Sie beispielsweise **Eingabeaufforderung** in das Suchfeld auf der Windows-Taskleiste ein. Wählen Sie die Desktop-App **Eingabeaufforderung** aus, oder drücken Sie die **EINGABETASTE**, wenn sie in den Suchergebnissen bereits ausgewählt ist.

1. Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek. Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei (*StringLibrary.csproj* oder *StringLibrary.vbproj*).

1. Führen Sie den Befehl [dotnet pack](../tools/dotnet-pack.md) aus, um ein Paket mit der Erweiterung *.nupkg* zu generieren:

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > Wenn sich das Verzeichnis, das die Datei *dotnet.exe* enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.

Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit der .NET Core-CLI](../deploying/creating-nuget-packages.md).
