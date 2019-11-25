---
title: Eine asynchrone Aufgabe oder Aufgabenliste abbrechen
ms.date: 07/20/2015
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
ms.openlocfilehash: 2956582cd0c8e044fcd37ffab13686489a7c854c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347968"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="1ec3d-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ec3d-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>

<span data-ttu-id="1ec3d-103">Sie können eine Schaltfläche einrichten, über die Sie eine asynchrone Anwendung abbrechen können, wenn Sie nicht darauf warten möchten, bis diese beendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="1ec3d-104">Anhand der Beispiele in diesem Thema können Sie einer Anwendung, über die der Inhalt einer Website oder einer Liste von Websites heruntergeladen wird, eine Schaltfläche zum Abbrechen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="1ec3d-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec3d-106">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="BKMK_CancelaTask"></a> <span data-ttu-id="1ec3d-107">Eine Aufgabe abbrechen</span><span class="sxs-lookup"><span data-stu-id="1ec3d-107">Cancel a Task</span></span>

<span data-ttu-id="1ec3d-108">Im ersten Beispiel wird die Schaltfläche **Abbrechen** einer Aufgabe mit einem einzigen Download zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="1ec3d-109">Wenn Sie die Schaltfläche auswählen, während die Anwendung Inhalt herunterlädt, wird der Download abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="1ec3d-110">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1ec3d-110">Downloading the Example</span></span>

<span data-ttu-id="1ec3d-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="1ec3d-112">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="1ec3d-113">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="1ec3d-114">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="1ec3d-115">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelATask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="1ec3d-116">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-116">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="1ec3d-117">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="1ec3d-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="1ec3d-119">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1ec3d-119">Building the Example</span></span>

<span data-ttu-id="1ec3d-120">Mit den folgenden Änderungen wird eine Schaltfläche **Abbrechen** zu einer Anwendung hinzugefügt, die eine Website herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="1ec3d-121">Wenn Sie das Beispiel nicht herunterladen oder erstellen möchten, können Sie sich das Endprodukt im Abschnitt „Vollständige Beispiele“ am Ende dieses Themas ansehen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="1ec3d-122">Die Änderungen im Code sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-122">Asterisks mark the changes in the code.</span></span>

<span data-ttu-id="1ec3d-123">Um das Beispiel selbst zu erstellen, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **StarterCode** anstelle von **CancelATask** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

<span data-ttu-id="1ec3d-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>

1. <span data-ttu-id="1ec3d-125">Deklarieren Sie eine `CancellationTokenSource`-Variable, `cts`, die im Bereich für alle Methoden liegt, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```vb
    Class MainWindow

        ' ***Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="1ec3d-126">Fügen Sie den folgenden Ereignishandler für die Schaltfläche **Abbrechen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="1ec3d-127">Der Ereignishandler verwendet die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>-Methode, um `cts` bei Abbruchanforderungen durch den Benutzer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```vb
    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub
    ```

3. <span data-ttu-id="1ec3d-128">Nehmen Sie die folgenden Änderungen in `startButton_Click` vor, dem Ereignishandler für die Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="1ec3d-129">Instanziieren Sie die `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

      ```vb
      ' ***Instantiate the CancellationTokenSource.
      cts = New CancellationTokenSource()
      ```

    - <span data-ttu-id="1ec3d-130">Senden Sie im Aufruf von `AccessTheWebAsync`, wodurch der Inhalt einer bestimmten Website heruntergeladen wird, die <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType>-Eigenschaft von `cts` als Argument.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="1ec3d-131">Die `Token`-Eigenschaft gibt die Meldung weiter, wenn ein Abbruch angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="1ec3d-132">Fügen Sie einen catch-Block hinzu, der eine Meldung angezeigt, wenn der Benutzer den Downloadvorgang abbrechen möchte.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="1ec3d-133">Im folgende Code sind alle Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-133">The following code shows the changes.</span></span>

      ```vb
      Try
          ' ***Send a token to carry the message if cancellation is requested.
          Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

          resultsTextBox.Text &=
              vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

          ' *** If cancellation is requested, an OperationCanceledException results.
      Catch ex As OperationCanceledException
          resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

      Catch ex As Exception
          resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
      End Try
      ```

4. <span data-ttu-id="1ec3d-134">Verwenden Sie in `AccessTheWebAsync` die <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> - Überladung der `GetAsync`-Methode im <xref:System.Net.Http.HttpClient>-Typ, um den Inhalt einer Website herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="1ec3d-135">Übergeben Sie `ct`, der <xref:System.Threading.CancellationToken>-Parameter von `AccessTheWebAsync`, als zweites Argument.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="1ec3d-136">Das Token enthält die Meldung, wenn der Benutzer die Schaltfläche **Abbrechen** auswählt.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-136">The token carries the message if the user chooses the **Cancel** button.</span></span>

    <span data-ttu-id="1ec3d-137">Im folgende Code sind die Änderungen in `AccessTheWebAsync` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &= vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
    ```

5. <span data-ttu-id="1ec3d-138">If you don’t cancel the program, it produces the following output:</span><span class="sxs-lookup"><span data-stu-id="1ec3d-138">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Ready to download.
    Length of the downloaded string: 158125.
    ```

    <span data-ttu-id="1ec3d-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output:</span><span class="sxs-lookup"><span data-stu-id="1ec3d-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output:</span></span>

    ```console
    Ready to download.
    Download canceled.
    ```

