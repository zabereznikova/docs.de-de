---
title: Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie die Elemente in einer Klassenbibliothek mit Visual Studio 2017 aufrufen.
keywords: .NET Core, .NET Core-Klassenbibliothek, .NET Standard, .NET Standard-Klassenbibliotheksdistribution
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: d7b94076-1108-4174-94e7-a18f00072bb7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0b42eeb0149feec09ddacba98383da3abd53bb5e
ms.lasthandoff: 03/13/2017

---

# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a>Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017 #

Nachdem Sie die Schritte in [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio-2017.md) und [Testen einer Klassenbibliothek in .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) zum Erstellen und Testen Ihrer Klassenbibliothek ausgeführt und eine Releaseversion der Bibliothek erstellt haben, besteht der nächste Schritt darin, diese für Aufrufer verfügbar zu machen. Dazu gibt es zwei Möglichkeiten:

- Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek einfach als Projekt in Ihre Projektmappe einfügen.

- Wenn die Bibliothek allgemein verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Einschließen einer Bibliothek als Projekt in einer Projektmappe ##

Ebenso wie wir Komponententests in dieselbe Projektmappe eingeschlossen haben wie unsere Klassenbibliothek, können wir unsere Anwendung als Teil dieser Projektmappe einschließen. Angenommen, wir verwenden unsere Klassenbibliothek in einer Konsolenanwendung, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:

1. Öffnen Sie die im Thema [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio-2017.md) erstellte `ClassLibraryProjects`-Projektmappe. Öffnen Sie dann im Projektmappen-Explorer das Kontextmenü für den Knoten **ClassLibraryProjects**, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neues Projekt hinzufügen** die Knoten **Visual C#** und **.NET Core**, und wählen Sie die Projektvorlage **Konsolenanwendung (.NET Core)** aus, wie nachfolgend dargestellt.

   ![Bild](./media/use-library.jpg)

1. Geben Sie im Textfeld **Name** `ShowCase` ein, und klicken Sie auf **OK**.

1. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den Projektknoten **ShowCase**, und wählen Sie **Als Startprojekt festlegen** aus.

1. Zunächst hat unser Projekt keinen Zugriff auf unsere Klassenbibliothek. Um das Aufrufen von Methoden in unserer Klassenbibliothek zuzulassen, öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Knoten **Abhängigkeiten** im Projekt **ShowCase**. Wählen Sie anschließend **Verweis hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Verweis-Manager** den Eintrag **StringLibrary** – unser Klassenbibliotheksprojekt – aus (siehe Darstellung unten), und klicken Sie dann auf **OK**.

   ![Bild](./media/add-lib-ref.jpg)

1. Ersetzen Sie im Codefenster für die Datei „program.cs“ den gesamten Code durch diesen:

 [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs#1)]

   Der Code verwendet die Eigenschaft [Console.WindowHeight](xref:System.Console.WindowHeight), um zu ermitteln, wie viele Zeilen das Konsolenfenster umfasst. Immer dann, wenn die Eigenschaft [Console.CursorTop](xref:System.Console.CursorTop) größer oder gleich der Gesamtzahl von Zeilen im Konsolenfenster ist, löscht der Code das Konsolenfenster und zeigt dem Benutzer erneut eine Meldung an.

   Das Programm selbst fordert den Benutzer lediglich zur Eingabe einer Zeichenfolge auf. Anschließend zeigt es an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die **EINGABETASTE** drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren (siehe nachfolgende Abbildung).

   ![Bild](./media/showcase-toolbar.jpg)

1. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

Die Anwendung, die diese Bibliothek verwendet, kann anschließend gedebuggt und schließlich veröffentlicht werden, indem Sie die Schritte in [Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017](debugging-with-visual-studio-2017.md) und [Veröffentlichen Ihrer Hello World-Anwendung mit Visual Studio 2017](publishing-with-visual-studio-2017.md) ausführen.

## <a name="distributing-the-library-in-a-nuget-package"></a>Verteilen der Bibliothek in einem NuGet-Paket ##

Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen. Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen. Um ein NuGet-Paket zu erstellen, verwenden Sie das [`dotnet.exe`-Befehlszeilenprogramm ](../../core/tools/dotnet.md) wie folgt:

1. Öffnen Sie ein Konsolenfenster. Geben Sie beispielsweise im Textfeld **Frag mich etwas** in der Windows-Taskleiste `Command Prompt` ein, und wählen Sie dann die Desktop-App **Eingabeaufforderung** aus, um das Konsolenfenster zu öffnen.

1. Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek. Sofern Sie nicht den Dateispeicherort neu konfiguriert haben, befindet sich dieses typischerweise im `Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary`-Verzeichnis. Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei, `StringLibrary.csproj`.

1. Führen Sie den Befehl `dotnet.exe pack --no-build` aus. Das Hilfsprogramm `dotnet.exe` generiert ein Paket mit der Erweiterung .nupkg.

   > [!TIP]
   > Wenn sich das Verzeichnis, das die Datei `dotnet.exe` enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.

Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit plattformübergreifenden Tools](../../core/deploying/creating-nuget-packages.md).
