---
title: Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017 | Microsoft-Dokumentation
description: Erfahren Sie, wie Sie die Elemente in einer Klassenbibliothek mit Visual Studio 2017 aufrufen.
keywords: .NET Core, .NET Core-Klassenbibliothek, .NET Standard, .NET Standard-Klassenbibliotheksdistribution
author: BillWagner
ms.author: wiwang
ms.date: 04/17/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: d7b94076-1108-4174-94e7-a18f00072bb7
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 5ad07e4116c75eb9b9d513c2a4fe43dfe62660d5
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---

<a id="consuming-a-class-library-with-net-core-in-visual-studio-2017" class="xliff"></a>

# Verarbeiten einer Klassenbibliothek mit .NET Core in Visual Studio 2017

Nachdem Sie die Schritte in [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio.md) und [Testen einer Klassenbibliothek in .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) zum Erstellen und Testen Ihrer Klassenbibliothek ausgeführt und eine Releaseversion der Bibliothek erstellt haben, besteht der nächste Schritt darin, diese für Aufrufer verfügbar zu machen. Dazu gibt es zwei Möglichkeiten:

* Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek als Projekt in Ihre Projektmappe einfügen.

* Wenn die Bibliothek allgemein verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.

<a id="including-a-library-as-a-project-in-a-solution" class="xliff"></a>

## Einschließen einer Bibliothek als Projekt in einer Projektmappe

Ebenso wie Sie Komponententests in dieselbe Projektmappe eingeschlossen haben wie Ihre Klassenbibliothek, können Sie Ihre Anwendung als Teil dieser Projektmappe einschließen. Angenommen, Sie können Ihre Klassenbibliothek in einer Konsolenanwendung verwenden, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:

1. Öffnen Sie die Projektmappe `ClassLibraryProjects`, die Sie im Thema [Erstellen einer C#-Klassenbibliothek mit .NET Core in Visual Studio 2017](./library-with-visual-studio.md). Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** den Knoten **.NET Core**, gefolgt von der Projektvorlage **Konsolen-App (.NET Core)**. Geben Sie im Textfeld **Name** „ShowCase“ ein, und klicken Sie auf die Schaltfläche **OK**.

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/consuming-library-with-visual-studio/addnewproject.png)

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.

   ![Kontextmenü „ShowCase“](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek. Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Verweis hinzufügen** aus.

   ![Kontextmenü „ShowCase-Abhängigkeiten“](./media/consuming-library-with-visual-studio/addreference.png)

1. Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.

   ![Verweis-Manager](./media/consuming-library-with-visual-studio/referencemanager.png)

1. Ersetzen Sie im Codefenster für die Datei *Program.cs* den gesamten Code durch diesen:

 [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs#1)]

   Der Code verwendet die Eigenschaft [Console.WindowHeight](xref:System.Console.WindowHeight), um die Anzahl der Zeilen im Konsolenfenster zu ermitteln. Immer dann, wenn die Eigenschaft [Console.CursorTop](xref:System.Console.CursorTop) größer oder gleich der Anzahl von Zeilen im Konsolenfenster ist, löscht der Code das Konsolenfenster und zeigt dem Benutzer eine Meldung an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird das Konsolenfenster geschlossen, und die Anwendung wird beendet.

1. Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren. Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.

   ![Bild](./media/consuming-library-with-visual-studio/toolbar.png)

Sie können die Anwendung, die diese Bibliothek verwendet, debuggen und schließlich veröffentlichen, indem Sie die Schritte in [Debuggen Ihrer C#-Anwendung „Hello World“ mit Visual Studio 2017](debugging-with-visual-studio.md) und [Veröffentlichen Ihrer Hello World-Anwendung mit Visual Studio 2017](publishing-with-visual-studio.md) ausführen.

<a id="distributing-the-library-in-a-nuget-package" class="xliff"></a>

## Verteilen der Bibliothek in einem NuGet-Paket

Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen. Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen. Um ein NuGet-Paket zu erstellen, verwenden Sie das [`dotnet`-Befehlszeilenprogramm ](../../core/tools/dotnet.md):

1. Öffnen Sie ein Konsolenfenster. Geben Sie z.B. im Textfeld **Frag mich etwas** in der Windows-Taskleiste `Command Prompt` (oder `cmd` als Abkürzung) ein, und öffnen Sie ein Konsolenfenster, indem Sie entweder die Desktopanwendung **Eingabeaufforderung** auswählen oder die EINGABETASTE drücken, wenn die Anwendung in den Suchergebnissen angezeigt wird.

1. Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek. Sofern Sie nicht den typischen Dateispeicherort neu konfiguriert haben, befindet sich dieser im Verzeichnis *Dokumente\Visual Studio 2017\Projekte\ClassLibraryProjects\StringLibrary*. Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei, *StringLibrary.csproj*.

1. Führen Sie den Befehl `dotnet pack --no-build` aus. Das Hilfsprogramm `dotnet` generiert ein Paket mit der Erweiterung *.nupkg*.

   > [!TIP]
   > Wenn sich das Verzeichnis, das die Datei *dotnet.exe* enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.

Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit plattformübergreifenden Tools](../../core/deploying/creating-nuget-packages.md).

