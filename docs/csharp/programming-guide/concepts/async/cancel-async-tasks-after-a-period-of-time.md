---
title: Abbrechen asynchroner Aufgaben nach einem bestimmten Zeitraum (C#)
description: Hier erfahren Sie, wie Sie den Abbruch aller zugeordneten Aufgaben planen, die nicht innerhalb eines bestimmten Zeitraums abgeschlossen werden.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: ad9064f8f45a737982ffc35ab4ea2395ddae9016
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811417"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a>Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)

Sie können einen asynchronen Vorgang nach einem gewissen Zeitraum mithilfe der <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>-Methode abbrechen, wenn Sie nicht auf das Ende des Vorgangs warten möchten. Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.

Dieses Beispiel fügt dem in [Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md) entwickelten Code Funktionen zum Herunterladen einer Liste von Websites und Anzeigen der Länge der Inhalte jeder Site hinzu.

In diesem Lernprogramm wird Folgendes behandelt:

> [!div class="checklist"]
>
> - Aktualisieren einer vorhandenen .NET-Konsolenanwendung
> - Planen eines Abbruchs

## <a name="prerequisites"></a>Voraussetzungen

Für dieses Lernprogramm ist Folgendes erforderlich:

- Erstellen einer Anwendung im Tutorial [Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
- [.NET SDK 5.0 oder höher](https://dotnet.microsoft.com/download/dotnet/5.0)
- integrierte Entwicklungsumgebung (Integrated Development Environment, IDE)
  - [Es wird empfohlen, Visual Studio, Visual Studio Code oder Visual Studio für Mac zu verwenden.](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a>Aktualisieren des Einstiegspunkts der Anwendung

Ersetzen Sie die vorhandene `Main`-Methode durch Folgendes:

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }

    Console.WriteLine("Application ending.");
}
```

Mit der aktualisierten `Main`-Methode werden einige Anweisungsnachrichten in die Konsole geschrieben. In der [try catch](../../../language-reference/keywords/try-catch.md)-Anweisung wird <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> aufgerufen, um einen Abbruch zu planen. Dadurch wird ein Abbruch nach einem bestimmten Zeitraum signalisiert.

Als Nächstes wird die `SumPageSizesAsync`-Methode erwartet. Wenn die Verarbeitung aller URLs schneller erfolgt als der geplante Abbruch, wird die Anwendung beendet. Wenn jedoch der geplante Abbruch vor der Verarbeitung aller URLs ausgelöst wird, wird eine <xref:System.Threading.Tasks.TaskCanceledException>-Klasse ausgelöst.

### <a name="example-application-output"></a>Ausgabe der Beispielanwendung

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Asynchrone Programmierung mit Async und Await (C#)](index.md)
- [Abbrechen einer Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md)
