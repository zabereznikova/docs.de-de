---
title: Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 770655005a3cf9cd13eb13cff1ca1d7e291e54e8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)
Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.  
  
 Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen. Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter. In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet. Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet. Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.  
  
> [!NOTE]
>  Zum Ausführen des Beispiels muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.  
  
## <a name="downloading-the-example"></a>Herunterladen des Beispiels  
 Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) herunterladen und anschließend die folgenden Schritte ausführen.  
  
1.  Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2.  Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
3.  Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.  
  
4.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt **ProcessTasksAsTheyFinish** und wählen dann **Als Startprojekt festlegen** aus.  
  
5.  Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
6.  Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.  
  
 Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Datei „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.  
  
## <a name="building-the-example"></a>Erstellen des Beispiels  
 In diesem Beispiel wird ein Code hinzugefügt, der in [Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) entwickelt wurde und die gleiche Benutzeroberfläche verwendet.  
  
 Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAfterOneTask** aus. Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu. Die Änderungen sind mit Sternchen gekennzeichnet.  
  
 Das Projekt **CancelAfterOneTask** enthält bereits eine Abfrage, die eine Auflistung von Aufgaben erstellt, während sie ausgeführt wird. Jeder Aufruf von `ProcessURLAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.  
  
```csharp  
IEnumerable<Task<int>> downloadTasksQuery =  
    from url in urlList select ProcessURL(url, client, ct);  
```  
  
 Nehmen Sie in der Datei „MainWindow.xaml.cs“ des Projekts die folgenden Änderungen an der `AccessTheWebAsync`-Methode vor.  
  
-   Führen Sie die Abfrage aus, indem Sie <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> anstelle von <xref:System.Linq.Enumerable.ToArray%2A> anwenden.  
  
    ```csharp  
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
    ```  
  
-   Fügen Sie eine While-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt.  
  
    1.  Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.  
  
        ```csharp  
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
        ```  
  
    2.  Entfernt die entsprechende Aufgabe aus der Auflistung.  
  
        ```csharp  
        downloadTasks.Remove(firstFinishedTask);  
        ```  
  
    3.  Erwartet `firstFinishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird. Die Variable `firstFinishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TReturn` eine ganze Zahl ist. Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.  
  
        ```csharp  
        int length = await firstFinishedTask;  
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
        ```  
  
 Sie sollten das Projekt mehrmals ausführen, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.  
  
> [!CAUTION]
>  Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen. Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen. Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](http://go.microsoft.com/fwlink/?LinkId=260810).  
  
## <a name="complete-example"></a>Vollständiges Beispiel  
 Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.cs“ für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.  
  
 Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.  
  
 Sie können das Projekt von [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) herunterladen.  
  
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
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
            }  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
 <xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Feinabstimmung der Async-Anwendung (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](../../../../csharp/programming-guide/concepts/async/index.md)   
 [Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)](http://go.microsoft.com/fwlink/?LinkId=255046)

