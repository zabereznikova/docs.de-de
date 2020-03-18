---
title: 'Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)'
ms.date: 07/20/2015
ms.assetid: f6927ef2-dc6c-43f8-bc82-bbeac42de423
ms.openlocfilehash: afd7dda4e876b7faa54ae4a8e62d640d2b9aaf07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970025"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-c"></a>Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)

Sie können die Leistung der asynchronen Projektmappe in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) verbessern, indem Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>-Methode verwenden. Diese Methode wartet auf mehrere asynchrone Vorgänge, die als Auflistung von Aufgaben dargestellt werden.

Sie haben möglicherweise in der exemplarischen Vorgehensweise bemerkt, dass die Websites Downloads in verschiedenen Geschwindigkeiten anbieten. Manchmal ist eine Website sehr langsam und verzögert alle verbleibenden Downloads. Wenn Sie die asynchronen Projektmappen ausführen, die Sie in der exemplarischen Vorgehensweise erstellt haben, können Sie das Programm einfach beenden, wenn Sie nicht warten möchten. Eine bessere Option wäre jedoch, alle Downloads gleichzeitig zu starten und schnellere Downloads einfach fortfahren, ohne auf langsamere zu warten.

Sie wenden die `Task.WhenAll`-Methode auf eine Aufgabenauflistung an. Die Anwendung von `WhenAll` gibt eine einzelne Aufgabe zurück, die nicht abgeschlossen ist, bevor jede Aufgabe in der Auflistung abgeschlossen ist. Die Aufgaben scheinen parallel ausgeführt zu werden, es werden jedoch keine weiteren Threads erstellt. Die Aufgaben können in jeder Reihenfolge abschließen.

