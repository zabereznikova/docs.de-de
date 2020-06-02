---
title: Erstellen einer Konsolenanwendung mit .NET Core mithilfe von Visual Studio Code
description: Erfahren Sie, wie Sie eine .NET Core-Konsolenanwendung mit Visual Studio Code und der .NET Core-CLI erstellen.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201705"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a>Tutorial: Erstellen einer Konsolenanwendung mit .NET Core mithilfe von Visual Studio Code

In diesem Tutorial wird gezeigt, wie Sie eine .NET Core-Konsolenanwendung erstellen und ausführen, indem Sie Visual Studio Code und die .NET Core-CLI verwenden. Projektaufgaben, z. B. das Erstellen, Kompilieren und Ausführen eines Projekts, werden mithilfe der CLI durchgeführt, sodass Sie dieses Tutorial mit einem anderen Code-Editor nachvollziehen und Befehle in einem Terminal ausführen können, wenn Sie dies bevorzugen.

## <a name="prerequisites"></a>Voraussetzungen

1. [Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [.NET Core 3.1 SDK oder höher](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>Erstellen der App

1. Öffnen Sie Visual Studio Code.

1. Erstellen eines Projekts.

   1. Wählen Sie **Datei** > **Ordner öffnen**/**Öffnen** im Hauptmenü aus, erstellen Sie einen Ordner *HelloWorld*, und klicken Sie dann auf **Ordner auswählen**/**Öffnen**.

      Der Name des Ordners wird standardmäßig zum Projektnamen und Namespacenamen. Sie fügen später in diesem Tutorial Code hinzu, der erwartet, dass der Projektnamespace `HelloWorld` ist.

   1. Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.

      Das**Terminal** wird mit der Eingabeaufforderung im Ordner *HelloWorld* geöffnet.

   1. Geben Sie im **Terminal** den folgenden Befehl ein:

      ```dotnetcli
      dotnet new console
      ```

Die Konsolenanwendungsvorlage für .NET Core definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument akzeptiert. Die Datei *Program.cs* enthält den folgenden Code:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

Die Vorlage erstellt eine einfache Anwendung, die die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode aufruft, um „Hello World!“ anzuzeigen. im Konsolenfenster anzuzeigen.

## <a name="run-the-app"></a>Ausführen der App

Führen Sie die folgenden Befehle im **Terminal** aus:

```dotnetcli
dotnet run
```

Das Programm zeigt „Hello World!“ an. und wird beendet.

![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a>Optimieren der App

Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.

1. Öffnen Sie *Program.cs*, indem Sie darauf klicken.

   Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.

   ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

1. Wählen Sie **Ja** aus, wenn Visual Studio Code Sie auffordert, die fehlenden Ressourcen zum Erstellen und Debuggen Ihrer App hinzuzufügen.

   ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

1. Ersetzen Sie den Inhalt der `Main`-Methode in *Program.cs*, der zurzeit nur aus der Zeile besteht, die `Console.WriteLine` aufruft, durch den folgenden Code:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   Dieser Code zeigt „What is your name?“ im Konsolenfenster an und wartet, bis der Benutzer eine Zeichenfolge eingegeben und die **EINGABETASTE** gedrückt hat. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Schließlich werden diese Werte im Konsolenfenster angezeigt.

   `\n` stellt ein Zeilenvorschubzeichen dar.

   Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen. Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt. Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.

1. Speichern Sie die Änderungen.

   > [!IMPORTANT]
   > In Visual Studio Code müssen Sie Änderungen explizit speichern. Im Gegensatz zu Visual Studio werden Dateiänderungen nicht automatisch gespeichert, wenn Sie eine App erstellen und ausführen.

1. Führen Sie das Programm erneut aus:

   ```dotnetcli
   dotnet run
   ```

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die **EINGABETASTE** drücken.

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Terminalfenster mit geänderter Programmausgabe":::

1. Drücken Sie eine beliebige Taste, um das Programm zu beenden.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET Core-Anwendung erstellt. Im nächsten Tutorial debuggen Sie die App.

> [!div class="nextstepaction"]
> [Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio Code](debugging-with-visual-studio-code.md)
