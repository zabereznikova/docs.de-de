---
title: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac
description: Erfahren Sie, wie Sie eine .NET-Konsolenanwendung mit Visual Studio für Mac erstellen.
ms.date: 11/30/2020
ms.openlocfilehash: 1351b06eec32cd8d3d9d44926655405fe2246f58
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599485"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a>Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio für Mac

In diesem Tutorial wird gezeigt, wie Sie eine .NET-Konsolenanwendung in Visual Studio für Mac erstellen und ausführen.

> [!NOTE]
> Ihr Feedback ist uns sehr wichtig. Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:
>
> * Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Ablegen eines Fehlerberichts geöffnet. Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://aka.ms/feedback/report?space=41) verfolgen.
> * Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://aka.ms/feedback/suggest?space=41).

## <a name="prerequisites"></a>Voraussetzungen

* [Visual Studio für Mac ab Version 8.8](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Wählen Sie die Option zum Installieren von .NET Core aus. Die Installation von Xamarin ist für die Entwicklung mit .NET optional. Weitere Informationen finden Sie in den folgenden Ressourcen:

  * [Tutorial: Installieren von Visual Studio für Mac](/visualstudio/mac/installation).
  * [Unterstützte macOS-Versionen](../install/windows.md)
  * [Von Visual Studio für Mac unterstützte .NET-Versionen](/visualstudio/mac/net-core-support).

## <a name="create-the-app"></a>Erstellen der App

1. Starten Sie Visual Studio für Mac.

1. Wählen Sie im Startfenster **Neu** aus.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Schaltfläche „Neu“ auf der Startseite von Visual Studio für Mac":::

1. Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Web und Konsole** die Option **App** aus. Wählen Sie die Vorlage **Konsolenanwendung** und anschließend **Weiter** aus.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Liste neuer Projektvorlagen":::

1. Wählen Sie in der Dropdownliste **Zielframework** des Dialogfelds **Neue Konsolenanwendung konfigurieren** die Option **.NET 5.0** und dann **Weiter** aus.

1. Geben Sie in **Projektname** HelloWorld ein, und wählen Sie **Erstellen** aus.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Dialogfeld „Neue Konsolenanwendung konfigurieren“":::

Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“ im Terminalfenster auf.

Der Code der Vorlage definiert die Klasse `Program` mit der einzelnen Methode `Main`, die ein <xref:System.String>-Array als Argument verwendet:

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

`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im Array `args` verfügbar.

## <a name="run-the-app"></a>Ausführen der App

1. Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen der App ohne Debuggen.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Im Terminal wird „Hello World!“ angezeigt":::

1. Schließen Sie das Fenster **Terminal**.

## <a name="enhance-the-app"></a>Optimieren der App

Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.

1. Ersetzen Sie in *Program.cs* den Inhalt der `Main`-Methode, der aus der Zeile besteht, die `Console.WriteLine` aufruft, durch folgenden Code:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   Mit diesem Code wird eine Eingabeaufforderung im Konsolenfenster angezeigt und gewartet, bis der Benutzer eine Zeichenfolge eingibt und die <kbd>EINGABETASTE</kbd> drückt. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType> Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` zu. Außerdem werden diese Werte im Konsolenfenster angezeigt. Schließlich wird eine Eingabeaufforderung im Konsolenfenster angezeigt, und die <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType>-Methode wird aufgerufen, um auf eine Benutzereingabe zu warten.

   `\n` stellt ein Zeilenvorschubzeichen dar.

   Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen. Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt. Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.

1. Drücken Sie <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>OPTION</kbd>+<kbd>BEFEHL</kbd>+<kbd>EINGABETASTE</kbd>) zum Ausführen der App.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminalfenster mit geänderter Programmausgabe":::

1. Schließen Sie das Terminal.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET-Konsolenanwendung erstellt. Im nächsten Tutorial debuggen Sie die App.

> [!div class="nextstepaction"]
> [Debuggen einer .NET-Konsolenanwendung mit Visual Studio für Mac](debugging-with-visual-studio-mac.md)
