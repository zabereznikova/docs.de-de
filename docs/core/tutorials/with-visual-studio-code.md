---
title: Erste Schritte mit c# und Visual Studio Code - C#-Handbuch
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
keywords: "C#, erste Schritte, Erwerb, Installation, Visual Studio Code, plattformübergreifend"
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Erste Schritte mit C# und Visual Studio Code

.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden. Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.

## <a name="prerequisites"></a>Erforderliche Komponenten

1. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
2. Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/download/core).
3. Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) aus dem Visual Studio Code Marketplace.

## <a name="hello-world"></a>Hello World

Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:

1. Öffnen Sie ein Projekt:

    * Öffnen Sie Visual Studio Code.
    * Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.
    * Wählen Sie **Datei** > **Ordner öffnen** über das Hauptmenü auf den Ordner zu öffnen, die Sie möchten des C#-Projekts, und klicken Sie auf **Ordner auswählen**. In unserem Beispiel erstellen wir einen Ordner für unsere Projekt mit dem Namen *HelloWorld*.

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. Initialisieren Sie ein C#-Projekt:
    * Öffnen Sie das integrierte Terminal aus Visual Studio-Code, indem Sie auswählen **Ansicht** > **integrierten Terminal** über das Hauptmenü.
    * Geben Sie im Terminalfenster `dotnet new console` ein.
    * Dieser Befehl erstellt eine `Program.cs` Datei im Ordner mit einem einfache "Hello World"-Programm, der bereits geschrieben werden, zusammen mit einer C#-Projektdatei mit dem Namen `HelloWorld.csproj`.

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnetnew.png)

3. Lösen Sie die Buildobjekte auf:

    * Für **.NET Core 1.x**, Typ `dotnet restore`. Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.

      ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Führen Sie das „Hello World“-Programm aus:

    * Geben Sie `dotnet run` ein. 

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnetrun.png)

Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.

## <a name="debug"></a>Debuggen

1. Öffnen Sie *Program.cs*, indem Sie darauf klicken. Beim ersten einer C#-Datei in Visual Studio Code öffnen [OmniSharp](http://www.omnisharp.net/) im Editor lädt.

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/opencs.png)

2. Visual Studio-Code sollten Sie aufgefordert, die fehlenden Ressourcen zum Erstellen und Debuggen der app hinzufügen. Wählen Sie **Ja**. 

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.

    ![Öffnen der Registerkarte „Debuggen“](media/with-visual-studio-code/opendebug.png)

4. Suchen Sie den grünen Pfeil am oberen Rand des Fensters. Stellen Sie sicher, dass in der Dropdownliste die Option `.NET Core Launch (console)` ausgewählt ist.

    ![Auswählen von .NET Core](media/with-visual-studio-code/selectcore.png)

5. Fügen Sie einen Haltepunkt zu Ihrem Projekt durch Klicken auf die **Editor Rand**, dies ist der Speicherplatz auf der linken Seite von der Zeilennummern im Editor neben der Zeile 9.

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/setbreakpoint.png)

6. Wählen Sie zum Starten des Debugvorgangs <kbd>F5</kbd> oder den grünen Pfeil. Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.
    * Beim Debuggen, können Sie die lokalen Variablen in der oberen linken Bereich anzeigen oder die Debug-Konsole.

    ![Ausführen und Debuggen](media/with-visual-studio-code/rundebug.png)

7. Wählen Sie im oberen Bereich den grünen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.

> [!TIP] 
> Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="see-also"></a>Siehe auch
[Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)   
[Debuggen in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)
