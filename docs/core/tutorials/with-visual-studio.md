---
title: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio
description: Erfahren Sie, wie Sie mithilfe von Visual Studio eine .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4cd18aca4396f902268d59867760424d65ddcf6d
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867632"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a>Tutorial: Erstellen einer .NET Core-Konsolenanwendung mit Visual Studio

In diesem Tutorial wird gezeigt, wie Sie eine .NET Core-Konsolenanwendung in Visual Studio 2019 erstellen und ausführen.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019 Version 16.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**. Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.

  Weitere Informationen finden Sie unter [Installieren des .NET Core SDK in Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).

## <a name="create-the-app"></a>Erstellen der App

Erstellen Sie ein .NET Core-Konsolen-App-Projekt mit dem Namen HelloWorld.

1. Starten Sie Visual Studio 2019.

1. Wählen Sie auf der Startseite **Neues Projekt erstellen** aus.

   ![Schaltfläche „Neues Projekt erstellen“, die auf der Visual Studio-Startseite ausgewählt ist](./media/with-visual-studio/start-window.png)

1. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie dann **C#** oder **Visual Basic** in der Liste der Sprachen und **Alle Plattformen** in der Liste der Plattformen aus. Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.

   ![Erstellen eines neuen Projektfenster mit ausgewählten Filtern](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > Wenn die .NET Core-Vorlagen nicht angezeigt werden, fehlt möglicherweise die erforderliche Workload. Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus. Der Visual Studio-Installer wird geöffnet. Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.

1. Geben Sie im Dialogfeld **Neues Projekt konfigurieren** in das Feld **Projektname** den Text **HelloWorld** ein. Wählen Sie dann **Erstellen** aus.

   ![Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.](./media/with-visual-studio/configure-new-project.png)

Die Vorlage erstellt eine einfache „Hello World“-Anwendung. Sie ruft die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>-Methode auf, um „Hello World!“ im Konsolenfenster anzuzeigen.

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main` ist der Einstiegspunkt der Anwendung, die Methode, die automatisch von der Laufzeit aufgerufen wird, wenn diese die Anwendung startet. Alle Befehlszeilenargumente, die beim Start der Anwendung bereitgestellt werden, sind im *args*-Array verfügbar.

Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.

## <a name="run-the-app"></a>Ausführen der App

1. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.

   Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“ auf dem Bildschirm sowie einige Visual Studio-Debuginformationen ausgibt.

   ![Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt](./media/with-visual-studio/hello-world-console.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="enhance-the-app"></a>Optimieren der App

Erweitern Sie die Anwendung, um den Benutzer aufzufordern, seinen Namen einzugeben und diesen zusammen mit dem Datum und der Uhrzeit anzuzeigen.

1. Ersetzen Sie in *Program.cs* oder *Program.vb* den Inhalt der `Main`-Methode, d. h. der Zeile, in der `Console.WriteLine` aufgerufen wird, durch folgenden Code:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   Mit diesem Code wird eine Eingabeaufforderung im Konsolenfenster angezeigt und gewartet, bis der Benutzer eine Zeichenfolge eingibt und die <kbd>EINGABETASTE</kbd> drückt. Der Code speichert diese Zeichenfolge in einer Variablen namens `name`. Er ruft auch den Wert der <xref:System.DateTime.Now?displayProperty=nameWithType>-Eigenschaft ab, der die aktuelle lokale Uhrzeit enthält, und weist den Wert einer Variablen namens `date` (`currentDate` in Visual Basic) zu. Außerdem werden diese Werte im Konsolenfenster angezeigt. Schließlich wird eine Eingabeaufforderung im Konsolenfenster angezeigt, und die <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType>-Methode wird aufgerufen, um auf eine Benutzereingabe zu warten.

   `\n` (`vbCrLf` in Visual Basic) stellt ein Zeilenvorschubzeichen dar.

   Mit dem Dollarzeichen (`$`) vor einer Zeichenfolge können Sie Ausdrücke wie Variablennamen in geschweifte Klammern in der Zeichenfolge einschließen. Der Ausdruckswert wird anstelle des Ausdrucks in die Zeichenfolge eingefügt. Diese Syntax wird als [interpolierte Zeichenfolgen](../../csharp/language-reference/tokens/interpolated.md) bezeichnet.

1. Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.

1. Reagieren Sie auf die Eingabeaufforderung, indem Sie einen Namen eingeben und die <kbd>EINGABETASTE</kbd> drücken.

   ![Konsolenfenster mit veränderter Programmausgabe](./media/with-visual-studio/hello-world-update.png)

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET Core-Konsolenanwendung erstellt. Im nächsten Tutorial debuggen Sie die App.

> [!div class="nextstepaction"]
> [Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio](debugging-with-visual-studio.md)
