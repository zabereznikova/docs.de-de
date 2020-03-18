---
title: Erste Schritte mit C# und Visual Studio Code
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: 8eaf1ba2314dcab96db615a8691afed82c5011a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397884"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Erste Schritte mit C# und Visual Studio Code

.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden. Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.

## <a name="prerequisites"></a>Voraussetzungen

1. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
2. Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download).
3. Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) für Visual Studio Code. Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).

## <a name="hello-world"></a>Hello World

Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:

1. Öffnen Sie ein Projekt:

    - Öffnen Sie Visual Studio Code.
    - Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.
    - Klicken Sie im Hauptmenü auf **Datei** > **Open Folder** (Ordner öffnen), um den Ordner zu öffnen, in dem Sie Ihr C#-Projekt speichern möchten, und klicken Sie auf **Ordner auswählen**. Für dieses Beispiel wird ein Ordner namens *HelloWorld* für das Projekt erstellt.

      ![Visual Studio Code, Ordner öffnen](media/with-visual-studio-code/vs-code-open-folder.png)

2. Initialisieren Sie ein C#-Projekt:

    - Öffnen Sie das integrierte Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Integriertes Terminal** klicken.
    - Geben Sie im Terminalfenster `dotnet new console` ein.
    - Durch diesen Befehl wird eine Datei *Program.cs* in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hello World“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens *HelloWorld.csproj* erstellt.

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnet-new-command.png)

3. Lösen Sie die Buildobjekte auf:

    - Geben Sie für **.NET Core 1.x** den Befehl `dotnet restore` ein. Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.

      ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. Führen Sie das „Hello World“-Programm aus:

    - Geben Sie `dotnet run` ein.

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.

## <a name="debug"></a>Debuggen

1. Öffnen Sie *Program.cs*, indem Sie darauf klicken. Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

2. Visual Studio Code fordert Sie dazu auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen. Wählen Sie **Ja** aus.

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.

    ![Öffnen Sie die Registerkarte „Debuggen“ in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

4. Suchen Sie den grünen Pfeil am oberen Rand des Fensters. Stellen Sie sicher, dass in der Dropdownliste daneben die Option **.NET Core Launch (Console)** (.NET Core-Start (Konsole)) ausgewählt ist.

    ![Auswählen von .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

5. Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie auf den **Rand des Editors** klicken. Dieser befindet sich links neben den Zeilennummern im Editor, neben Zeile 9. Alternativ können Sie den Textcursor im Editor in Zeile 9 bewegen und die Taste <kbd>F9</kbd> drücken.

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten. Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.
    - Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.

7. Wählen Sie im oberen Bereich den blauen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.

    ![Ausführen und Debuggen in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="add-a-class"></a>Hinzufügen einer Klasse

1. Um eine neue Klasse hinzuzufügen, klicken Sie mit der rechten Maustaste auf den VSCode-Explorer, und wählen Sie **Neue Datei** aus. Dadurch wird dem Ordner, den Sie in Visual Studio Code geöffnet haben, eine neue Datei hinzugefügt.
2. Nennen Sie die Datei *MyClass.cs*. Sie müssen sie mit der `.cs`-Erweiterung speichern, damit sie als Csharp-Datei erkannt wird.
3. Fügen Sie den folgenden Code zum Erstellen Ihrer ersten Klasse hinzu. Achten Sie darauf, den richtigen Namespace einzubeziehen, damit Sie aus Ihrer Datei *Program.cs* darauf verweisen können:

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

4. Rufen Sie die neue Klasse aus Ihrer Main-Methode in *Program.cs* auf, indem Sie den folgenden Code hinzufügen:

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

5. Speichern Sie die Änderungen, und führen Sie das Programm erneut aus. Die neue Nachricht sollte mit der angefügten Zeichenfolge angezeigt werden.

    ```dotnetcli
    dotnet run
    ```

    Sie erhalten die folgende Ausgabe:

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>FAQ

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Mir fehlen für das Erstellen und Debuggen von C# in Visual Studio Code die erforderlichen Objekte. Mein Debugger gibt an: „Keine Konfiguration.“

Die C#-Erweiterung in Visual Studio Code kann Objekte zum Erstellen und Debuggen für Sie generieren. Wenn Sie ein C#-Projekt zum ersten Mal öffnen, fordert Visual Studio Code Sie zur Generierung dieser Objekte auf. Wenn Sie zu diesem Zeitpunkt keine Objekte generiert haben, können Sie diesen Befehl weiterhin ausführen, indem Sie die Befehlspalette ( **„Ansicht“ > „Befehlspalette“** ) öffnen und „>.NET: Objekte zum Erstellen und Debuggen generieren“ eingeben. Durch diese Auswahl werden die erforderlichen Konfigurationsdateien *.vscode*, *launch.json* und *tasks.json* generiert.

## <a name="see-also"></a>Weitere Informationen

- [Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
- [Debuggen in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)
