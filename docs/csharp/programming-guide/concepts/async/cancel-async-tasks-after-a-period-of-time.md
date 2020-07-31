---
title: Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)
description: Verwenden Sie die Methode CancellationTokenSource.CancelAfter in C#, um den Abbruch aller zugeordneten Aufgaben zu planen, die in diesem Beispiel nicht innerhalb eines Zeitraums abgeschlossen wurden.
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: f32af1d893c60ac17648f60fa3aa90adaa0383e8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925291"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="096c1-103">Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)</span><span class="sxs-lookup"><span data-stu-id="096c1-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="096c1-104">Sie können einen asynchronen Vorgang nach einem gewissen Zeitraum mithilfe der <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>-Methode abbrechen, wenn Sie nicht auf das Ende des Vorgangs warten möchten.</span><span class="sxs-lookup"><span data-stu-id="096c1-104">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="096c1-105">Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="096c1-105">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="096c1-106">Dieses Beispiel fügt dem in [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelten Code Funktionen zum Herunterladen einer Liste von Websites und Anzeigen der Länge der Inhalte jeder Site hinzu.</span><span class="sxs-lookup"><span data-stu-id="096c1-106">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="096c1-107">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="096c1-107">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-the-example"></a><span data-ttu-id="096c1-108">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="096c1-108">Download the example</span></span>

<span data-ttu-id="096c1-109">Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="096c1-109">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="096c1-110">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="096c1-110">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="096c1-111">Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.</span><span class="sxs-lookup"><span data-stu-id="096c1-111">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="096c1-112">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="096c1-112">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="096c1-113">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterTime**-Projekt und wählen dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="096c1-113">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="096c1-114">Drücken Sie die Taste **F5**, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="096c1-114">Choose the **F5** key to run the project.</span></span> <span data-ttu-id="096c1-115">(Oder drücken Sie **STRG**+**F5**, um das Projekt auszuführen, ohne es zu debuggen.)</span><span class="sxs-lookup"><span data-stu-id="096c1-115">(Or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

6. <span data-ttu-id="096c1-116">Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="096c1-116">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

<span data-ttu-id="096c1-117">Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Dateien „MainWindow.xaml.vb“ und „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.</span><span class="sxs-lookup"><span data-stu-id="096c1-117">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>

## <a name="build-the-example"></a><span data-ttu-id="096c1-118">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="096c1-118">Build the example</span></span>

<span data-ttu-id="096c1-119">Das Beispiel in diesem Thema baut auf dem Projekt auf, das unter [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelt wurde, um eine Aufgabenliste abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="096c1-119">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="096c1-120">Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="096c1-120">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="096c1-121">Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus.</span><span class="sxs-lookup"><span data-stu-id="096c1-121">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="096c1-122">Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.</span><span class="sxs-lookup"><span data-stu-id="096c1-122">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="096c1-123">Zum Angeben einer maximalen Zeitspanne bis zum Abbrechen der Aufgaben fügen Sie den Aufruf von `CancelAfter` in `startButton_Click` hinzu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="096c1-123">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="096c1-124">Die Ergänzung ist mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="096c1-124">The addition is marked with asterisks.</span></span>

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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
```

 <span data-ttu-id="096c1-125">Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="096c1-125">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="096c1-126">Die folgende Ausgabe ist beispielhaft.</span><span class="sxs-lookup"><span data-stu-id="096c1-126">The following output is a sample.</span></span>

```output
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="096c1-127">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="096c1-127">Complete example</span></span>

<span data-ttu-id="096c1-128">Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.cs“ für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="096c1-128">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="096c1-129">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="096c1-129">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="096c1-130">Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="096c1-130">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="096c1-131">Sie können das Projekt hier herunterladen: [Async Sample: Fine Tuning Your Application (Async-Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="096c1-131">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="096c1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="096c1-132">See also</span></span>

- [<span data-ttu-id="096c1-133">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="096c1-133">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="096c1-134">Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)</span><span class="sxs-lookup"><span data-stu-id="096c1-134">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="096c1-135">Cancel an Async Task or a List of Tasks (C#) (Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#))</span><span class="sxs-lookup"><span data-stu-id="096c1-135">Cancel an Async Task or a List of Tasks (C#)</span></span>](./cancel-an-async-task-or-a-list-of-tasks.md)
- [<span data-ttu-id="096c1-136">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="096c1-136">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- <span data-ttu-id="096c1-137">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)</span><span class="sxs-lookup"><span data-stu-id="096c1-137">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
