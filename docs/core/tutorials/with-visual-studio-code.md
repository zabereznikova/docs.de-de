---
title: Erste Schritte mit C# und Visual Studio Code
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506889"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Erste Schritte mit C# und Visual Studio Code

.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden. Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.

## <a name="prerequisites"></a>Voraussetzungen

1. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
2. Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download).
3. Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) für Visual Studio Code. Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).

## <a name="hello-world"></a>Hello World

Beginnen wir mit einem einfachen Hallo-Welt-Programm in .NET Core:

1. Öffnen Sie ein Projekt:

    - Öffnen Sie Visual Studio Code.
    - Klicken Sie im Hauptmenü auf **Datei** > **Ordner öffnen**.
    - Erstellen Sie einen Ordner mit dem Namen *HelloWorld*, und klicken Sie auf **Ordner auswählen**. Der Name des Ordners wird standardmäßig zum Projektnamen und Namespacenamen. Sie fügen später in diesem Tutorial Code hinzu, der erwartet, dass der Projektnamespace `HelloWorld` ist.

1. Initialisieren Sie ein C#-Projekt:

    - Öffnen Sie das Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Terminal** klicken.
    - Geben Sie im Terminalfenster `dotnet new console` ein.

      Durch diesen Befehl wird eine Datei *Program.cs* in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hello World“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens *HelloWorld.csproj* erstellt.

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnet-new-command.png)

1. Führen Sie das „Hello World“-Programm aus:

    - Geben Sie im Terminalfenster `dotnet run` ein.

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a>Debug

1. Öffnen Sie *Program.cs*, indem Sie darauf klicken. Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code fordert Sie auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen. Wählen Sie **Ja**.

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

1. Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.

    ![Öffnen Sie die Registerkarte „Debuggen“ in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. Suchen Sie den grünen Pfeil am oberen Rand des Fensters. Stellen Sie sicher, dass in der Dropdownliste daneben die Option **.NET Core Launch (Console)** (.NET Core-Start (Konsole)) ausgewählt ist.

    ![Auswählen von .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie auf den **Rand des Editors** klicken. Dieser befindet sich links neben den Zeilennummern im Editor, neben Zeile 9. Alternativ können Sie den Textcursor im Editor in Zeile 9 bewegen und die Taste <kbd>F9</kbd> drücken.

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten. Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.
    - Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.

1. Wählen Sie im oberen Bereich den blauen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.

    ![Ausführen und Debuggen in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="add-a-class"></a>Hinzufügen einer Klasse

1. Klicken Sie im Visual Studio Code-Explorer mit der rechten Maustaste unter *Program.cs*, und klicken Sie dann auf **Neue Datei**, um eine neue Klasse hinzuzufügen. Dadurch wird dem Ordner, den Sie in Visual Studio Code geöffnet haben, eine neue Datei hinzugefügt.
1. Nennen Sie die Datei *MyClass.cs*. Sie müssen sie mit der `.cs`-Erweiterung speichern, damit sie als Csharp-Datei erkannt wird.
1. Fügen Sie den folgenden Code hinzu, um Ihre erste Klasse zu erstellen.

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

1. Rufen Sie die neue Klasse über die `Main`-Methode auf, indem Sie den Code in *Program.cs* durch folgenden Code ersetzen:

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

1. Speichern Sie die Änderungen.

1. Führen Sie das Programm erneut aus.

    ```dotnetcli
    dotnet run
    ```

    Die neue Meldung wird mit der angefügten Zeichenfolge angezeigt.

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>FAQ

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Mir fehlen für das Erstellen und Debuggen von C# in Visual Studio Code die erforderlichen Objekte. Mein Debugger gibt an: „Keine Konfiguration.“

Die C#-Erweiterung in Visual Studio Code kann Objekte zum Erstellen und Debuggen für Sie generieren. Wenn Sie ein C#-Projekt zum ersten Mal öffnen, fordert Visual Studio Code Sie zur Generierung dieser Objekte auf. Wenn Sie zu diesem Zeitpunkt keine Objekte generiert haben, können Sie diesen Befehl weiterhin ausführen, indem Sie die Befehlspalette ( **„Ansicht“ > „Befehlspalette“** ) öffnen und „>.NET: Objekte zum Erstellen und Debuggen generieren“ eingeben. Durch diese Auswahl werden die erforderlichen Konfigurationsdateien *.vscode*, *launch.json* und *tasks.json* generiert.

## <a name="see-also"></a>Siehe auch

- [Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)
- [Debuggen in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)
