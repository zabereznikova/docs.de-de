---
title: Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)
description: Verwenden Sie die Task.WhenAny-Methode in diesem Beispiel zusammen mit einem CancellationToken in C#, um alle verbleibenden Aufgaben abzubrechen, sobald eine Aufgabe abgeschlossen wurde.
ms.date: 07/20/2015
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
ms.openlocfilehash: 6de60c8faa93752961e3703a042885a71972cc4a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925279"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a>Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)
Mit der <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methode zusammen mit einem <xref:System.Threading.CancellationToken> können Sie alle verbleibenden Aufgaben abbrechen, wenn eine Aufgabe abgeschlossen wurde. Die `WhenAny`-Methode akzeptiert ein Argument, das eine Auflistung von Aufgaben ist. Die Methode startet alle Aufgaben und gibt eine einzelne Aufgabe zurück. Die einzelne Aufgabe ist abgeschlossen, wenn eine beliebige Aufgabe in der Auflistung abgeschlossen ist.  
  
 In diesem Beispiel wird veranschaulicht, wie ein Abbruchtoken in Verbindung mit `WhenAny` verwendet wird, um an der ersten Aufgabe festzuhalten, die in der Auflistung von Aufgaben beendet wird, und die übrigen Aufgaben abzubrechen. Jede Aufgabe lädt den Inhalt einer Website herunter. Im Beispiel wird die Länge des Inhalts des ersten abgeschlossenen Downloads angezeigt und die anderen Downloads abgebrochen.  
  
> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.  
  
## <a name="downloading-the-example"></a>Herunterladen des Beispiels  
 Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.  
  
1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2. Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.  
  
4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterOneTask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.  
  
5. Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
6. Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.  
  
 Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Dateien „MainWindow.xaml.vb“ und „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.  
  
## <a name="building-the-example"></a>Erstellen des Beispiels  
 Das Beispiel in diesem Thema baut auf dem Projekt auf, das unter [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelt wurde, um eine Aufgabenliste abzubrechen. Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.  
  
 Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus. Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.  
  
 Starten Sie in der Datei „MainWindow.xaml.cs“ des **CancelAListOfTasks**-Projekts den Übergang, indem Sie die Verarbeitungsschritte für jede Website von der Schleife in `AccessTheWebAsync` zur folgenden asynchronen Methode verschieben.  
  
```csharp  
// ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 In `AccessTheWebAsync` wird in diesem Beispiel eine Abfrage, die <xref:System.Linq.Enumerable.ToArray%2A>-Methode und die `WhenAny`-Methode verwendet, um ein Array von Aufgaben zu erstellen und zu starten. Die Anwendung von `WhenAny` auf den Array gibt eine einzelne Aufgabe zurück, die, wenn sie erwartet wird, zur ersten Aufgabe auswertet wird, die im Array von Aufgaben zum Abschluss kommt.  
  
 Nehmen Sie in `AccessTheWebAsync` die folgenden Änderungen vor. Die Änderungen in der Codedatei sind mit Sternchen gekennzeichnet.  
  
1. Kommentieren Sie die Schleife aus oder löschen Sie sie.  
  
2. Erstellen Sie eine Abfrage, die eine Auflistung generischer Aufgaben erstellt, wenn sie ausgeführt wird. Jeder Aufruf von `ProcessURLAsync` gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3. Rufen Sie `ToArray` auf, um die Abfrage auszuführen und die Aufgaben zu starten. Die Anwendung der `WhenAny`-Methode im nächsten Schritt würde die Abfrage ohne `ToArray` ausführen und die Aufgaben starten, bei anderen Methoden ist dies möglicherweise nicht der Fall. Die sicherste Methode besteht darin, die Ausführung der Abfrage explizit zu erzwingen.  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4. Rufen Sie `WhenAny` mit der Auflistung von Aufgaben auf. `WhenAny` gibt `Task(Of Task(Of Integer))` oder `Task<Task<int>>` zurück.  Das bedeutet, dass `WhenAny` eine Aufgabe zurückgibt, die zu einem einzelnen `Task(Of Integer)` oder `Task<int>` ausgewertet wird, wenn sie erwartet wird. Diese einzelne Aufgabe ist die erste Aufgabe in der Auflistung, die beendet wird. Die Aufgabe, die als erste beendet wird, wird `firstFinishedTask` zugewiesen. Der Typ von `firstFinishedTask` ist <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist, da dies der Rückgabetyp von `ProcessURLAsync` ist.  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5. In diesem Beispiel sind Sie nur an der Aufgabe interessiert, die zuerst beendet wird. Verwenden Sie daher <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, um die verbleibenden Aufgaben abzubrechen.  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6. Schließlich warten Sie ab, dass `firstFinishedTask` die Länge des heruntergeladenen Inhalts abruft.  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
    ```  
  
 Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.  
  
## <a name="complete-example"></a>Vollständiges Beispiel  
 Der folgende Code besteht aus der vollständigen Datei „MainWindow.xaml.cs“ für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.  
  
 Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.  
  
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
  
namespace CancelAfterOneTask  
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
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.
            //    // Argument ct carries the message if the Cancel button is chosen.
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Feinabstimmung der Async-Anwendung (C#)](./fine-tuning-your-async-application.md)
- [Asynchrone Programmierung mit „async“ und „await“ (C#)](./index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
