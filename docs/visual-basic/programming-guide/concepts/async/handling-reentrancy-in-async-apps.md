---
title: Ablauf des erneuten Eintretens in asynchronen Anwendungen
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: cd8b43aa9b2373b5ce038e5007678778201f0746
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354264"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="d1339-102">Handling Reentrancy in Async Apps (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1339-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>

<span data-ttu-id="d1339-103">Wenn Sie asynchronen Code in der App einschließen, sollten Sie erneutes Eintreten, also den erneuten Beginn eines asynchronen Vorgangs vor seinem Abschließen, berücksichtigen und möglicherweise verhindern.</span><span class="sxs-lookup"><span data-stu-id="d1339-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="d1339-104">Wenn Sie Möglichkeiten für erneutes Eintreten nicht identifizieren und behandeln, kann dies zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="d1339-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

> [!NOTE]
> <span data-ttu-id="d1339-105">Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="d1339-105">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="d1339-106">Für die App-Entwicklung ist ab sofort mindestens Transport Layer Security (TLS) Version 1.2 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d1339-106">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="d1339-107">Wenn Ihre App auf eine .NET Framework-Version vor 4.7 ausgerichtet ist, lesen Sie den Artikel [Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="d1339-107">If your app targets a .NET framework version earlier than 4.7, please refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md)</span></span> 

## <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="d1339-108">Erkennen von Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="d1339-108">Recognizing Reentrancy</span></span>

