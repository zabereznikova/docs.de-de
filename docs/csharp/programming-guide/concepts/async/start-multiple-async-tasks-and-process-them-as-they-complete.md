---
title: Verarbeiten asynchroner Aufgaben nach Abschluss
description: In diesem Beispiel wird gezeigt, wie Sie mit Task.WhenAny in C# mehrere Tasks starten und deren Ergebnisse jeweils nach Abschluss der Durchführung verarbeiten, anstatt sie in der Reihenfolge zu verarbeiten, in der sie gestartet wurden.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 4cdd35af900863895911ea5c2c9772af362951ec
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615970"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a>Verarbeiten asynchroner Aufgaben nach Abschluss (C#)

Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.

Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen. Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter. In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von <xref:System.Threading.Tasks.Task.WhenAny%2A> die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet. Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet. Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.

## <a name="create-example-application"></a>Erstellen einer Beispielanwendung

Erstellen Sie eine neue .NET Core-Konsolenanwendung. Sie können mithilfe des [dotnet new console](../../../../core/tools/dotnet-new.md#console)-Befehls oder über [Visual Studio](/visualstudio/install/install-visual-studio) eine solche Anwendung erstellen. Öffnen Sie die *Program.cs*-Datei in Ihrem bevorzugten Code-Editor.

### <a name="replace-using-statements"></a>Ersetzen von using-Anweisungen

Ersetzen Sie die vorhandenen using-Anweisungen durch diese Deklarationen:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Hinzufügen von Feldern

Fügen Sie in der `Program`-Klassendefinition die folgenden beiden Felder hinzu:

```csharp
static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

Der `HttpClient` ermöglicht das Senden von HTTP-Anforderungen und das Empfangen von HTTP-Antworten. Die `s_urlList` enthält alle URLs, die von der Anwendung verarbeitet werden sollen.

## <a name="update-application-entry-point"></a>Aktualisieren des Einstiegspunkts der Anwendung

Der Haupteinstiegspunkt in die Konsolenanwendung ist die `Main`-Methode. Ersetzen Sie die vorhandene Methode durch Folgendes:

```csharp
static Task Main() => SumPageSizesAsync();
```

Die aktualisierte `Main`-Methode wird jetzt als [Async main](../../../whats-new/csharp-7.md#async-main)-Methode betrachtet, die einen asynchronen Einstiegspunkt in die ausführbare Datei ermöglicht. Sie wird mit einem Aufruf von `SumPageSizesAsync` angegeben.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Erstellen der SumPageSizesAsync-Methode

Fügen Sie unter der `Main`-Methode die `SumPageSizesAsync`-Methode hinzu:

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

Die Methode beginnt mit dem Instanziieren und Starten einer <xref:System.Diagnostics.Stopwatch>-Klasse. Dann ist eine Abfrage enthalten, die eine Auflistung von Aufgaben erstellt, wenn sie ausgeführt wird. Jeder Aufruf von `ProcessUrlAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist:

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

Aufgrund der [verzögerten Ausführung](../../../../standard/linq/deferred-execution-example.md) mit LINQ wird <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> aufgerufen, um die einzelnen Aufgaben zu starten.

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

Die `while`-Schleife führt die folgenden Schritte für jede Aufgabe in der Auflistung aus:

1. Es wird ein Aufruf von `WhenAny` erwartet, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet hat.

    ```csharp
    Task<int> finishedTask = await Task.WhenAny(downloadTasks);
    ```

1. Entfernt die entsprechende Aufgabe aus der Auflistung.

    ```csharp
    downloadTasks.Remove(finishedTask);
    ```

1. Erwartet `finishedTask`, das durch einen Aufruf von `ProcessUrlAsync` zurückgegeben wird. Die Variable `finishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist. Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt. Wenn für die Aufgabe ein Fehler auftritt, löst `await` im Gegensatz zum Lesen der <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>-Eigenschaft, die die `AggregateException` auslösen würde, die erste untergeordnete Ausnahme aus, die in der `AggregateException` gespeichert ist.

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a>Hinzufügen der Prozessmethode

Fügen Sie die folgende `ProcessUrlAsync`-Methode unterhalb der `SumPageSizesAsync`-Methode hinzu:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Für eine beliebige URL verwendet die Methode die `client`-Instanz, die bereitgestellt wird, um die Antwort als `byte[]` zu erhalten. Die Länge wird zurückgegeben, nachdem die URL und die Länge in die Konsole geschrieben wurden.

Führen Sie das Programm mehrmals aus, um zu bestätigen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.

> [!CAUTION]
> Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen. Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen. Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Asynchrone Programmierung mit Async und Await (C#)](index.md)
