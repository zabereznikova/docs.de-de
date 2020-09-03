---
title: Abbrechen einer Aufgabenliste (C#)
description: In diesem Artikel erfahren Sie, wie Sie Abbruchtoken verwenden, um eine Abbruchanforderung für eine Aufgabenliste zu signalisieren.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 30bef5d1a5082fbd3757377dbedb8f9b9d17e218
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053092"
---
# <a name="cancel-a-list-of-tasks-c"></a>Abbrechen einer Aufgabenliste (C#)

Sie können eine asynchrone Konsolenanwendung abbrechen, wenn Sie nicht auf den Abschluss ihrer Ausführung warten möchten. Anhand des in diesem Artikel veranschaulichten Beispiels können Sie einen Abbruch zu einer Anwendung hinzufügen, die die Inhalte von einer Liste von Websites herunterlädt. Sie können viele Aufgaben abbrechen, indem Sie die <xref:System.Threading.CancellationTokenSource>-Instanz jeder Aufgabe zuordnen. Wenn Sie die <kbd>EINGABETASTE</kbd> drücken, brechen Sie alle Aufgaben ab, die noch nicht abgeschlossen wurden.

In diesem Lernprogramm wird Folgendes behandelt:

> [!div class="checklist"]
>
> - Erstellen einer .NET-Konsolenanwendung
> - Schreiben einer asynchronen Anwendung, die einen Abbruch unterstützt
> - Veranschaulichung der Signalisierung eines Abbruchs

## <a name="prerequisites"></a>Voraussetzungen

Für dieses Lernprogramm ist Folgendes erforderlich:

- [.NET SDK 5.0 oder höher](https://dotnet.microsoft.com/download/dotnet/5.0)
- Integrierte Entwicklungsumgebung (Integrated Development Environment, IDE)
  - [Es wird empfohlen, Visual Studio, Visual Studio Code oder Visual Studio für Mac zu verwenden.](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a>Erstellen einer Beispielanwendung

Erstellen Sie eine neue .NET Core-Konsolenanwendung. Sie können eine solche Anwendung mithilfe des Befehls [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) oder über [Visual Studio](/visualstudio/install/install-visual-studio) erstellen. Öffnen Sie die *Program.cs*-Datei in Ihrem bevorzugten Code-Editor.

### <a name="replace-using-statements"></a>Ersetzen von using-Anweisungen

Ersetzen Sie die vorhandenen using-Anweisungen durch diese Deklarationen:

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a>Hinzufügen von Feldern

Fügen Sie die folgenden drei Felder in der `Program`-Klassendefinition hinzu:

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

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

<xref:System.Threading.CancellationTokenSource> wird dazu verwendet, einen angeforderten Abbruch für <xref:System.Threading.CancellationToken> zu signalisieren. `HttpClient` ermöglicht das Senden und Empfangen von HTTP-Antworten. `s_urlList` enthält alle URLs, die von der Anwendung verarbeitet werden sollen.

## <a name="update-application-entry-point"></a>Aktualisieren des Einstiegspunkts der Anwendung

Der Haupteinstiegspunkt in die Konsolenanwendung ist die `Main`-Methode. Ersetzen Sie die vorhandene Methode durch Folgendes:

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

Die aktualisierte `Main`-Methode wird jetzt als [Async main](../../../whats-new/csharp-7-1.md#async-main)-Methode betrachtet, die einen asynchronen Einstiegspunkt in die ausführbare Datei ermöglicht. Sie schreibt einige Anweisungsnachrichten an die Konsole und deklariert dann eine <xref:System.Threading.Tasks.Task>-Instanz namens `cancelTask`, die Tastatureingaben in die Konsole liest. Wenn die <kbd>EINGABETASTE</kbd> gedrückt wird, wird ein Aufruf an <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> ausgeführt. Dies signalisiert den Abbruch. Dann wird eine `sumPageSizesTask`-Variable der `SumPageSizesAsync`-Methode zugewiesen. Beide Aufgaben werden dann an <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType> übergeben, was fortgesetzt wird, wenn eine der beiden Aufgaben abgeschlossen wird.

## <a name="create-the-asynchronous-sum-page-sizes-method"></a>Erstellen der SumPageSizesAsync-Methode

Fügen Sie unter der `Main`-Methode die `SumPageSizesAsync`-Methode hinzu:

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

Die Methode beginnt mit dem Instanziieren und Starten einer <xref:System.Diagnostics.Stopwatch>-Klasse. Anschließend durchläuft sie alle URLs in `s_urlList` und ruft `ProcessUrlAsync` auf. Mit jeder Iteration wird `s_cts.Token` an die `ProcessUrlAsync`-Methode übergeben, und der Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` ein Integer ist:

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a>Hinzufügen der Prozessmethode

Fügen Sie die folgende `ProcessUrlAsync`-Methode unterhalb der `SumPageSizesAsync`-Methode hinzu:

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

Für eine beliebige URL verwendet die Methode die `client`-Instanz, die bereitgestellt wird, um die Antwort als `byte[]` zu erhalten. Die <xref:System.Threading.CancellationToken>-Instanz wird an die Methoden <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> und <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType> übergeben. `token` wird dazu verwendet, den angeforderten Abbruch zu registrieren. Die Länge wird zurückgegeben, nachdem die URL und die Länge in die Konsole geschrieben wurden.

### <a name="example-application-output"></a>Ausgabe der Beispielanwendung

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [Asynchrone Programmierung mit Async und Await (C#)](index.md)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Abbrechen asynchroner Aufgaben nach einem bestimmten Zeitraum (C#)](cancel-async-tasks-after-a-period-of-time.md)
