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
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="3f83b-103">Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)</span><span class="sxs-lookup"><span data-stu-id="3f83b-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="3f83b-104">Sie können einen asynchronen Vorgang nach einem gewissen Zeitraum mithilfe der <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>-Methode abbrechen, wenn Sie nicht auf das Ende des Vorgangs warten möchten.</span><span class="sxs-lookup"><span data-stu-id="3f83b-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="3f83b-105">Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="3f83b-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="3f83b-106">Dieses Beispiel fügt dem in [Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md) entwickelten Code Funktionen zum Herunterladen einer Liste von Websites und Anzeigen der Länge der Inhalte jeder Site hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f83b-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="3f83b-107">In diesem Lernprogramm wird Folgendes behandelt:</span><span class="sxs-lookup"><span data-stu-id="3f83b-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="3f83b-108">Aktualisieren einer vorhandenen .NET-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="3f83b-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="3f83b-109">Planen eines Abbruchs</span><span class="sxs-lookup"><span data-stu-id="3f83b-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f83b-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3f83b-110">Prerequisites</span></span>

<span data-ttu-id="3f83b-111">Für dieses Lernprogramm ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="3f83b-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="3f83b-112">Erstellen einer Anwendung im Tutorial [Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)](cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="3f83b-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="3f83b-113">.NET SDK 5.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="3f83b-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="3f83b-114">integrierte Entwicklungsumgebung (Integrated Development Environment, IDE)</span><span class="sxs-lookup"><span data-stu-id="3f83b-114">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="3f83b-115">Es wird empfohlen, Visual Studio, Visual Studio Code oder Visual Studio für Mac zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f83b-115">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

## <a name="update-application-entry-point"></a><span data-ttu-id="3f83b-116">Aktualisieren des Einstiegspunkts der Anwendung</span><span class="sxs-lookup"><span data-stu-id="3f83b-116">Update application entry point</span></span>

<span data-ttu-id="3f83b-117">Ersetzen Sie die vorhandene `Main`-Methode durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3f83b-117">Replace the existing `Main` method with the following:</span></span>

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

<span data-ttu-id="3f83b-118">Mit der aktualisierten `Main`-Methode werden einige Anweisungsnachrichten in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="3f83b-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="3f83b-119">In der [try catch](../../../language-reference/keywords/try-catch.md)-Anweisung wird <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> aufgerufen, um einen Abbruch zu planen.</span><span class="sxs-lookup"><span data-stu-id="3f83b-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> to schedule a cancellation.</span></span> <span data-ttu-id="3f83b-120">Dadurch wird ein Abbruch nach einem bestimmten Zeitraum signalisiert.</span><span class="sxs-lookup"><span data-stu-id="3f83b-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="3f83b-121">Als Nächstes wird die `SumPageSizesAsync`-Methode erwartet.</span><span class="sxs-lookup"><span data-stu-id="3f83b-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="3f83b-122">Wenn die Verarbeitung aller URLs schneller erfolgt als der geplante Abbruch, wird die Anwendung beendet.</span><span class="sxs-lookup"><span data-stu-id="3f83b-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="3f83b-123">Wenn jedoch der geplante Abbruch vor der Verarbeitung aller URLs ausgelöst wird, wird eine <xref:System.Threading.Tasks.TaskCanceledException>-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3f83b-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="3f83b-124">Ausgabe der Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="3f83b-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="3f83b-125">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f83b-125">Complete example</span></span>

<span data-ttu-id="3f83b-126">Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3f83b-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="3f83b-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f83b-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="3f83b-128">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="3f83b-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="3f83b-129">Abbrechen einer Aufgabenliste (C#)</span><span class="sxs-lookup"><span data-stu-id="3f83b-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
