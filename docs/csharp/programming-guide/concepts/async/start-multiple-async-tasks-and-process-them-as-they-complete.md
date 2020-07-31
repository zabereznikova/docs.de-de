---
title: Verarbeiten asynchroner Aufgaben nach Abschluss
description: In diesem Beispiel wird gezeigt, wie Sie mit Task.WhenAny in C# mehrere Tasks starten und deren Ergebnisse jeweils nach Abschluss der Durchführung verarbeiten, anstatt sie in der Reihenfolge zu verarbeiten, in der sie gestartet wurden.
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: a7cfa0bdf783fe9bb735241ca398fde7895f1493
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925149"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)

Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.

Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen. Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter. In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet. Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet. Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="download-an-example-solution"></a>Herunterladen einer Beispielprojektmappe

Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.

> [!TIP]
> Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich stattdessen die Datei *MainWindow.xaml.cs* am Ende dieses Themas ansehen.

1. Extrahieren Sie die heruntergeladenen Dateien aus der *ZIP*-Datei, und starten Sie dann Visual Studio.

2. Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen heruntergeladenen Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (*SLN*) für *AsyncFineTuningCS*/*AsyncFineTuningVB*.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt **ProcessTasksAsTheyFinish** und wählen dann **Als Startprojekt festlegen** aus.

5. Drücken Sie die Taste <kbd>F5</kbd>, um das Programm mit Debuggen auszuführen, oder drücken Sie die Tasten <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.

6. Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.

## <a name="create-the-program-yourself"></a>Das Programm selbst erstellen

Dieses Beispiel stellt eine Ergänzung des Codes dar, der in [Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)](cancel-remaining-async-tasks-after-one-is-complete.md) entwickelt wird, und verwendet die gleiche Benutzeroberfläche.

Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt [Herunterladen des Beispiels](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), wählen Sie als Startprojekt aber **CancelAfterOneTask** aus. Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu. Die Änderungen sind mit Sternchen gekennzeichnet.

Das Projekt **CancelAfterOneTask** enthält bereits eine Abfrage, die eine Auflistung von Aufgaben erstellt, während sie ausgeführt wird. Jeder Aufruf von `ProcessURLAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist:

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

Nehmen Sie in der Datei *MainWindow.xaml.cs* des Projekts die folgenden Änderungen an der `AccessTheWebAsync`-Methode vor:

- Führen Sie die Abfrage aus, indem Sie <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anstelle von <xref:System.Linq.Enumerable.ToArray%2A> anwenden.

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- Fügen Sie eine `while`-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt:

    1. Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. Entfernt die entsprechende Aufgabe aus der Auflistung.

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. Erwartet `firstFinishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird. Die Variable `firstFinishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TReturn` eine ganze Zahl ist. Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt. Wenn für die Aufgabe ein Fehler auftritt, löst `await` die erste untergeordnete Ausnahme aus, die in der `AggregateException` gespeichert ist, im Gegensatz zum Lesen der `Result`-Eigenschaft, die die `AggregateException` auslösen würde.

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

Führen Sie das Programm mehrmals aus, um zu bestätigen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.

> [!CAUTION]
> Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen. Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen. Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der Datei *MainWindow.xaml.cs* für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden. Beachten Sie ferner, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.

Sie können das Projekt hier herunterladen: [Async Sample: Fine Tuning Your Application (Async-Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Feinabstimmung der Async-Anwendung (C#)](fine-tuning-your-async-application.md)
- [Asynchrone Programmierung mit „async“ und „await“ (C#)](index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