## <a name="BKMK_CancelaListofTasks"></a> <span data-ttu-id="1ec3d-140">Eine Aufgabenliste abbrechen</span><span class="sxs-lookup"><span data-stu-id="1ec3d-140">Cancel a List of Tasks</span></span>

<span data-ttu-id="1ec3d-141">Sie können das vorherige Beispiel so erweitern, dass viele Aufgaben abgebrochen werden, indem Sie jeder Aufgabe die gleiche `CancellationTokenSource`-Instanz zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="1ec3d-142">Wenn Sie die Schaltfläche **Abbrechen** auswählen, brechen Sie alle Aufgaben ab, die noch nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="1ec3d-143">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1ec3d-143">Downloading the Example</span></span>

<span data-ttu-id="1ec3d-144">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="1ec3d-145">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="1ec3d-146">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="1ec3d-147">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="1ec3d-148">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAListOfTasks**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="1ec3d-149">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-149">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="1ec3d-150">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="1ec3d-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="1ec3d-152">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1ec3d-152">Building the Example</span></span>

<span data-ttu-id="1ec3d-153">Um das Beispiel selbst zu erweitern, befolgen Sie Schritt für Schritt die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelATask** aus.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="1ec3d-154">Fügen Sie die folgenden Änderungen zu diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-154">Add the following changes to that project.</span></span> <span data-ttu-id="1ec3d-155">Die Änderungen im Programm sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-155">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="1ec3d-156">Fügen Sie eine Methode hinzu, um eine Liste von Webadressen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-156">Add a method to create a list of web addresses.</span></span>

    ```vb
    ' ***Add a method that creates a list of web addresses.
    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function
    ```

2. <span data-ttu-id="1ec3d-157">Rufen Sie die Methode in `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-157">Call the method in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Call SetUpURLList to make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()
    ```

3. <span data-ttu-id="1ec3d-158">Fügen Sie die folgende Schleife in `AccessTheWebAsync` hinzu, um jede Webadresse in der Liste zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```vb
    ' ***Add a loop to process the list of web addresses.
    For Each url In urlList
        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' Argument ct carries the message if the Cancel button is chosen.
        ' ***Note that the Cancel button can cancel all remaining downloads.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        resultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
    Next
    ```

4. <span data-ttu-id="1ec3d-159">Da `AccessTheWebAsync` die Längen anzeigt, muss die Methode nichts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="1ec3d-160">Entfernen Sie die return-Anweisung, und ändern Sie den Rückgabetyp der Methode in <xref:System.Threading.Tasks.Task> anstelle von <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```vb
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task
    ```

    <span data-ttu-id="1ec3d-161">Rufen Sie die Methode über `startButton_Click` auf, indem Sie eine Anweisung anstelle eines Ausdrucks verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```vb
    Await AccessTheWebAsync(cts.Token)
    ```

5. <span data-ttu-id="1ec3d-162">If you don’t cancel the program, it produces the following output:</span><span class="sxs-lookup"><span data-stu-id="1ec3d-162">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

    <span data-ttu-id="1ec3d-163">Wenn Sie die Schaltfläche **Abbrechen** auswählen, bevor die Downloads abgeschlossen sind, enthält die Ausgabe die Längen der Downloads, die vor dem Abbruch abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="BKMK_CompleteExamples"></a> <span data-ttu-id="1ec3d-164">Vollständige Beispiele</span><span class="sxs-lookup"><span data-stu-id="1ec3d-164">Complete Examples</span></span>

<span data-ttu-id="1ec3d-165">Die folgenden Abschnitte enthalten den Code für jedes der vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="1ec3d-166">Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="1ec3d-167">Sie können die Projekte von [Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-167">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="cancel-a-task-example"></a><span data-ttu-id="1ec3d-168">Beispiel zum Abbrechen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="1ec3d-168">Cancel a Task Example</span></span>

<span data-ttu-id="1ec3d-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' ***Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)
        ' ***Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            ' ***Send a token to carry the message if cancellation is requested.
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

            ' *** If cancellation is requested, an OperationCanceledException results.
        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' ***Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &=
            vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
End Class

' Output for a successful download:

' Ready to download.

' Length of the downloaded string: 158125.

' Or, if you cancel:

' Ready to download.

' Download canceled.
```

### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="1ec3d-170">Beispiel zum Abbrechen einer Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="1ec3d-170">Cancel a List of Tasks Example</span></span>

<span data-ttu-id="1ec3d-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span><span class="sxs-lookup"><span data-stu-id="1ec3d-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

        ' Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).
            Await AccessTheWebAsync(cts.Token)
            '  ***Small change in the display lines.
            resultsTextBox.Text &= vbCrLf & "Downloads complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' ***Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' ***Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' ***Add a loop to process the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' ***Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
    End Function

    ' ***Add a method that creates a list of web addresses.
    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

End Class

' Output if you do not choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Length of the downloaded string: 158124.

' Length of the downloaded string: 204890.

' Length of the downloaded string: 175488.

' Length of the downloaded string: 145790.

' Downloads complete.

'  Sample output if you choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Downloads canceled.
```

## <a name="see-also"></a><span data-ttu-id="1ec3d-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ec3d-172">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="1ec3d-173">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ec3d-173">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
- <span data-ttu-id="1ec3d-174">[Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Feinabstimmung der Async-Anwendung (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1ec3d-174">[Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)</span></span>
- <span data-ttu-id="1ec3d-175">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung der Anwendung)</span><span class="sxs-lookup"><span data-stu-id="1ec3d-175">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
