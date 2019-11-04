---
title: Verwenden einer .NET Standard-Bibliothek in Visual Studio 2017
description: Erstellen Sie eine .NET Core-Anwendung, die Member einer anderen Klassenbibliothek mit Visual Studio 2017 aufruft.
author: BillWagner
ms.author: wiwagn
ms.date: 06/05/2018
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: cfceb7ba384a28a09f172032f6edb6f5e495e9c0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420902"
---
# <a name="consume-a-net-standard-library-in-visual-studio-2017"></a>Verwenden einer .NET Standard-Bibliothek in Visual Studio 2017

Nachdem Sie eine .NET Standard-Klassenbibliothek anhand der unter [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](./library-with-visual-studio.md) oder [Erstellen einer Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) beschriebenen Schritte erstellt und Sie in [Testen einer Klassenbibliothek mit .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) getestet und eine Releaseversion der Bibliothek erstellt haben, können Sie sie im nächsten Schritt für Aufrufer verfügbar machen. Dazu gibt es zwei Möglichkeiten:

* Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek als Projekt in Ihre Projektmappe einfügen.

* Wenn die Bibliothek allgemein verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Einschließen einer Bibliothek als Projekt in einer Projektmappe

Ebenso wie Sie Komponententests in dieselbe Projektmappe eingeschlossen haben wie Ihre Klassenbibliothek, können Sie Ihre Anwendung als Teil dieser Projektmappe einschließen. Angenommen, Sie können Ihre Klassenbibliothek in einer Konsolenanwendung verwenden, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie im Thema [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio.md). Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen**, erweitern Sie den Knoten **Visual C#** , und klicken Sie auf den Knoten .**NET Core** und anschließend auf die Projektvorlage **Konsolen-App (.NET Core)** . Geben Sie im Textfeld **Name** „ShowCase“ ein, und klicken Sie auf die Schaltfläche **OK**.

   ![Visual Studio, Dialogfeld „Neues Projekt hinzufügen“ – C#](./media/consuming-library-with-visual-studio/add-new-project-dialog.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts – C#](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Visual Studio-Kontextmenü „Projektverweis hinzufügen“ – C#](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Visual Studio, Dialogfeld „Verweise verwalten“ – C#](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* den gesamten Code durch diesen:

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“ – C#](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie im Thema [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017 (Erstellen einer C#-Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017)](vb-library-with-visual-studio.md). Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen**, erweitern Sie den Knoten **Visual Basic**, und klicken Sie auf den Knoten .**NET Core** und anschließend auf die Projektvorlage **Konsolen-App (.NET Core)** . Geben Sie im Textfeld **Name** „ShowCase“ ein, und klicken Sie auf die Schaltfläche **OK**.

   ![Visual Studio, Dialogfeld „Neues Projekt hinzufügen“ – Visual Basic](./media/consuming-library-with-visual-studio/add-new-vb-project-dialog.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus. 

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts – Visual Basic](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Visual Studio-Kontextmenü „Projektverweis hinzufügen“ – Visual Basic](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Visual Studio, Dialogfeld „Verweise verwalten“ – Visual Basic](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.vb* den gesamten Code durch diesen:

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Debuggen auf der Symbolleiste – Visual Basic](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

---

Sie können die Anwendung, die diese Bibliothek verwendet, debuggen und schließlich veröffentlichen, indem Sie die Schritte in [Debuggen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](debugging-with-visual-studio.md) und [Veröffentlichen Ihrer „Hallo Welt“-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md) ausführen.

## <a name="distributing-the-library-in-a-nuget-package"></a>Verteilen der Bibliothek in einem NuGet-Paket

Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen. Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen. Um ein NuGet-Paket zu erstellen, verwenden Sie das [`dotnet`-Befehlszeilenprogramm ](../tools/dotnet.md):

1. Öffnen Sie ein Konsolenfenster. Geben Sie z.B. im Textfeld **Frag mich etwas** in der Windows-Taskleiste `Command Prompt` (oder `cmd` als Abkürzung) ein, und öffnen Sie ein Konsolenfenster, indem Sie entweder die Desktopanwendung **Eingabeaufforderung** auswählen oder die EINGABETASTE drücken, wenn die Anwendung in den Suchergebnissen angezeigt wird.

1. Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek. Sofern Sie nicht den typischen Dateispeicherort neu konfiguriert haben, befindet sich dieser im Verzeichnis *Dokumente\Visual Studio 2017\Projekte\ClassLibraryProjects\StringLibrary*. Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei, *StringLibrary.csproj*.

1. Führen Sie den Befehl `dotnet pack --no-build` aus. Das Hilfsprogramm `dotnet` generiert ein Paket mit der Erweiterung *.nupkg*.

   > [!TIP]
   > Wenn sich das Verzeichnis, das die Datei *dotnet.exe* enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.

Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit plattformübergreifenden Tools](../deploying/creating-nuget-packages.md).
