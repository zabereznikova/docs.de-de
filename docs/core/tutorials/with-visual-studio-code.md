---
title: Erste Schritte mit C# und Visual Studio Code (C#-Handbuch)
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 321edcebdea141b7290fa57b47c8d9fc91d3521c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668222"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Erste Schritte mit C# und Visual Studio Code

.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden. Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.

## <a name="prerequisites"></a>Erforderliche Komponenten

1. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
2. Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/download/core).
3. Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) für Visual Studio Code. Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).

## <a name="hello-world"></a>Hello World

Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:

1. Öffnen Sie ein Projekt:

    * Öffnen Sie Visual Studio Code.
    * Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.
    * Klicken Sie im Hauptmenü auf **Datei** > **Open Folder** (Ordner öffnen), um den Ordner zu öffnen, in dem Sie Ihr C#-Projekt speichern möchten, und klicken Sie auf **Ordner auswählen**. Für dieses Beispiel wird ein Ordner namens *HelloWorld* für das Projekt erstellt.

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. Initialisieren Sie ein C#-Projekt:
    * Öffnen Sie das integrierte Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Integriertes Terminal** klicken.
    * Geben Sie im Terminalfenster `dotnet new console` ein.
    * Durch diesen Befehl wird eine `Program.cs`-Datei in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hallo Welt“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens `HelloWorld.csproj` erstellt.

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnetnew.png)

3. Lösen Sie die Buildobjekte auf:

    * Geben Sie für **.NET Core 1.x** den Befehl `dotnet restore` ein. Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.

      ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Führen Sie das „Hello World“-Programm aus:

    * Geben Sie `dotnet run` ein.

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnetrun.png)

Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.

## <a name="debug"></a>Debug

1. Öffnen Sie *Program.cs*, indem Sie darauf klicken. Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](http://www.omnisharp.net/) im Editor geladen.

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/opencs.png)

2. Visual Studio Code fordert Sie dazu auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen. Wählen Sie **Ja**.

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.

    ![Öffnen der Registerkarte „Debuggen“](media/with-visual-studio-code/opendebug.png)

4. Suchen Sie den grünen Pfeil am oberen Rand des Fensters. Stellen Sie sicher, dass in der Dropdownliste die Option `.NET Core Launch (console)` ausgewählt ist.

    ![Auswählen von .NET Core](media/with-visual-studio-code/selectcore.png)

5. Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie auf den **Rand des Editors** klicken. Dieser befindet sich links neben den Zeilennummern im Editor, neben Zeile 9. Alternativ können Sie den Textcursor im Editor in Zeile 9 bewegen und die Taste <kbd>F9</kbd> drücken.

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/setbreakpoint.png)

6. Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten. Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.
    * Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.

    ![Ausführen und Debuggen](media/with-visual-studio-code/rundebug.png)

7. Wählen Sie im oberen Bereich den grünen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.

> [!TIP]
> Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="faq"></a>FAQ

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Mir fehlen für das Erstellen und Debuggen von C# in Visual Studio Code die erforderlichen Objekte. Mein Debugger gibt an: „Keine Konfiguration.“

Die C#-Erweiterung in Visual Studio Code kann Objekte zum Erstellen und Debuggen für Sie generieren. Wenn Sie ein C#-Projekt zum ersten Mal öffnen, fordert Visual Studio Code Sie zur Generierung dieser Objekte auf. Wenn Sie zu diesem Zeitpunkt keine Objekte generiert haben, können Sie diesen Befehl weiterhin ausführen, indem Sie die Befehlspalette (**„Ansicht“ > „Befehlspalette“**) öffnen und „>.NET: Objekte zum Erstellen und Debuggen generieren“ eingeben. Durch diese Auswahl werden die erforderlichen Konfigurationsdateien „.vscode“, „launch.json“ und „tasks.json“ generiert.

## <a name="see-also"></a>Siehe auch

* [Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
* [Debuggen in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)
