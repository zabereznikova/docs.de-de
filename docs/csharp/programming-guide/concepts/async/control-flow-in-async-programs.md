---
title: Ablaufsteuerung in asynchronen Programmen (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 99f80a86f14179c5f270064a9f96e35f8611ef13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204445"
---
# <a name="control-flow-in-async-programs-c"></a><span data-ttu-id="ebaba-102">Ablaufsteuerung in asynchronen Programmen (C#)</span><span class="sxs-lookup"><span data-stu-id="ebaba-102">Control flow in async programs (C#)</span></span>

<span data-ttu-id="ebaba-103">Sie können asynchrone Programme mithilfe der Schlüsselwörter `async` und `await` einfacher schreiben und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ebaba-103">You can write and maintain asynchronous programs more easily by using the `async` and `await` keywords.</span></span> <span data-ttu-id="ebaba-104">Möglicherweise könnten Sie jedoch die Ergebnisse überraschen, wenn Sie die Funktionsweise Ihres Programms nicht verstehen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="ebaba-105">In diesem Thema wird die Ablaufsteuerung durch ein einfaches asynchrones Programm nachvollzogen, um darzustellen, wann die Steuerung von einer Methode zu einer anderen springt und welche Informationen jedes Mal übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ebaba-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>

<span data-ttu-id="ebaba-106">Im Allgemeinen markieren Sie Methoden mit asynchronem Code mithilfe des [async (C#)](../../../language-reference/keywords/async.md)-Modifizierers.</span><span class="sxs-lookup"><span data-stu-id="ebaba-106">In general, you mark methods that contain asynchronous code with the [async (C#)](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="ebaba-107">In einer Methode, die mit einem asynchronen Modifizierer markiert ist, können Sie einen [await (C#)](../../../language-reference/operators/await.md)-Operator verwenden, um anzugeben, wo die Methode anhält, um darauf zu warten, dass ein aufgerufener asynchroner Prozess abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-107">In a method that's marked with an async modifier, you can use an [await (C#)](../../../language-reference/operators/await.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="ebaba-108">Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await (C#)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="ebaba-108">For more information, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="ebaba-109">Im folgenden Beispiel werden asynchrone Methoden verwendet, um den Inhalt einer angegebenen Website als Zeichenfolge herunterzuladen und um die Länge der Zeichenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-109">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="ebaba-110">Das Beispiel enthält die folgenden beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="ebaba-110">The example contains the following two methods.</span></span>

- <span data-ttu-id="ebaba-111">`startButton_Click`, die `AccessTheWebAsync` aufruft und das Ergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-111">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>

- <span data-ttu-id="ebaba-112">`AccessTheWebAsync`, die den Inhalt einer Website als Zeichenfolge herunterlädt und die Länge der Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-112">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="ebaba-113">`AccessTheWebAsync` verwendet eine asynchrone <xref:System.Net.Http.HttpClient>-Methode, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, um den Inhalt herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-113">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>

<span data-ttu-id="ebaba-114">Nummerierte Ausgabezeilen werden über das Programm verteilt an strategischen Stellen angezeigt, die dabei helfen sollen, die Ausführung des Programms nachzuvollziehen und zu verdeutlichen, was an den markierten Punkten geschieht.</span><span class="sxs-lookup"><span data-stu-id="ebaba-114">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="ebaba-115">Die Ausgabezeilen werden durchgehend von "ONE" (Eins) bis "SIX" (Sechs) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ebaba-115">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="ebaba-116">Die Bezeichnungen entsprechen der Reihenfolge, in der das Programm diese Codezeilen erreicht.</span><span class="sxs-lookup"><span data-stu-id="ebaba-116">The labels represent the order in which the program reaches these lines of code.</span></span>

<span data-ttu-id="ebaba-117">Im folgenden Code wird die Gliederung des Programms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-117">The following code shows an outline of the program.</span></span>

```csharp
public partial class MainWindow : Window
{
    // . . .
    private async void startButton_Click(object sender, RoutedEventArgs e)
    {
        // ONE
        Task<int> getLengthTask = AccessTheWebAsync();

        // FOUR
        int contentLength = await getLengthTask;

        // SIX
        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {contentLength}.\r\n";
    }

    async Task<int> AccessTheWebAsync()
    {
        // TWO
        HttpClient client = new HttpClient();
        Task<string> getStringTask =
            client.GetStringAsync("https://msdn.microsoft.com");

        // THREE
        string urlContents = await getStringTask;

        // FIVE
        return urlContents.Length;
    }
}
```

<span data-ttu-id="ebaba-118">An jeder der mit "ONE" bis "SIX" bezeichneten Stellen werden Informationen über den aktuellen Status des Programms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-118">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="ebaba-119">Es wird die folgende Ausgabe generiert:</span><span class="sxs-lookup"><span data-stu-id="ebaba-119">The following output is produced:</span></span>

```output
ONE:   Entering startButton_Click.
           Calling AccessTheWebAsync.

TWO:   Entering AccessTheWebAsync.
           Calling HttpClient.GetStringAsync.

THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.

FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.

FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.

SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.

Length of the downloaded string: 33946.
```

## <a name="set-up-the-program"></a><span data-ttu-id="ebaba-120">Einrichten des Programms</span><span class="sxs-lookup"><span data-stu-id="ebaba-120">Set up the program</span></span>

<span data-ttu-id="ebaba-121">Sie können den Code, der in diesem Thema verwendet wird, von MSDN herunterladen oder Sie können ihn selbst erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-121">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaba-122">Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ebaba-122">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="download-the-program"></a><span data-ttu-id="ebaba-123">Herunterladen des Programms</span><span class="sxs-lookup"><span data-stu-id="ebaba-123">Download the program</span></span>

<span data-ttu-id="ebaba-124">Sie können die Anwendung für dieses Thema von [Asynchrones Beispiel: Ablaufsteuerung in asynchronen Programmen](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-124">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="ebaba-125">Mithilfe der folgenden Schritte wird das Programm geöffnet und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-125">The following steps open and run the program.</span></span>

1. <span data-ttu-id="ebaba-126">Entzippen Sie die heruntergeladene Datei und starten Sie anschließend Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebaba-126">Unzip the downloaded file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="ebaba-127">Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-127">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="ebaba-128">Navigieren Sie zu dem Ordner, der den entzippten Beispielcode enthält, öffnen Sie die Projektmappendatei (SLN) und drücken Sie dann die **F5**-TASTE, um das Projekt zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-128">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the **F5** key to build and run the project.</span></span>

### <a name="create-the-program-yourself"></a><span data-ttu-id="ebaba-129">Das Programm selbst erstellen</span><span class="sxs-lookup"><span data-stu-id="ebaba-129">Create the program Yourself</span></span>

<span data-ttu-id="ebaba-130">Das folgende Windows Presentation Foundation (WPF)-Projekt enthält das Codebeispiel für dieses Thema.</span><span class="sxs-lookup"><span data-stu-id="ebaba-130">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>

<span data-ttu-id="ebaba-131">Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ebaba-131">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="ebaba-132">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebaba-132">Start Visual Studio.</span></span>

2. <span data-ttu-id="ebaba-133">Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ebaba-133">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="ebaba-134">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-134">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="ebaba-135">Wählen Sie die Kategorie **Installiert** > **Visual C#**  > **Windows Desktop** und dann aus der Liste der Projektvorlagen **WPF-App** aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-135">Choose the **Installed** > **Visual C#** > **Windows Desktop** category, and then choose **WPF App** from the list of project templates.</span></span>

4. <span data-ttu-id="ebaba-136">Geben Sie `AsyncTracer` als Name für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-136">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="ebaba-137">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-137">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="ebaba-138">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-138">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="ebaba-139">Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-139">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="ebaba-140">Ersetzen Sie den automatisch generierten Code in der **XAML**-Ansicht der Datei „MainWindow.xaml“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="ebaba-140">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```csharp
    <Window
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"
            Title="Control Flow Trace" Height="350" Width="592">
        <Grid>
            <Button x:Name="startButton" Content="Start
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>
        </Grid>
    </Window>
    ```

     <span data-ttu-id="ebaba-141">Ein einfaches Fenster, das ein Textfeld und eine Schaltfläche enthält, wird in der **Entwurfsansicht** der Datei „MainWindow.xaml“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-141">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

7. <span data-ttu-id="ebaba-142">Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebaba-142">Add a reference for <xref:System.Net.Http>.</span></span>

8. <span data-ttu-id="ebaba-143">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="ebaba-143">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

9. <span data-ttu-id="ebaba-144">Ersetzen Sie den Code in „MainWindow.xaml.cs“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="ebaba-144">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

    // Add a using directive and a reference for System.Net.Http;
    using System.Net.Http;

    namespace AsyncTracer
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                InitializeComponent();
            }

            private async void startButton_Click(object sender, RoutedEventArgs e)
            {
                // The display lines in the example lead you through the control shifts.
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +
                    "           Calling AccessTheWebAsync.\r\n";

                Task<int> getLengthTask = AccessTheWebAsync();

                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is started.\r\n" +
                    "           About to await getLengthTask -- no caller to return to.\r\n";

                int contentLength = await getLengthTask;

                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is finished.\r\n" +
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +
                    "           About to display contentLength and exit.\r\n";

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }

            async Task<int> AccessTheWebAsync()
            {
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";

                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";

                // GetStringAsync returns a Task<string>.
                Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");

                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +
                    "           Task getStringTask is started.";

                // AccessTheWebAsync can continue to work until getStringTask is awaited.

                resultsTextBox.Text +=
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";

                // Retrieve the website contents when task is complete.
                string urlContents = await getStringTask;

                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +
                    "\r\n           Task getStringTask is complete." +
                    "\r\n           Processing the return statement." +
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";

                return urlContents.Length;
            }
        }
    }
    ```

10. <span data-ttu-id="ebaba-145">Drücken Sie die Taste **F5**, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="ebaba-145">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="ebaba-146">Die folgende Ausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ebaba-146">The following output appears:</span></span>

    ```output
    ONE:   Entering startButton_Click.
               Calling AccessTheWebAsync.

    TWO:   Entering AccessTheWebAsync.
               Calling HttpClient.GetStringAsync.

    THREE: Back in AccessTheWebAsync.
               Task getStringTask is started.
               About to await getStringTask & return a Task<int> to startButton_Click.

    FOUR:  Back in startButton_Click.
               Task getLengthTask is started.
               About to await getLengthTask -- no caller to return to.

    FIVE:  Back in AccessTheWebAsync.
               Task getStringTask is complete.
               Processing the return statement.
               Exiting from AccessTheWebAsync.

    SIX:   Back in startButton_Click.
               Task getLengthTask is finished.
               Result from AccessTheWebAsync is stored in contentLength.
               About to display contentLength and exit.

    Length of the downloaded string: 33946.
    ```

## <a name="trace-the-program"></a><span data-ttu-id="ebaba-147">Ablaufverfolgung für das Programm durchführen</span><span class="sxs-lookup"><span data-stu-id="ebaba-147">Trace the program</span></span>

### <a name="steps-one-and-two"></a><span data-ttu-id="ebaba-148">Schritte EINS und ZWEI</span><span class="sxs-lookup"><span data-stu-id="ebaba-148">Steps ONE and TWO</span></span>

<span data-ttu-id="ebaba-149">Durch die ersten beiden Ausgabezeilen wird der Pfad verfolgt, während `startButton_Click``AccessTheWebAsync` aufruft und `AccessTheWebAsync` die asynchrone <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> aufruft.</span><span class="sxs-lookup"><span data-stu-id="ebaba-149">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="ebaba-150">Im folgenden Bild werden die Aufrufe von Methode zu Methode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-150">The following image outlines the calls from method to method.</span></span>

<span data-ttu-id="ebaba-151">![Schritte EINS und ZWEI](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="ebaba-151">![Steps ONE and TWO](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>

<span data-ttu-id="ebaba-152">Der Rückgabetyp sowohl von `AccessTheWebAsync` als auch von `client.GetStringAsync` ist <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="ebaba-152">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="ebaba-153">Für `AccessTheWebAsync` ist TResult eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="ebaba-153">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="ebaba-154">Für `GetStringAsync` ist TResult eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ebaba-154">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="ebaba-155">Weitere Informationen über Rückgabetypen asynchroner Methoden finden Sie unter [Async Return Types (C#) (Async-Rückgabetypen (C#))](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="ebaba-155">For more information about async method return types, see [Async Return Types (C#)](./async-return-types.md).</span></span>

<span data-ttu-id="ebaba-156">Eine asynchrone Methode, die eine Aufgabe zurückgibt, gibt eine Aufgabeninstanz zurück, wenn die Steuerung wieder zum Aufrufer zurückwechselt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-156">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="ebaba-157">Die Steuerung kehrt von einer asynchronen Methode wieder zu deren Aufrufer zurück, wenn entweder ein `await`-Operator in der aufgerufenen Methode auftritt oder die aufgerufene Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-157">Control returns from an async method to its caller either when an `await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="ebaba-158">Durch die durchgehend mit "THREE" (Drei) bis "SIX" (Sechs) bezeichneten Ausgabezeilen wird dieser Teil des Prozesses verfolgt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-158">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>

### <a name="step-three"></a><span data-ttu-id="ebaba-159">Schritt DREI</span><span class="sxs-lookup"><span data-stu-id="ebaba-159">Step THREE</span></span>

<span data-ttu-id="ebaba-160">In `AccessTheWebAsync` wird die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> aufgerufen, um den Inhalt der Zielwebseite herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-160">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="ebaba-161">Die Steuerung kehrt von `client.GetStringAsync` zu `AccessTheWebAsync` zurück, wenn `client.GetStringAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-161">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>

 <span data-ttu-id="ebaba-162">Die `client.GetStringAsync`-Methode gibt eine Zeichenfolgenaufgabe zurück, die der `getStringTask`-Variablen in `AccessTheWebAsync` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-162">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="ebaba-163">Die folgende Zeile im Beispielprogramm zeigt den Aufruf von `client.GetStringAsync` und die Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="ebaba-163">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 <span data-ttu-id="ebaba-164">Sie können sich die Aufgabe als eine Zusage von `client.GetStringAsync` vorstellen, schließlich eine tatsächliche Zeichenfolge zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-164">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="ebaba-165">In der Zwischenzeit, wenn `AccessTheWebAsync` auszuführende Aufgaben hat, die nicht von der zugesagten Zeichenfolge von `client.GetStringAsync` abhängen, können diese Aufgaben fortgesetzt werden, während `client.GetStringAsync` wartet.</span><span class="sxs-lookup"><span data-stu-id="ebaba-165">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="ebaba-166">Im Beispiel bieten die folgenden, mit „THREE“ bezeichneten Ausgabezeilen die Gelegenheit, um unabhängige Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebaba-166">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 <span data-ttu-id="ebaba-167">Durch die folgende Anweisung wird die Ausführung in `AccessTheWebAsync` angehalten, wenn `getStringTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-167">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>

```csharp
string urlContents = await getStringTask;
```

 <span data-ttu-id="ebaba-168">Das folgende Bild zeigt die Ablaufsteuerung von `client.GetStringAsync` bis zur Zuweisung von `getStringTask` und von der Erstellung von `getStringTask` bis zur Anwendung eines await-Operators an.</span><span class="sxs-lookup"><span data-stu-id="ebaba-168">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an await operator.</span></span>

 <span data-ttu-id="ebaba-169">![Schritt DREI](./media/asynctrace-three.png "AsyncTrace-Three")</span><span class="sxs-lookup"><span data-stu-id="ebaba-169">![Step THREE](./media/asynctrace-three.png "AsyncTrace-Three")</span></span>

 <span data-ttu-id="ebaba-170">Durch den await-Ausdruck wird `AccessTheWebAsync` angehalten, bis `client.GetStringAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-170">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="ebaba-171">In der Zwischenzeit kehrt die Steuerung zum Aufrufer von `AccessTheWebAsync`, `startButton_Click`, zurück.</span><span class="sxs-lookup"><span data-stu-id="ebaba-171">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>

> [!NOTE]
> <span data-ttu-id="ebaba-172">In der Regel warten Sie sofort auf den Aufruf einer asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="ebaba-172">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="ebaba-173">Beispielsweise könnte die folgende Zuweisung den vorherigen Code ersetzen, der `getStringTask` erstellt und anschließend darauf wartet: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span><span class="sxs-lookup"><span data-stu-id="ebaba-173">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span></span>
>
> <span data-ttu-id="ebaba-174">In diesem Thema wird der await-Operator später angewendet, um die Ausgabezeilen anzupassen, die die Ablaufsteuerung durch das Programm markieren.</span><span class="sxs-lookup"><span data-stu-id="ebaba-174">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>

### <a name="step-four"></a><span data-ttu-id="ebaba-175">Schritt VIER</span><span class="sxs-lookup"><span data-stu-id="ebaba-175">Step FOUR</span></span>

<span data-ttu-id="ebaba-176">Der deklarierte Rückgabetyp von `AccessTheWebAsync` ist `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="ebaba-176">The declared return type of `AccessTheWebAsync` is `Task<int>`.</span></span> <span data-ttu-id="ebaba-177">Wenn `AccessTheWebAsync` angehalten wird, wird daher eine Ganzzahlaufgabe an `startButton_Click` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ebaba-177">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="ebaba-178">Sie sollten verstanden haben, dass die zurückgegebene Aufgabe nicht `getStringTask` ist.</span><span class="sxs-lookup"><span data-stu-id="ebaba-178">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="ebaba-179">Die zurückgegebene Aufgabe ist eine neue Ganzzahlaufgabe, die die verbleibenden Aufgaben in der angehaltenen Methode, `AccessTheWebAsync`, darstellt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-179">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="ebaba-180">Die Aufgabe ist eine Zusage von `AccessTheWebAsync`, eine ganze Zahl zu erzeugen, wenn die Aufgabe abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-180">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>

<span data-ttu-id="ebaba-181">Die folgende Anweisung weist diese Aufgabe der `getLengthTask`-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="ebaba-181">The following statement assigns this task to the `getLengthTask` variable.</span></span>

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 <span data-ttu-id="ebaba-182">Wie in `AccessTheWebAsync` kann `startButton_Click` mit Aufgaben fortsetzen, die nicht von den Ergebnissen der asynchronen Aufgabe (`getLengthTask`) abhängen, bis diese Aufgabe erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-182">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="ebaba-183">Die folgenden Ausgabezeilen stellen diese Aufgaben dar.</span><span class="sxs-lookup"><span data-stu-id="ebaba-183">The following output lines represent that work.</span></span>

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 <span data-ttu-id="ebaba-184">Die Ausführung von `startButton_Click` wird angehalten, wenn `getLengthTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-184">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="ebaba-185">Durch die folgende Zuweisungsanweisung wird `startButton_Click` angehalten, bis `AccessTheWebAsync` abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ebaba-185">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="ebaba-186">In der folgenden Abbildung veranschaulichen die Pfeile die Ablaufsteuerung vom await-Ausdruck in `AccessTheWebAsync` zur Zuweisung eines Werts an `getLengthTask`, gefolgt von normaler Verarbeitung in `startButton_Click` bis `getLengthTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaba-186">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>

 <span data-ttu-id="ebaba-187">![Schritt VIER](./media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="ebaba-187">![Step FOUR](./media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>

### <a name="step-five"></a><span data-ttu-id="ebaba-188">Schritt FÜNF</span><span class="sxs-lookup"><span data-stu-id="ebaba-188">Step FIVE</span></span>

<span data-ttu-id="ebaba-189">Wenn `client.GetStringAsync` signalisiert, dass es abgeschlossen ist, wird die Verarbeitung in `AccessTheWebAsync` aus dem Anhalten freigegeben und kann nach dem await-Ausdruck fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ebaba-189">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="ebaba-190">Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung dar.</span><span class="sxs-lookup"><span data-stu-id="ebaba-190">The following lines of output represent the resumption of processing.</span></span>

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 <span data-ttu-id="ebaba-191">Der Operand der return-Anweisung, `urlContents.Length`, wird in der Aufgabe gespeichert, die `AccessTheWebAsync` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-191">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="ebaba-192">Der await-Ausdruck ruft diesen Wert von `getLengthTask` in `startButton_Click` ab.</span><span class="sxs-lookup"><span data-stu-id="ebaba-192">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>

 <span data-ttu-id="ebaba-193">Im folgenden Bild wird die Übertragung der Steuerung gezeigt, nachdem `client.GetStringAsync` (und `getStringTask`) abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="ebaba-193">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>

 <span data-ttu-id="ebaba-194">![Schritt FÜNF](./media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="ebaba-194">![Step FIVE](./media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>

 <span data-ttu-id="ebaba-195">`AccessTheWebAsync` wird bis zum Abschluss ausgeführt und die Steuerung kehrt zu `startButton_Click` zurück, das den Abschluss erwartet.</span><span class="sxs-lookup"><span data-stu-id="ebaba-195">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>

### <a name="step-six"></a><span data-ttu-id="ebaba-196">Schritt SECHS</span><span class="sxs-lookup"><span data-stu-id="ebaba-196">Step SIX</span></span>

<span data-ttu-id="ebaba-197">Wenn `AccessTheWebAsync` signalisiert, dass es abgeschlossen ist, kann die Verarbeitung nach der await-Anweisung in `startButton_Async` fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ebaba-197">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="ebaba-198">Für das Programm gibt es eigentlich nichts mehr zu tun.</span><span class="sxs-lookup"><span data-stu-id="ebaba-198">In fact, the program has nothing more to do.</span></span>

<span data-ttu-id="ebaba-199">Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung in `startButton_Async` dar:</span><span class="sxs-lookup"><span data-stu-id="ebaba-199">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 <span data-ttu-id="ebaba-200">Der await-Ausdruck ruft von `getLengthTask` den ganzzahligen Wert ab, der der Operand der return-Anweisung in `AccessTheWebAsync` ist.</span><span class="sxs-lookup"><span data-stu-id="ebaba-200">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="ebaba-201">Die folgende Anweisung weist diesen Wert der `contentLength`-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="ebaba-201">The following statement assigns that value to the `contentLength` variable.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="ebaba-202">Im folgenden Bild wird die Rückgabe der Steuerung von `AccessTheWebAsync` an `startButton_Click` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebaba-202">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>

 <span data-ttu-id="ebaba-203">![Schritt SECHS](./media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="ebaba-203">![Step SIX](./media/asynctrace-six.png "AsyncTrace-SIX")</span></span>

## <a name="see-also"></a><span data-ttu-id="ebaba-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebaba-204">See also</span></span>

- [<span data-ttu-id="ebaba-205">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="ebaba-205">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="ebaba-206">Asynchrone Rückgabetypen (C#)</span><span class="sxs-lookup"><span data-stu-id="ebaba-206">Async Return Types (C#)</span></span>](./async-return-types.md)
- [<span data-ttu-id="ebaba-207">Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)</span><span class="sxs-lookup"><span data-stu-id="ebaba-207">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="ebaba-208">Async Sample: Ablaufsteuerung in asynchronen Programmen (C# und Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebaba-208">Async Sample: Control Flow in Async Programs (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
