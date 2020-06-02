---
title: Erstellen einer .NET Standard-Klassenbibliothek in Visual Studio
description: Erfahren Sie, wie Sie eine .NET Standard-Klassenbibliothek mit Visual Studio erstellen.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 2afe11ad75fc36a67efed48d56dbafb11bceaf2a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005248"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a>Tutorial: Erstellen einer .NET-Standardbibliothek in Visual Studio

Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt. Wenn Sie die Klassenbibliothek fertig stellen, können Sie entscheiden, ob Sie sie als Drittanbieterkomponente verteilen oder als Komponente mit einer oder mehreren Anwendungen in ein Paket einbeziehen möchten.

> [!NOTE]
> Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET Standard](../../standard/net-standard.md).

In diesem Tutorial erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält. Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String>-Klasse.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019 Version 16.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**. Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.

  Weitere Informationen finden Sie im Abschnitt [Installieren mit Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) des Artikels [Installieren des .NET Core SDK](../install/sdk.md?pivots=os-windows).

## <a name="create-a-visual-studio-solution"></a>Erstellen einer Visual Studio-Projektmappe

Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern. Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt. Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.

So erstellen Sie eine leere Projektmappe:

1. Öffnen Sie Visual Studio.

2. Wählen Sie im Startfenster **Neues Projekt erstellen** aus.

3. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Projektmappe** in das Suchfeld ein. Wählen Sie die Vorlage **Leere Projektmappe** aus, und klicken Sie dann auf **Weiter**.

   ![Vorlage „Leere Projektmappe“ in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **ClassLibraryProjects** ein. Wählen Sie dann **Erstellen** aus.

## <a name="create-a-class-library-project"></a>Erstellen eines Klassenbibliotheksprojekts

1. Fügen Sie der Projektmappe ein neues .NET Standard-Klassenbibliotheksprojekt mit dem Namen „StringLibrary“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** **library** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus. Wählen Sie die Vorlage **Klassenbibliothek (.NET Standard)** aus, und wählen Sie dann **Weiter**aus.

   1. Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibrary** ein. Wählen Sie anschließend **Erstellen** aus.

1. Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET Standard als Ziel verwendet. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Bibliotheksprojekt, und klicken Sie dann auf **Eigenschaften**. Das Textfeld **Zielframework** zeigt dann, dass .NET Standard 2.0 als Ziel verwendet wird.

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/library-project-properties.png)

1. Wenn Sie Visual Basic verwenden, löschen Sie den Text im Textfeld **Stammnamespace**.

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/vb/library-project-properties.png)

   Für jedes Projekt erstellt Visual Basic automatisch einen Namespace, der dem Projektnamen entspricht. In diesem Tutorial definieren Sie einen Namespace der obersten Ebene mithilfe des Schlüsselworts [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) in der Codedatei.

1. Ersetzen Sie den Code im Codefenster für *Class1.cs* oder *Class1.vb* durch den folgenden Code, und speichern Sie die Datei. Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.

   [!code-csharp[](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]
   [!code-vb[](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`. Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt. Der Unicode-Standard unterscheidet Groß- und Kleinschreibung. Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus, um zu bestätigen, dass das Projekt ohne Fehler kompiliert wird.

## <a name="add-a-console-app-to-the-solution"></a>Hinzufügen einer Konsolen-App zur Projektmappe

Verwenden Sie die Klassenbibliothek in einer Konsolenanwendung, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen der Zeichenfolge ein Großbuchstabe ist.

1. Fügen Sie der Projektmappe eine neue .NET Core-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.

   1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

   1. Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.

   1. Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.

   1. Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein. Wählen Sie dann **Erstellen** aus.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek. Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.

   ![Kontextmenü „Verweis hinzufügen“ in Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** das Projekt **StringLibrary** und dann **OK** aus.

   ![Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary](media/library-with-visual-studio/manage-project-references.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code.

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die **EINGABETASTE** drücken, und drücken Sie dann die **EINGABETASTE**, um das Programm zu beenden.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Konsolenfenster, in dem ShowCase ausgeführt wird":::

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Projektmappe erstellt, ein Bibliotheksprojekt hinzugefügt und ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet. Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.

> [!div class="nextstepaction"]
> [Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio](testing-library-with-visual-studio.md)
