---
title: Eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic) Abbrechen | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="d8c24-102">Abbrechen einer asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8c24-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="d8c24-103">Sie können eine Schaltfläche einrichten, über die Sie eine asynchrone Anwendung abbrechen können, wenn Sie nicht darauf warten möchten, bis diese beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8c24-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="d8c24-104">Anhand der Beispiele in diesem Thema können Sie einer Anwendung, über die der Inhalt einer Website oder einer Liste von Websites heruntergeladen wird, eine Schaltfläche zum Abbrechen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="d8c24-105">Die Beispiele verwenden die Benutzeroberfläche, [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8c24-106">Zum Ausführen der Beispiele müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d8c24-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="d8c24-107"><a name="BKMK_CancelaTask"></a>Eine Aufgabe abbrechen</span><span class="sxs-lookup"><span data-stu-id="d8c24-107"><a name="BKMK_CancelaTask"></a> Cancel a Task</span></span>  
 <span data-ttu-id="d8c24-108">Im ersten Beispiel wird die **Abbrechen** Schaltfläche Aufgabe mit einem einzigen Download.</span><span class="sxs-lookup"><span data-stu-id="d8c24-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="d8c24-109">Wenn Sie die Schaltfläche auswählen, während die Anwendung Inhalt herunterlädt, wird der Download abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="d8c24-110">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="d8c24-110">Downloading the Example</span></span>  
 <span data-ttu-id="d8c24-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d8c24-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="d8c24-112">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8c24-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d8c24-113">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="d8c24-114">In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="d8c24-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="d8c24-115">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelATask** Projekt, und wählen Sie dann **Set as StartUp Project**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="d8c24-116">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="d8c24-117">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="d8c24-118">Wenn Sie das Projekt herunterladen möchten, können Sie die Dateien "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="d8c24-119">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="d8c24-119">Building the Example</span></span>  
 <span data-ttu-id="d8c24-120">Fügen Sie die folgenden Änderungen eine **Abbrechen** Schaltfläche, um eine Anwendung, die eine Website herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="d8c24-121">Wenn Sie das Beispiel nicht herunterladen oder erstellen möchten, können Sie sich das Endprodukt im Abschnitt „Vollständige Beispiele“ am Ende dieses Themas ansehen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="d8c24-122">Die Änderungen im Code sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d8c24-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="d8c24-123">So erstellen Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **StarterCode** als die **Startprojekt** anstelle von **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="d8c24-124">Anschließend fügen Sie der Datei "MainWindow.Xaml.vb" des Projekts.</span><span class="sxs-lookup"><span data-stu-id="d8c24-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="d8c24-125">Deklarieren Sie eine `CancellationTokenSource`-Variable, `cts`, die im Bereich für alle Methoden liegt, die darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="d8c24-126">Fügen Sie den folgenden Ereignishandler für das **Abbrechen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d8c24-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="d8c24-127">Der Ereignishandler verwendet die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>-Methode benachrichtigt `cts` Wenn der Benutzer den Abbruch anfordert.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d8c24-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="d8c24-128">Nehmen Sie die folgenden im Handler für Änderungen das **Start** Schaltfläche `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="d8c24-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="d8c24-129">Instanziieren Sie die `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="d8c24-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="d8c24-130">Im Aufruf von `AccessTheWebAsync`, wodurch der Inhalt einer bestimmten Website heruntergeladen, senden die <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>Eigenschaft `cts` als Argument.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d8c24-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> property of `cts` as an argument.</span></span> <span data-ttu-id="d8c24-131">Die `Token`-Eigenschaft gibt die Meldung weiter, wenn ein Abbruch angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="d8c24-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="d8c24-132">Fügen Sie einen catch-Block hinzu, der eine Meldung angezeigt, wenn der Benutzer den Downloadvorgang abbrechen möchte.</span><span class="sxs-lookup"><span data-stu-id="d8c24-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="d8c24-133">Im folgende Code sind alle Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-133">The following code shows the changes.</span></span>  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  <span data-ttu-id="d8c24-134">In `AccessTheWebAsync`, verwenden Sie die <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>Überladung von der `GetAsync` -Methode in der <xref:System.Net.Http.HttpClient>Typ, um den Inhalt einer Website herunterzuladen.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d8c24-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="d8c24-135">Übergeben Sie `ct`der <xref:System.Threading.CancellationToken>Parameter von `AccessTheWebAsync`, als zweites Argument.</xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="d8c24-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="d8c24-136">Das Token enthält die Meldung, wenn der Benutzer die **Abbrechen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d8c24-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="d8c24-137">Im folgende Code sind die Änderungen in `AccessTheWebAsync` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  <span data-ttu-id="d8c24-138">Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="d8c24-139">Bei Auswahl der **Abbrechen** Schaltfläche, bevor das Programm beendet wird, Herunterladen des Inhalts, das Programm erzeugt die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d8c24-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <span data-ttu-id="d8c24-140"><a name="BKMK_CancelaListofTasks"></a>Eine Aufgabenliste Abbrechen</span><span class="sxs-lookup"><span data-stu-id="d8c24-140"><a name="BKMK_CancelaListofTasks"></a> Cancel a List of Tasks</span></span>  
 <span data-ttu-id="d8c24-141">Sie können das vorherige Beispiel so erweitern, dass viele Aufgaben abgebrochen werden, indem Sie jeder Aufgabe die gleiche `CancellationTokenSource`-Instanz zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="d8c24-142">Bei Auswahl der **Abbrechen** klicken, brechen Sie alle Aufgaben, die noch nicht abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="d8c24-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="d8c24-143">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="d8c24-143">Downloading the Example</span></span>  
 <span data-ttu-id="d8c24-144">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d8c24-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="d8c24-145">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8c24-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d8c24-146">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="d8c24-147">In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="d8c24-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="d8c24-148">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelAListOfTasks** Projekt, und wählen Sie dann **Set as StartUp Project**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="d8c24-149">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="d8c24-150">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="d8c24-151">Wenn Sie das Projekt herunterladen möchten, können Sie die Dateien "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="d8c24-152">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="d8c24-152">Building the Example</span></span>  
 <span data-ttu-id="d8c24-153">Erweitern Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **CancelATask** als die **Startprojekt**.</span><span class="sxs-lookup"><span data-stu-id="d8c24-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="d8c24-154">Fügen Sie die folgenden Änderungen zu diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8c24-154">Add the following changes to that project.</span></span> <span data-ttu-id="d8c24-155">Die Änderungen im Programm sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d8c24-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="d8c24-156">Fügen Sie eine Methode hinzu, um eine Liste von Webadressen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-156">Add a method to create a list of web addresses.</span></span>  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
    ```  
  
2.  <span data-ttu-id="d8c24-157">Rufen Sie die Methode in `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="d8c24-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="d8c24-158">Fügen Sie die folgende Schleife in `AccessTheWebAsync` hinzu, um jede Webadresse in der Liste zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d8c24-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
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
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  <span data-ttu-id="d8c24-159">Da `AccessTheWebAsync` die Längen anzeigt, muss die Methode nichts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d8c24-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="d8c24-160">Entfernen Sie die return-Anweisung, und ändern Sie den Rückgabetyp der Methode in <xref:System.Threading.Tasks.Task>statt <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="d8c24-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
<span data-ttu-id="d8c24-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d8c24-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="d8c24-162">Rufen Sie die Methode über `startButton_Click` auf, indem Sie eine Anweisung anstelle eines Ausdrucks verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8c24-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="d8c24-163">Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8c24-163">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
  
    ```  
  
     <span data-ttu-id="d8c24-164">Bei Auswahl der **Abbrechen** klicken, bevor die Downloads abgeschlossen sind, enthält die Ausgabe die Längen der Downloads, die vor dem Abbruch abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="d8c24-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <span data-ttu-id="d8c24-165"><a name="BKMK_CompleteExamples"></a>Vollständige Beispiele</span><span class="sxs-lookup"><span data-stu-id="d8c24-165"><a name="BKMK_CompleteExamples"></a> Complete Examples</span></span>  
 <span data-ttu-id="d8c24-166">Die folgenden Abschnitte enthalten den Code für jedes der vorherigen Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d8c24-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="d8c24-167">Beachten Sie, dass Sie eine Referenz für <xref:System.Net.Http>.</xref:System.Net.Http> hinzufügen müssen</span><span class="sxs-lookup"><span data-stu-id="d8c24-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="d8c24-168">Sie können die Projekte vom herunterladen [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="d8c24-168">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="d8c24-169">Beispiel zum Abbrechen einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="d8c24-169">Cancel a Task Example</span></span>  
 <span data-ttu-id="d8c24-170">Der folgende Code ist die vollständige "MainWindow.Xaml.vb"-Datei für das Beispiel, das eine einzelne Aufgabe abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-170">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
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
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
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
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="d8c24-171">Beispiel zum Abbrechen einer Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="d8c24-171">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="d8c24-172">Der folgende Code ist die vollständige "MainWindow.Xaml.vb"-Datei für das Beispiel, das eine Liste von Aufgaben abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="d8c24-172">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
  
## <a name="see-also"></a><span data-ttu-id="d8c24-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8c24-173">See Also</span></span>  
 <span data-ttu-id="d8c24-174"><xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="d8c24-174"><xref:System.Threading.CancellationTokenSource></span></span>   
 <span data-ttu-id="d8c24-175"><xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="d8c24-175"><xref:System.Threading.CancellationToken></span></span>   
<span data-ttu-id="d8c24-176"> [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="d8c24-176"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="d8c24-177"> [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="d8c24-177"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="d8c24-178"> [ASYNC-Beispiel: Feinabstimmung der Anwendung](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="d8c24-178"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
