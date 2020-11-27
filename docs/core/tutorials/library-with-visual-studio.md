---
title: Erstellen einer .NET-Klassenbibliothek mit Visual Studio
description: Hier erfahren Sie, wie Sie eine .NET-Klassenbibliothek mit Visual Studio erstellen.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperfq1
ms.openlocfilehash: 3af08b5a92c61f29a3700a3417043170f41407bc
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916149"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio"></a>Tutorial: Erstellen einer .NET-Klassenbibliothek mit Visual Studio

In diesem Tutorial erstellen Sie eine einfache Klassenbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.

Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Wenn die Bibliothek auf .NET Standard 2.0 ausgelegt ist, kann sie von jeder .NET-Implementierung (einschließlich .NET Framework) aufgerufen werden, die .NET Standard 2.0 unterstützt. Wenn die Bibliothek auf .NET 5 ausgelegt ist, kann sie von jeder Anwendung aufgerufen werden, die auf .NET 5 ausgerichtet ist. In diesem Tutorial erfahren Sie, wie Sie .NET 5 als Zielversion verwenden.

Wenn Sie eine Klassenbibliothek erstellen, können Sie diese als NuGet-Paket oder als mit der zugehörigen Anwendung gebündelte Komponente ausliefern.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019 Version 16.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung** Das .NET 5.0 SDK wird automatisch installiert, wenn Sie diese Workload auswählen. In diesem Tutorial wird davon ausgegangen, dass Sie die Option **Show all .NET Core templates in the New project** (Alle .NET Core-Vorlagen im Dialogfeld „Neues Projekt“ anzeigen) wie im [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio](with-visual-studio.md) gezeigt aktiviert haben.

## <a name="create-a-solution"></a>Erstellen einer Projektmappe

Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern. Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt. Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.

So erstellen Sie eine leere Projektmappe:

1. Starten Sie Visual Studio.

2. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

3. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Projektmappe** in das Suchfeld ein. Wählen Sie die Vorlage **Leere Projektmappe** aus, und klicken Sie dann auf **Weiter**.

   :::image type="content" source="media/library-with-visual-studio/blank-solution.png" alt-text="Vorlage „Leere Projektmappe“ in Visual Studio":::

4. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **ClassLibraryProjects** ein. Wählen Sie dann **Erstellen** aus.

## <a name="create-a-class-library-project"></a>Erstellen eines Klassenbibliotheksprojekts

1. Fügen Sie ein neues .NET-Klassenbibliotheksprojekt namens „StringLibrary“ zur Projektmappe hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** **library** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus. Wählen Sie die Vorlage **Klassenbibliothek** aus, und klicken Sie dann auf **Weiter**.

   1. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibrary** ein, und klicken Sie anschließend auf **Weiter**.

   1. Wählen Sie auf der Seite **Zusätzliche Informationen** die Option **.NET 5.0 (aktuell)** aus, und klicken Sie dann auf **Erstellen**.

1. Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET als Ziel verwendet. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Bibliotheksprojekt, und klicken Sie dann auf **Eigenschaften**. Das Textfeld **Zielframework** zeigt dann, dass .NET 5.0 als Ziel verwendet wird.

1. Wenn Sie Visual Basic verwenden, löschen Sie den Text im Textfeld **Stammnamespace**.

   :::image type="content" source="./media/library-with-visual-studio/vb/library-project-properties.png" alt-text="Projekteigenschaften für die Klassenbibliothek":::

   Für jedes Projekt erstellt Visual Basic automatisch einen Namespace, der dem Projektnamen entspricht. In diesem Tutorial definieren Sie einen Namespace der obersten Ebene mithilfe des Schlüsselworts [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) in der Codedatei.

1. Ersetzen Sie den Code im Codefenster für *Class1.cs* oder *Class1.vb* durch den folgenden Code, und speichern Sie die Datei. Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`. Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt. Der Unicode-Standard unterscheidet Groß- und Kleinschreibung. Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.

   Die Methode `StartsWithUpper` wird als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md) implementiert, damit sie wie ein Member der Klasse <xref:System.String> aufgerufen werden kann.

1. Klicken Sie auf der Menüleiste auf **Erstellen** > **Projektmappe erstellen**, oder drücken Sie <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>B</kbd>, um zu bestätigen, dass das Projekt ohne Fehler kompiliert wird.

## <a name="add-a-console-app-to-the-solution"></a>Hinzufügen einer Konsolen-App zur Projektmappe

Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet. Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.

1. Fügen Sie der Projektmappe eine neue .NET-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.

   1. Wählen Sie die Vorlage **Konsolenanwendung** aus, und klicken Sie dann auf **Weiter**.

   1. Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein. Wählen Sie anschließend **Weiter** aus.

   1. Wählen Sie auf der Seite **Zusätzliche Informationen** im Feld **Zielframework** die Option **.NET 5.0 (aktuell)** aus. Wählen Sie dann **Erstellen** aus.

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.

## <a name="add-a-project-reference"></a>Hinzufügen eines Projektverweises

Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek. Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.

   :::image type="content" source="media/library-with-visual-studio/add-reference-context-menu.png" alt-text="Kontextmenü „Verweis hinzufügen“ in Visual Studio":::

1. Wählen Sie im Dialogfeld **Verweis-Manager** das Projekt **StringLibrary** und dann **OK** aus.

   :::image type="content" source="media/library-with-visual-studio/manage-project-references.png" alt-text="Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary":::

## <a name="run-the-app"></a>Ausführen der App

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

   :::image type="content" source="media/library-with-visual-studio/set-startup-project-context-menu.png" alt-text="Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts":::

1. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen zu kompilieren und auszuführen.

   :::image type="content" source="media/library-with-visual-studio/visual-studio-project-toolbar.png" alt-text="Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“":::

1. Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Konsolenfenster, in dem ShowCase ausgeführt wird":::

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Entwickeln von Bibliotheken mit der .NET-CLI](libraries.md)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Klassenbibliothek erstellt. Im nächsten Tutorial erfahren Sie, wie Sie Komponententests für die Klassenbibliothek ausführen.

> [!div class="nextstepaction"]
> [Durchführen eines Komponententests für eine .NET-Klassenbibliothek mit Visual Studio](testing-library-with-visual-studio.md)

Alternativ können Sie die automatisierten Komponententests auch überspringen und sich damit beschäftigen, wie die Bibliothek durch Erstellen eines NuGet-Pakets freigegeben werden kann:

> [!div class="nextstepaction"]
> [Erstellen und Veröffentlichen eines Pakets mithilfe von Visual Studio](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

Stattdessen können Sie sich auch über das Veröffentlichen einer Konsolen-App informieren. Wenn Sie die Konsolen-App aus der Projektmappe veröffentlichen, die Sie in diesem Tutorial erstellt haben, wird die Klassenbibliothek als *DLL*-Datei veröffentlicht.

> [!div class="nextstepaction"]
> [Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio](publishing-with-visual-studio.md)