> [!IMPORTANT]
> Die folgenden Prozeduren beschreiben Erweiterungen zu asynchronen Anwendungen, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt werden. Sie können die Anwendungen entwickeln, indem Sie entweder die exemplarische Vorgehensweise durcharbeiten oder den Code von [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.
>
> Für die Ausführung des Beispiels muss Visual Studio 2012 oder höher auf dem Computer installiert sein.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>So fügen Sie der GetURLContentsAsync-Lösung Task.WhenAll hinzu

1. Fügen Sie die `ProcessURLAsync`-Methode der ersten Anwendung hinzu, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt wurde.

    - Wenn Sie die [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) heruntergeladen haben, öffnen Sie das „AsyncWalkthrough“-Projekt, und fügen Sie dann `ProcessURLAsync` der Datei „MainWindow.xaml.cs“ hinzu.

    - Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `GetURLContentsAsync`-Methode enthält. Die Datei „MainWindow.xaml.cs“ für diese Anwendung ist das erste Beispiel im Abschnitt „Vollständige Codebeispiele der exemplarischen Vorgehensweise“.

    Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `foreach`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise. Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.

    ```csharp
    private async Task<int> ProcessURLAsync(string url)
    {
        var byteArray = await GetURLContentsAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. Kommentieren Sie die Schleife `foreach` in `SumPageSizesAsync` aus, oder löschen Sie sie, wie der folgenden Code zeigt.

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    byte[] urlContents = await GetURLContentsAsync(url);

    //    // The previous line abbreviates the following two assignment statements.
    //    // GetURLContentsAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //    //byte[] urlContents = await getContentsTask;

    //    DisplayResults(url, urlContents);

    //    // Update the total.
    //    total += urlContents.Length;
    //}
    ```

3. Erstellen Sie eine Auflistung von Aufgaben. Der folgende Code definiert eine [Abfrage](../linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt. Die Aufgaben werden beim Auswerten der Abfrage gestartet.

    Fügen Sie nach der Deklaration von `SumPageSizesAsync` den folgenden Code der `urlList`-Methode hinzu:

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben `downloadTasks` an. `Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.

    Im folgenden Beispiel erwartet der `await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt. Der Ausdruck wird gegen ein Array mit ganzen Zahlen ausgewertet, wobei jede ganze Zahl die Länge einer heruntergeladenen Website ist. Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen. Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>So fügen Sie der HttpClient.GetByteArrayAsync-Lösung Task.WhenAll hinzu

1. Fügen Sie die folgende Version von `ProcessURLAsync` der zweiten Anwendung hinzu, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt wurde.

    - Wenn Sie den Code von [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) heruntergeladen haben, öffnen Sie das „AsyncWalkthrough_HttpClient“-Projekt und fügen dann `ProcessURLAsync` entweder der „MainWindow.xaml.cs“-Datei hinzu.

    - Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `HttpClient.GetByteArrayAsync`-Methode verwendet. Die „MainWindow.xaml.cs“-Datei für diese Anwendung ist das zweite Beispiel im Abschnitt „Vollständige Codebeispiele der exemplarischen Vorgehensweise“.

    Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `foreach`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise. Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.

    Der einzige Unterschied der `ProcessURLAsync`-Methode in der vorherigen Prozedur ist die Verwendung der <xref:System.Net.Http.HttpClient>-Instanz, `client`.

    ```csharp
    async Task<int> ProcessURLAsync(string url, HttpClient client)
    {
        byte[] byteArray = await client.GetByteArrayAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. Kommentieren Sie die Schleife `For Each` oder `foreach` in `SumPageSizesAsync` aus oder löschen Sie sie, wie der folgenden Code zeigt.

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    // GetByteArrayAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    byte[] urlContent = await client.GetByteArrayAsync(url);

    //    // The previous line abbreviates the following two assignment
    //    // statements.
    //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
    //    byte[] urlContent = await getContentTask;

    //    DisplayResults(url, urlContent);

    //    // Update the total.
    //    total += urlContent.Length;
    //}
    ```

3. Definieren Sie eine [Abfrage](../linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt. Die Aufgaben werden beim Auswerten der Abfrage gestartet.

    Fügen Sie nach der Deklaration von `SumPageSizesAsync` und `client` den folgenden Code der `urlList`-Methode hinzu:

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url, client);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben an, `downloadTasks`. `Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.

    Im folgenden Beispiel erwartet der `await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt. Wenn vollständig, wertet der `await`-Ausdruck als Ergebnis ein Array von ganzen Zahlen aus, wobei jede ganze Zahl die Länge einer heruntergeladenen Website hat. Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen. Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>So testen Sie die Task.WhenAll-Lösungen

- Drücken Sie in beiden Projektmappen F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten**. Die Ausgabe sollte in etwa der Ausgabe der async-Lösungen in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entsprechen. Beachten Sie jedoch, dass die Websites in einer jeweils anderen Reihenfolge angezeigt werden.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Erweiterungen des Projekts, das die `GetURLContentsAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Two-step async call.
            Task sumTask = SumPageSizesAsync();
            await sumTask;

            // One-step async call.
            //await SumPageSizesAsync();

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    byte[] urlContents = await GetURLContentsAsync(url);

            //    // The previous line abbreviates the following two assignment statements.
            //    // GetURLContentsAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
            //    //byte[] urlContents = await getContentsTask;

            //    DisplayResults(url, urlContents);

            //    // Update the total.
            //    total += urlContents.Length;
            //}

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        private async Task<int> ProcessURLAsync(string url)
        {
            var byteArray = await GetURLContentsAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    await responseStream.CopyToAsync(content);
                }
            }

            // Return the result as a byte array.
            return content.ToArray();

        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Erweiterungen des Projekts, das die `HttpClient.GetByteArrayAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_HttpClient_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client = new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url, client);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    // GetByteArrayAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    byte[] urlContent = await client.GetByteArrayAsync(url);

            //    // The previous line abbreviates the following two assignment
            //    // statements.
            //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
            //    byte[] urlContent = await getContentTask;

            //    DisplayResults(url, urlContent);

            //    // Update the total.
            //    total += urlContent.Length;
            //}

            // Display the total count for all of the web addresses.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        async Task<int> ProcessURLAsync(string url, HttpClient client)
        {
            byte[] byteArray = await client.GetByteArrayAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each web site. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
