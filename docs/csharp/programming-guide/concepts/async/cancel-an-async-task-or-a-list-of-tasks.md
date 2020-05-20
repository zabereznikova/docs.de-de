---
title: Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 93526f772f79e993767fd8f29087b6caf4e29468
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595717"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a><span data-ttu-id="eb539-102">Abbrechen einer asynchronen Aufgabe oder Aufgabenliste (C#)</span><span class="sxs-lookup"><span data-stu-id="eb539-102">Cancel an async task or a list of tasks (C#)</span></span>

<span data-ttu-id="eb539-103">Sie können eine Schaltfläche einrichten, über die Sie eine asynchrone Anwendung abbrechen können, wenn Sie nicht darauf warten möchten, bis diese beendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb539-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="eb539-104">Anhand der Beispiele in diesem Thema können Sie einer Anwendung, über die der Inhalt einer Website oder einer Liste von Websites heruntergeladen wird, eine Schaltfläche zum Abbrechen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eb539-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="eb539-105">In den Beispielen wird die Benutzeroberfläche verwendet, die in [Feinabstimmung der Async-Anwendung (C#)](./fine-tuning-your-async-application.md) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eb539-105">The examples use the UI that [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="eb539-106">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="eb539-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="cancel-a-task"></a><span data-ttu-id="eb539-107">Abbrechen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="eb539-107">Cancel a task</span></span>

<span data-ttu-id="eb539-108">Im ersten Beispiel wird die Schaltfläche **Abbrechen** einer Aufgabe mit einem einzigen Download zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="eb539-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="eb539-109">Wenn Sie die Schaltfläche auswählen, während die Anwendung Inhalt herunterlädt, wird der Download abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="eb539-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="eb539-110">Das Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="eb539-110">Download the example</span></span>

<span data-ttu-id="eb539-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="eb539-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="eb539-112">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eb539-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="eb539-113">Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-113">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="eb539-114">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS oder AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="eb539-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="eb539-115">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelATask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="eb539-116">Wählen Sie die Taste **F5** aus, um das Projekt auszuführen (oder drücken Sie **STRG**+**F5**, um das Projekt ohne Debuggen auszuführen).</span><span class="sxs-lookup"><span data-stu-id="eb539-116">Choose the **F5** key to run the project (or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

> [!TIP]
> <span data-ttu-id="eb539-117">Wenn Sie das Projekt nicht herunterladen möchten, können Sie die „MainWindow.xaml.cs“-Dateien am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eb539-117">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="eb539-118">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="eb539-118">Build the example</span></span>
 <span data-ttu-id="eb539-119">Mit den folgenden Änderungen wird eine Schaltfläche **Abbrechen** zu einer Anwendung hinzugefügt, die eine Website herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="eb539-119">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="eb539-120">Wenn Sie das Beispiel nicht herunterladen oder erstellen möchten, können Sie sich das Endprodukt im Abschnitt „Vollständige Beispiele“ am Ende dieses Themas ansehen.</span><span class="sxs-lookup"><span data-stu-id="eb539-120">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="eb539-121">Die Änderungen im Code sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="eb539-121">Asterisks mark the changes in the code.</span></span>

 <span data-ttu-id="eb539-122">Um das Beispiel selbst zu erstellen, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **StarterCode** anstelle von **CancelATask** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

 <span data-ttu-id="eb539-123">Fügen Sie dann der Datei „MainWindow.xaml.cs“ dieses Projekts die folgenden Änderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb539-123">Then add the following changes to the MainWindow.xaml.cs file of that project.</span></span>

1. <span data-ttu-id="eb539-124">Deklarieren Sie eine `CancellationTokenSource`-Variable, `cts`, die im Bereich für alle Methoden liegt, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="eb539-124">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="eb539-125">Fügen Sie den folgenden Ereignishandler für die Schaltfläche **Abbrechen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb539-125">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="eb539-126">Der Ereignishandler verwendet die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>-Methode, um `cts` bei Abbruchanforderungen durch den Benutzer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="eb539-126">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. <span data-ttu-id="eb539-127">Nehmen Sie die folgenden Änderungen in `startButton_Click` vor, dem Ereignishandler für die Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="eb539-127">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="eb539-128">Instanziieren Sie die `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="eb539-128">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - <span data-ttu-id="eb539-129">Senden Sie im Aufruf von `AccessTheWebAsync`, wodurch der Inhalt einer bestimmten Website heruntergeladen wird, die <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType>-Eigenschaft von `cts` als Argument.</span><span class="sxs-lookup"><span data-stu-id="eb539-129">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="eb539-130">Die `Token`-Eigenschaft gibt die Meldung weiter, wenn ein Abbruch angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="eb539-130">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="eb539-131">Fügen Sie einen catch-Block hinzu, der eine Meldung angezeigt, wenn der Benutzer den Downloadvorgang abbrechen möchte.</span><span class="sxs-lookup"><span data-stu-id="eb539-131">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="eb539-132">Im folgende Code sind alle Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eb539-132">The following code shows the changes.</span></span>

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. <span data-ttu-id="eb539-133">Verwenden Sie in `AccessTheWebAsync` die <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> - Überladung der `GetAsync`-Methode im <xref:System.Net.Http.HttpClient>-Typ, um den Inhalt einer Website herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="eb539-133">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="eb539-134">Übergeben Sie `ct`, der <xref:System.Threading.CancellationToken>-Parameter von `AccessTheWebAsync`, als zweites Argument.</span><span class="sxs-lookup"><span data-stu-id="eb539-134">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="eb539-135">Das Token enthält die Meldung, wenn der Benutzer die Schaltfläche **Abbrechen** auswählt.</span><span class="sxs-lookup"><span data-stu-id="eb539-135">The token carries the message if the user chooses the **Cancel** button.</span></span>

     <span data-ttu-id="eb539-136">Im folgende Code sind die Änderungen in `AccessTheWebAsync` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eb539-136">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. <span data-ttu-id="eb539-137">Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="eb539-137">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     <span data-ttu-id="eb539-138">Wenn Sie die Schaltfläche **Abbrechen** auswählen, bevor das Programm das Herunterladen des Inhalts abgeschlossen hat, erzeugt das Programm die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="eb539-138">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><span data-ttu-id="eb539-139">Abbrechen einer Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="eb539-139">Cancel a list of tasks</span></span>

<span data-ttu-id="eb539-140">Sie können das vorherige Beispiel so erweitern, dass viele Aufgaben abgebrochen werden, indem Sie jeder Aufgabe die gleiche `CancellationTokenSource`-Instanz zuordnen.</span><span class="sxs-lookup"><span data-stu-id="eb539-140">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="eb539-141">Wenn Sie die Schaltfläche **Abbrechen** auswählen, brechen Sie alle Aufgaben ab, die noch nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="eb539-141">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="eb539-142">Das Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="eb539-142">Download the example</span></span>

<span data-ttu-id="eb539-143">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="eb539-143">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="eb539-144">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eb539-144">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="eb539-145">Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-145">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="eb539-146">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS oder AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="eb539-146">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="eb539-147">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAListOfTasks**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-147">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="eb539-148">Drücken Sie die **F5**-Taste, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eb539-148">Choose the **F5** key to run the project.</span></span>

     <span data-ttu-id="eb539-149">Drücken Sie die Tasten **STRG**+**F5**, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="eb539-149">Choose the **Ctrl**+**F5** keys to run the project without debugging it.</span></span>

<span data-ttu-id="eb539-150">Wenn Sie das Projekt nicht herunterladen möchten, können Sie die „MainWindow.xaml.cs“-Dateien am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eb539-150">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="eb539-151">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="eb539-151">Build the example</span></span>

<span data-ttu-id="eb539-152">Um das Beispiel selbst zu erweitern, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelATask** aus.</span><span class="sxs-lookup"><span data-stu-id="eb539-152">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="eb539-153">Fügen Sie die folgenden Änderungen zu diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb539-153">Add the following changes to that project.</span></span> <span data-ttu-id="eb539-154">Die Änderungen im Programm sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="eb539-154">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="eb539-155">Fügen Sie eine Methode hinzu, um eine Liste von Webadressen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb539-155">Add a method to create a list of web addresses.</span></span>

    ```csharp
    // ***Add a method that creates a list of web addresses.
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
    ```

2. <span data-ttu-id="eb539-156">Rufen Sie die Methode in `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="eb539-156">Call the method in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. <span data-ttu-id="eb539-157">Fügen Sie die folgende Schleife in `AccessTheWebAsync` hinzu, um jede Webadresse in der Liste zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="eb539-157">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. <span data-ttu-id="eb539-158">Da `AccessTheWebAsync` die Längen anzeigt, muss die Methode nichts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="eb539-158">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="eb539-159">Entfernen Sie die return-Anweisung, und ändern Sie den Rückgabetyp der Methode in <xref:System.Threading.Tasks.Task> anstelle von <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="eb539-159">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     <span data-ttu-id="eb539-160">Rufen Sie die Methode über `startButton_Click` auf, indem Sie eine Anweisung anstelle eines Ausdrucks verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb539-160">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. <span data-ttu-id="eb539-161">Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="eb539-161">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     <span data-ttu-id="eb539-162">Wenn Sie die Schaltfläche **Abbrechen** auswählen, bevor die Downloads abgeschlossen sind, enthält die Ausgabe die Längen der Downloads, die vor dem Abbruch abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="eb539-162">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><span data-ttu-id="eb539-163">Vollständige Beispiele</span><span class="sxs-lookup"><span data-stu-id="eb539-163">Complete examples</span></span>

<span data-ttu-id="eb539-164">Die folgenden Abschnitte enthalten den Code für jedes der vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="eb539-164">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="eb539-165">Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="eb539-165">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="eb539-166">Sie können die Projekte von [Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="eb539-166">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="example---cancel-a-task"></a><span data-ttu-id="eb539-167">Beispiel: Abbrechen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="eb539-167">Example - Cancel a task</span></span>

<span data-ttu-id="eb539-168">Der folgende Code ist die vollständige Datei „MainWindow.xaml.cs“ für das Beispiel, in dem eine einzelne Aufgabe abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="eb539-168">The following code is the complete MainWindow.xaml.cs file for the example that cancels a single task.</span></span>

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

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a><span data-ttu-id="eb539-169">Beispiel: Abbrechen einer Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="eb539-169">Example - Cancel a list of tasks</span></span>

<span data-ttu-id="eb539-170">Der folgende Code ist die vollständige Datei „MainWindow.xaml.cs“ für das Beispiel, in dem eine Aufgabenliste abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="eb539-170">The following code is the complete MainWindow.xaml.cs file for the example that cancels a list of tasks.</span></span>

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

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
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
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
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

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="eb539-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb539-171">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="eb539-172">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="eb539-172">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="eb539-173">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="eb539-173">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- [<span data-ttu-id="eb539-174">Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)</span><span class="sxs-lookup"><span data-stu-id="eb539-174">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
