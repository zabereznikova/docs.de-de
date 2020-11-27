---
title: Erstellen einer .NET-Konsolenanwendung mit Visual Studio
description: Hier erfahren Sie, wie Sie mithilfe von Visual Studio eine .NET-Konsolenanwendung mit C# oder Visual Basic erstellen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e395122e59f17ed66bbd9d83b01610993f663ce1
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915919"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a>Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio

In diesem Tutorial wird gezeigt, wie Sie eine .NET-Konsolenanwendung in Visual Studio 2019 erstellen und ausführen.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019 Version 16.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**. Das .NET 5.0 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.

  Weitere Informationen finden Sie unter [Installieren mit Visual Studio](../install/windows.md#install-with-visual-studio).

## <a name="create-the-app"></a>Erstellen der App

Erstellen Sie ein .NET-Konsolen-App-Projekt mit dem Namen „HelloWorld“.

1. Starten Sie Visual Studio 2019.

1. Klicken Sie auf **Extras** > **Optionen** > **Umgebung** > **Previewfeatures**, und aktivieren Sie dann **Show all .NET Core templates in the New project (requires restart)** (Alle .NET Core-Vorlagen im neuen Projekt anzeigen (Neustart erforderlich)).

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Anzeigen aller .NET-Vorlagenoptionen":::

1. Schließen Sie Visual Studio, und öffnen Sie es wieder.

1. Wählen Sie auf der Startseite **Neues Projekt erstellen** aus.

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Schaltfläche „Neues Projekt erstellen“, die auf der Visual Studio-Startseite ausgewählt ist":::

1. Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Konsole** in das Suchfeld ein. Wählen Sie dann **C#** oder **Visual Basic** in der Liste der Sprachen und **Alle Plattformen** in der Liste der Plattformen aus. Wählen Sie die Vorlage **Konsolenanwendung** aus, und klicken Sie dann auf **Weiter**.

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Erstellen eines neuen Projektfenster mit ausgewählten Filtern":::

   > [!TIP]
   > Wenn die .NET-Vorlagen nicht angezeigt werden, fehlt möglicherweise die erforderliche Workload. Wählen Sie unter der Meldung **Sie finden nicht, wonach Sie suchen?** den Link **Weitere Tools und Features installieren** aus. Der Visual Studio-Installer wird geöffnet. Stellen Sie sicher, dass Sie die Workload **Plattformübergreifende .NET Core-Entwicklung** installiert haben.

1. Geben Sie im Dialogfeld **Neues Projekt konfigurieren** in das Feld **Projektname** den Text **HelloWorld** ein. Wählen Sie dann **Erstellen** aus.

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Konfigurieren Sie das Fenster für das neue Projekt mit den Feldern „Projektname“, „Speicherort“ und „Projektmappenname“.":::

1. Wählen Sie im Dialogfeld **Zusätzliche Informationen** die Option **.NET 5.0 (Current)** (.NET 5.0 (aktuell)) aus, und klicken Sie dann auf **Erstellen**.

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Dialogfeld „Zusätzliche Informationen“":::

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

   Ein Konsolenfenster wird geöffnet, das den Text „Hello World!“ auf dem Bildschirm anzeigt.

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Konsolenfenster, das Hello World „Drücken Sie eine beliebige Taste, um fortzufahren...“ zeigt":::

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

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Konsolenfenster mit veränderter Programmausgabe":::

1. Drücken Sie eine beliebige Taste, um das Konsolenfenster zu schließen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Aktuelle Releases und langfristige Supportreleases](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET-Konsolenanwendung erstellt. Im nächsten Tutorial debuggen Sie die App.

> [!div class="nextstepaction"]
> [Tutorial: Debuggen einer .NET Core-Konsolenanwendung mit Visual Studio](debugging-with-visual-studio.md)