<span data-ttu-id="d1339-109">Im Beispiel in diesem Thema entscheiden sich Benutzer für eine Schaltfläche **Start**, um eine asynchrone App zu initiieren, mit der eine Reihe von Websites heruntergeladen und die Gesamtanzahl der heruntergeladenen Bytes berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-109">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="d1339-110">Eine synchrone Version des Beispiels würde auf die gleiche Weise reagieren, unabhängig davon, wie oft ein Benutzer die Schaltfläche auswählt, da diese Ereignisse nach dem ersten Mal vom UI-Thread ignoriert werden, bis die Anwendung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d1339-110">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="d1339-111">In einer asynchronen App reagiert der UI-Thread weiterhin, und Sie können möglicherweise erneut in den asynchronen Vorgang eintreten, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d1339-111">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="d1339-112">Im folgenden Beispiel wird die erwartete Ausgabe bei einmaliger Betätigung der Schaltfläche **Start** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-112">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="d1339-113">Eine Liste der heruntergeladenen Websites wird mit der Größe, in Bytes für jede Site, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-113">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="d1339-114">Die Gesamtanzahl von Bytes wird am Ende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-114">The total number of bytes appears at the end.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="d1339-115">Wenn der Benutzer die Schaltfläche allerdings mehrmals auswählt, wird der Ereignishandler wiederholt aufgerufen, und der Downloadvorgang beginnt jedes Mal erneut.</span><span class="sxs-lookup"><span data-stu-id="d1339-115">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="d1339-116">Daher werden mehrere asynchrone Vorgänge gleichzeitig ausgeführt, die Ausgabe überlappt mit den Ergebnissen, und die Gesamtzahl der Bytes ist verwirrend.</span><span class="sxs-lookup"><span data-stu-id="d1339-116">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="d1339-117">Sie können den Code, der diese Ausgabe erzeugt, überprüfen, indem Sie einen Bildlauf zum Ende dieses Themas durchführen.</span><span class="sxs-lookup"><span data-stu-id="d1339-117">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="d1339-118">Sie können mit dem Code experimentieren, indem Sie die Projektmappe auf den lokalen Computer herunterladen und das WebsiteDownload-Projekt ausführen, oder, indem Sie den Code am Ende dieses Themas zum Erstellen Ihres eigenen Projekts verwenden. Weitere Informationen und Anweisungen finden Sie unter [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="d1339-118">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="d1339-119">Umgang mit Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="d1339-119">Handling Reentrancy</span></span>

<span data-ttu-id="d1339-120">Sie können das erneute Eintreten auf verschiedene Weise behandeln, je nachdem, was von der App ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1339-120">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="d1339-121">In diesem Thema werden die folgenden Beispiele zur Veranschaulichung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d1339-121">This topic presents the following examples:</span></span>

- [<span data-ttu-id="d1339-122">Die Schaltfläche „Start“ deaktivieren</span><span class="sxs-lookup"><span data-stu-id="d1339-122">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="d1339-123">Deaktivieren der Schaltfläche **Start**, während der Vorgang ausgeführt wird, sodass der Benutzer ihn nicht unterbrechen kann</span><span class="sxs-lookup"><span data-stu-id="d1339-123">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="d1339-124">Den Vorgang abbrechen und neu starten</span><span class="sxs-lookup"><span data-stu-id="d1339-124">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="d1339-125">Abbrechen aller Vorgänge, die noch ausgeführt werden, wenn der Benutzer die Schaltfläche **Start** erneut anklickt, sodass nur der zuletzt angeforderte Vorgang fortgesetzt wird</span><span class="sxs-lookup"><span data-stu-id="d1339-125">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="d1339-126">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="d1339-126">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="d1339-127">Alle angeforderten Vorgänge asynchron ausführen lassen, die Anzeige der Ausgabe allerdings koordinieren, damit die Ergebnisse der einzelnen Vorgänge zusammen und in Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-127">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="d1339-128">Die Schaltfläche „Start“ deaktivieren</span><span class="sxs-lookup"><span data-stu-id="d1339-128">Disable the Start Button</span></span>

<span data-ttu-id="d1339-129">Sie können die Schaltfläche **Start** während eines ausführenden Vorgangs blockieren, indem Sie die Schaltfläche oben im `StartButton_Click`-Ereignishandler deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1339-129">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="d1339-130">Sie können die Schaltfläche aus einem `Finally`-Block erneut aktivieren, sobald der Vorgang beendet ist, damit Benutzer die App erneut ausführen können.</span><span class="sxs-lookup"><span data-stu-id="d1339-130">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="d1339-131">Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-131">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="d1339-132">Sie können Änderungen am Code am Ende dieses Themas hinzufügen, oder Sie können die fertige App unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d1339-132">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="d1339-133">Der Projektname ist "DisableStartButton".</span><span class="sxs-lookup"><span data-stu-id="d1339-133">The project name is DisableStartButton.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

<span data-ttu-id="d1339-134">Aufgrund der Änderungen reagiert die Schaltfläche nicht, während die Websites von `AccessTheWebAsync` heruntergeladen werden, sodass ein erneutes Eintreten in den Prozess nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d1339-134">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="d1339-135">Den Vorgang abbrechen und neu starten</span><span class="sxs-lookup"><span data-stu-id="d1339-135">Cancel and Restart the Operation</span></span>

<span data-ttu-id="d1339-136">Anstatt die Schaltfläche **Start** zu deaktivieren, kann die Schaltfläche aktiv bleiben. Wenn der Benutzer die Schaltfläche dann erneut anklickt, brechen Sie den bereits ausgeführten Vorgang ab und lassen den zuletzt begonnenen Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="d1339-136">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="d1339-137">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="d1339-137">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="d1339-138">Um dieses Szenario festzulegen, nehmen Sie am grundlegenden Code aus [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample) folgende Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="d1339-138">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="d1339-139">Sie können die fertige App auch unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d1339-139">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="d1339-140">Der Name dieses Projekts lautet "CancelAndRestart".</span><span class="sxs-lookup"><span data-stu-id="d1339-140">The name of this project is CancelAndRestart.</span></span>

1. <span data-ttu-id="d1339-141">Deklarieren Sie eine <xref:System.Threading.CancellationTokenSource>-Variable, `cts`, die im Bereich für alle Methoden liegt.</span><span class="sxs-lookup"><span data-stu-id="d1339-141">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="d1339-142">Bestimmen Sie im Element `StartButton_Click`, ob ein Vorgang bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d1339-142">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="d1339-143">If the value of `cts` is `Nothing`, no operation is already active.</span><span class="sxs-lookup"><span data-stu-id="d1339-143">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="d1339-144">If the value isn't `Nothing`, the operation that is already running is canceled.</span><span class="sxs-lookup"><span data-stu-id="d1339-144">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. <span data-ttu-id="d1339-145">Legen Sie `cts` auf einen anderen Wert fest, der den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-145">Set `cts` to a different value that represents the current process.</span></span>

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. <span data-ttu-id="d1339-146">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d1339-146">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

<span data-ttu-id="d1339-147">Im folgende Code werden alle Änderungen in `StartButton_Click` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-147">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="d1339-148">Die Ergänzungen werden mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d1339-148">The additions are marked with asterisks.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

<span data-ttu-id="d1339-149">Nehmen Sie dazu in `AccessTheWebAsync`die folgenden Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="d1339-149">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="d1339-150">Fügen Sie einen Parameter hinzu, um das Abbruchtoken von `StartButton_Click` zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d1339-150">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="d1339-151">Verwenden Sie die <xref:System.Net.Http.HttpClient.GetAsync%2A>-Methode zum Herunterladen der Websites, da `GetAsync` ein <xref:System.Threading.CancellationToken> Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d1339-151">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="d1339-152">Bevor Sie `DisplayResults` aufrufen, um die Ergebnisse für jede heruntergeladene Website anzuzeigen, aktivieren Sie `ct`, um sicherzustellen, dass der aktuelle Vorgang nicht abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="d1339-152">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

 <span data-ttu-id="d1339-153">Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-153">The following code shows these changes, which are marked with asterisks.</span></span>

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="d1339-154">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:</span><span class="sxs-lookup"><span data-stu-id="d1339-154">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="d1339-155">Zum Ausschließen der Teillisten entfernen Sie die Kommentarmarkierungen der ersten Codezeile in `StartButton_Click`, um das Textfeld bei jedem erneuten Start des Vorgangs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d1339-155">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="d1339-156">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="d1339-156">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="d1339-157">Das dritte Beispiel ist das schwierigste, da von der App jedes Mal, wenn der Benutzer die Schaltfläche **Start** anklickt, ein anderer asynchroner Vorgang gestartet wird und alle Vorgänge vollständig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-157">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="d1339-158">Alle angeforderten Vorgänge laden Websites asynchron aus der Liste herunter, doch die Ausgabe der Vorgänge wird sequenziell dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d1339-158">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="d1339-159">Das bedeutet, die tatsächliche Downloadaktivität überlappt, wie es die Ausgabe in [Erkennen von Ablaufinvarianz](#BKMK_RecognizingReentrancy) zeigt, die Ergebnislisten für jede Gruppe aber getrennt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-159">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="d1339-160">Die Vorgänge geben global <xref:System.Threading.Tasks.Task>, `pendingWork` frei, der als Gatekeeper für den Anzeigenprozess dient.</span><span class="sxs-lookup"><span data-stu-id="d1339-160">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="d1339-161">Sie können dieses Beispiel ausführen, indem Sie die Änderungen in den Code in [Erstellen der App](#BKMK_BuildingTheApp) einfügen, oder Sie können den Anweisungen in [Herunterladen der App](#BKMK_DownloadingTheApp) folgen, um das Beispiel herunterzuladen und dann das QueueResults-Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d1339-161">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample and then run the QueueResults project.</span></span>

<span data-ttu-id="d1339-162">Die folgende Ausgabe zeigt das Ergebnis bei einmaliger Betätigung der Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="d1339-162">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="d1339-163">Die Buchstabenbezeichnung „A“ gibt an, dass das Ergebnis vom ersten Klick auf die Schaltfläche **Start** stammt.</span><span class="sxs-lookup"><span data-stu-id="d1339-163">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="d1339-164">Die Zahlen geben die Reihenfolge der URL in der Liste der Downloadziele wieder.</span><span class="sxs-lookup"><span data-stu-id="d1339-164">The numbers show the order of the URLs in the list of download targets.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

<span data-ttu-id="d1339-165">Wenn der Benutzer die Schaltfläche **Start** dreimal anklickt, erzeugt die App eine Ausgabe, die den folgenden Zeilen ähnelt.</span><span class="sxs-lookup"><span data-stu-id="d1339-165">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="d1339-166">Die Informationszeilen, die mit einem Nummernzeichen (#) beginnen, verfolgen den Status der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d1339-166">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

<span data-ttu-id="d1339-167">Die Gruppen B und C starten, bevor Gruppe A beendet ist, doch die Ausgabe für jede Gruppe wird getrennt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-167">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="d1339-168">Die gesamte Ausgabe für Gruppe A wird zuerst angezeigt, gefolgt von der gesamten Ausgabe für Gruppe B und dann die gesamte Ausgabe für Gruppe C. Die App zeigt die Gruppen immer in Reihenfolge an, und die Informationen zu den einzelnen Websites werden immer in der Reihenfolge angezeigt, in der die URLs in der URL-Liste aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-168">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="d1339-169">Sie können die Reihenfolge, in der die Downloads tatsächlich vorkommen, allerdings nicht vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="d1339-169">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="d1339-170">Nachdem mehrere Gruppen gestartet wurden, sind alle von ihnen generierten Downloadtasks aktiv.</span><span class="sxs-lookup"><span data-stu-id="d1339-170">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="d1339-171">Sie können nicht davon ausgehen, dass A-1 vor B-1 heruntergeladen wird, und Sie können auch nicht davon ausgehen, dass A-1 vor A-2 heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="d1339-171">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="d1339-172">Globale Definitionen</span><span class="sxs-lookup"><span data-stu-id="d1339-172">Global Definitions</span></span>

<span data-ttu-id="d1339-173">Im Beispielcode sind die folgenden zwei globalen Deklarationen enthalten, die von allen Methoden sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d1339-173">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

<span data-ttu-id="d1339-174">Mit der `Task`-Variable `pendingWork` wird der Anzeigenprozess beaufsichtigt, und es wird verhindert, dass der Anzeigevorgang einer Gruppe zur Unterbrechung des Anzeigevorgangs einer anderen Gruppe führt.</span><span class="sxs-lookup"><span data-stu-id="d1339-174">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="d1339-175">Die Zeichenvariable `group` bezeichnet die Ausgabe von unterschiedlichen Gruppen, um sicherzustellen, dass Ergebnisse in der erwarteten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1339-175">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="d1339-176">Der Click-Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="d1339-176">The Click Event Handler</span></span>

<span data-ttu-id="d1339-177">Mit dem Ereignishandler `StartButton_Click` wird der Gruppenbuchstabe bei jedem Auswählen der Schaltfläche **Start** erhöht.</span><span class="sxs-lookup"><span data-stu-id="d1339-177">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="d1339-178">Anschließend ruft der Handler zum Ausführen des Downloadingvorgangs das Element `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="d1339-178">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="d1339-179">Die AccessTheWebAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="d1339-179">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="d1339-180">In diesem Beispiel wird `AccessTheWebAsync` in zwei Methoden aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="d1339-180">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="d1339-181">Mit der erste Methode, `AccessTheWebAsync`, werden alle Downloadtasks für eine Gruppe gestartet und `pendingWork` wird zum Steuern des Anzeigenprozesses festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d1339-181">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="d1339-182">Die Methode verwendet zum gleichzeitigen Starten aller Downloadtasks eine LINQ-Abfrage (Language-Integrated Query) sowie <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1339-182">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="d1339-183">`AccessTheWebAsync` ruft dann `FinishOneGroupAsync` auf, um den Abschluss jedes einzelnen Downloads zu erwarten und die Länge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1339-183">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="d1339-184">`FinishOneGroupAsync` gibt einen Task zurück, der in `pendingWork` dem Element `AccessTheWebAsync` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d1339-184">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="d1339-185">Dieser Wert verhindert die Unterbrechung durch einen anderen Vorgang, bevor die Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d1339-185">That value prevents interruption by another operation before the task is complete.</span></span>

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="d1339-186">Die FinishOneGroupAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="d1339-186">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="d1339-187">Diese Methode durchläuft die Downloadaufgaben in einer Gruppe, erwartet dabei jeden einzelnen Task, zeigt die Länge der heruntergeladenen Website an und addiert diese Länge zur Summe.</span><span class="sxs-lookup"><span data-stu-id="d1339-187">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="d1339-188">Die erste Anweisung in `FinishOneGroupAsync` verwendet `pendingWork`, um sicherzustellen, dass die Eingabe der Methode keinen Vorgang behindert, der sich bereits im Anzeige- oder im Warteprozess befindet.</span><span class="sxs-lookup"><span data-stu-id="d1339-188">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="d1339-189">Wenn ein solcher Vorgang ausgeführt wird, wird der eintretende Vorgang solange aufgeschoben, bis er an der Reihe ist.</span><span class="sxs-lookup"><span data-stu-id="d1339-189">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="d1339-190">Sie können dieses Beispiel ausführen, indem Sie die Änderungen in den Code in [Erstellen der App](#BKMK_BuildingTheApp) einfügen, oder Sie können den Anweisungen in [Herunterladen der App](#BKMK_DownloadingTheApp) folgen, um das Beispiel herunterzuladen und dann das QueueResults-Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d1339-190">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample, and then run the QueueResults project.</span></span>

#### <a name="points-of-interest"></a><span data-ttu-id="d1339-191">Relevante Punkte</span><span class="sxs-lookup"><span data-stu-id="d1339-191">Points of Interest</span></span>

<span data-ttu-id="d1339-192">Die Informationszeilen, die mit einem Nummernzeichen (#) in der Ausgabe beginnen, erläutern die Funktionsweise dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="d1339-192">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="d1339-193">Die Ausgabe zeigt die folgenden Muster an.</span><span class="sxs-lookup"><span data-stu-id="d1339-193">The output shows the following patterns.</span></span>

- <span data-ttu-id="d1339-194">Eine Gruppe kann gestartet werden, während die Ausgabe einer vorherigen Gruppe angezeigt wird. Doch die Anzeige der Ausgabe der vorherigen Gruppe wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d1339-194">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- <span data-ttu-id="d1339-195">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span><span class="sxs-lookup"><span data-stu-id="d1339-195">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="d1339-196">Gruppe A hat bei Erreichen von `FinishOneGroupAsync` einen Erwartungsausdruck noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d1339-196">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="d1339-197">Daher wurde die Steuerung nicht an `AccessTheWebAsync` zurückgegeben, und die erste Zuweisung zu `pendingWork` ist nicht aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d1339-197">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="d1339-198">Die folgenden zwei Zeilen werden immer zusammen in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-198">The following two lines always appear together in the output.</span></span> <span data-ttu-id="d1339-199">Der Code wird zwischen dem Starten des Vorgangs einer Gruppe in `StartButton_Click` und dem Zuweisen eines Tasks für die Gruppe zu `pendingWork` nie unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d1339-199">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  <span data-ttu-id="d1339-200">Nachdem eine Gruppe in `StartButton_Click` eintritt, schließt der Vorgang einen Erwartungsausdruck erst ab, wenn der Vorgang in `FinishOneGroupAsync` eintritt.</span><span class="sxs-lookup"><span data-stu-id="d1339-200">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="d1339-201">Daher kann kein weiterer Vorgang während dieses Codeabschnitts die Steuerung übernehmen.</span><span class="sxs-lookup"><span data-stu-id="d1339-201">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="d1339-202">Die Beispiel-App überprüfen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d1339-202">Reviewing and Running the Example App</span></span>

<span data-ttu-id="d1339-203">Zum besseren Verständnis der Beispiel-App können Sie sie herunterladen, sie selbst erstellen oder den Code am Ende dieses Themas überprüfen, ohne die App zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d1339-203">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="d1339-204">Um die App des Beispiels als WPF-Desktop-App (Windows Presentation Foundation) auszuführen, muss Visual Studio 2012 oder höher oder .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="d1339-204">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="d1339-205">Herunterladen der App</span><span class="sxs-lookup"><span data-stu-id="d1339-205">Downloading the App</span></span>

1. <span data-ttu-id="d1339-206">Sie können die komprimierte Datei unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d1339-206">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="d1339-207">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1339-207">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="d1339-208">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="d1339-208">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="d1339-209">Navigieren Sie zu dem Ordner mit dem dekomprimierten Beispielcode, und öffnen Sie die Projektmappendatei (SLN-Datei).</span><span class="sxs-lookup"><span data-stu-id="d1339-209">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="d1339-210">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, das Sie ausführen möchten, und wählen Sie dann **Set as StartUpProject** (Als StartUpProject festlegen) aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-210">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="d1339-211">Drücken Sie zum Erstellen und Ausführen des Projekts die Tastenkombination "STRG+F5".</span><span class="sxs-lookup"><span data-stu-id="d1339-211">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="d1339-212">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="d1339-212">Building the App</span></span>

<span data-ttu-id="d1339-213">Der folgende Abschnitt enthält den Code, um das Beispiel als WPF-App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1339-213">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="d1339-214">So erstellen Sie eine WPF-App</span><span class="sxs-lookup"><span data-stu-id="d1339-214">To build a WPF app</span></span>

1. <span data-ttu-id="d1339-215">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1339-215">Start Visual Studio.</span></span>

2. <span data-ttu-id="d1339-216">Wählen Sie in der Menüleiste **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-216">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="d1339-217">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-217">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="d1339-218">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1339-218">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="d1339-219">Wählen Sie in der Liste der Projekttypen **WPF-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-219">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="d1339-220">Benennen Sie das Projekt `WebsiteDownloadWPF`, wählen Sie die .NET Framework-Version 4.6 oder höher aus, und klicken Sie dann auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1339-220">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="d1339-221">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-221">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="d1339-222">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-222">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="d1339-223">Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-223">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="d1339-224">Ersetzen Sie den automatisch generierten Code in der **XAML**-Ansicht der Datei „MainWindow.xaml“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="d1339-224">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     <span data-ttu-id="d1339-225">Ein einfaches Fenster, das ein Textfeld und eine Schaltfläche enthält, wird in der **Entwurfsansicht** der Datei „MainWindow.xaml“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1339-225">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="d1339-226">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise**, und klicken Sie anschließend auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d1339-226">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="d1339-227">Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu, sofern dieser nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d1339-227">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="d1339-228">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span><span class="sxs-lookup"><span data-stu-id="d1339-228">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

10. <span data-ttu-id="d1339-229">In MainWindow.xaml.vb , replace the code with the following code.</span><span class="sxs-lookup"><span data-stu-id="d1339-229">In MainWindow.xaml.vb , replace the code with the following code.</span></span>

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. <span data-ttu-id="d1339-230">Wählen Sie zum Ausführen des Programms die Tastenkombination „STRG+F5“ aus, und wählen Sie dann mehrmals die Schaltfläche **Start** aus.</span><span class="sxs-lookup"><span data-stu-id="d1339-230">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="d1339-231">Nehmen Sie die Änderungen aus [Die Schaltfläche „Start“ deaktivieren](#BKMK_DisableTheStartButton), [Den Vorgang abbrechen und neu starten](#BKMK_CancelAndRestart) oder [Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen](#BKMK_RunMultipleOperations) vor, um mit Ablaufinvarianz umzugehen.</span><span class="sxs-lookup"><span data-stu-id="d1339-231">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1339-232">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1339-232">See also</span></span>

- <span data-ttu-id="d1339-233">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="d1339-233">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
- [<span data-ttu-id="d1339-234">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1339-234">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
