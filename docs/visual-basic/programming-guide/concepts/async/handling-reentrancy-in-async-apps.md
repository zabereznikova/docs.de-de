---
title: Des erneuten Eintretens in asynchronen Anwendungen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 8c35f0b393f38ea32f456a60ebd520065d16c6eb
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="d3b58-102">Des erneuten Eintretens in asynchronen Anwendungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3b58-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>
<span data-ttu-id="d3b58-103">Wenn Sie asynchronen Code in der App einschließen, sollten Sie erneutes Eintreten, also den erneuten Beginn eines asynchronen Vorgangs vor seinem Abschließen, berücksichtigen und möglicherweise verhindern.</span><span class="sxs-lookup"><span data-stu-id="d3b58-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="d3b58-104">Wenn Sie Möglichkeiten für erneutes Eintreten nicht identifizieren und behandeln, kann dies zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>  
  
 <span data-ttu-id="d3b58-105">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="d3b58-105">**In this topic**</span></span>  
  
-   [<span data-ttu-id="d3b58-106">Erkennen von Reentranz</span><span class="sxs-lookup"><span data-stu-id="d3b58-106">Recognizing Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="d3b58-107">Arbeiten mit Reentranz</span><span class="sxs-lookup"><span data-stu-id="d3b58-107">Handling Reentrancy</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="d3b58-108">Deaktivieren Sie die Schaltfläche "Start"</span><span class="sxs-lookup"><span data-stu-id="d3b58-108">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="d3b58-109">Abbrechen und Neustarten des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="d3b58-109">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [<span data-ttu-id="d3b58-110">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="d3b58-110">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [<span data-ttu-id="d3b58-111">Überprüfen und Ausführen der Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="d3b58-111">Reviewing and Running the Example App</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
> [!NOTE]
>  <span data-ttu-id="d3b58-112">Zum Ausführen des Beispiels müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d3b58-112">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="d3b58-113"><a name="BKMK_RecognizingReentrancy"></a>Erkennen von Reentranz</span><span class="sxs-lookup"><span data-stu-id="d3b58-113"><a name="BKMK_RecognizingReentrancy"></a> Recognizing Reentrancy</span></span>  
 <span data-ttu-id="d3b58-114">Wählen Sie im Beispiel in diesem Thema Benutzer eine **Start** Schaltfläche zum Initiieren einer asynchronen app, die eine Reihe von Websites heruntergeladen und berechnet die Gesamtzahl der Bytes, die heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d3b58-114">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="d3b58-115">Eine synchrone Version des Beispiels würde auf die gleiche Weise reagieren, unabhängig davon, wie oft ein Benutzer die Schaltfläche auswählt, da diese Ereignisse nach dem ersten Mal vom UI-Thread ignoriert werden, bis die Anwendung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d3b58-115">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="d3b58-116">In einer asynchronen App reagiert der UI-Thread weiterhin, und Sie können möglicherweise erneut in den asynchronen Vorgang eintreten, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d3b58-116">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>  
  
 <span data-ttu-id="d3b58-117">Das folgende Beispiel zeigt die erwartete Ausgabe, wenn der Benutzer die **starten** Schaltfläche nur einmal.</span><span class="sxs-lookup"><span data-stu-id="d3b58-117">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="d3b58-118">Eine Liste der heruntergeladenen Websites wird mit der Größe, in Bytes für jede Site, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-118">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="d3b58-119">Die Gesamtanzahl von Bytes wird am Ende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-119">The total number of bytes appears at the end.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3b58-120">Wenn der Benutzer die Schaltfläche allerdings mehrmals auswählt, wird der Ereignishandler wiederholt aufgerufen, und der Downloadvorgang beginnt jedes Mal erneut.</span><span class="sxs-lookup"><span data-stu-id="d3b58-120">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="d3b58-121">Daher werden mehrere asynchrone Vorgänge gleichzeitig ausgeführt, die Ausgabe überlappt mit den Ergebnissen, und die Gesamtzahl der Bytes ist verwirrend.</span><span class="sxs-lookup"><span data-stu-id="d3b58-121">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/en-us/library/jj155761.aspx                29019  
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
  
 <span data-ttu-id="d3b58-122">Sie können den Code, der diese Ausgabe erzeugt, überprüfen, indem Sie einen Bildlauf zum Ende dieses Themas durchführen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-122">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="d3b58-123">Sie können mit dem Code experimentieren, indem Sie die Lösung auf dem lokalen Computer herunterladen und das WebsiteDownload-Projekt oder mit dem Code am Ende dieses Themas, um Ihr eigenes Projekt Weitere Informationen und Anweisungen zu erstellen, finden Sie unter [überprüfen und Ausführen der Beispiel-App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span><span class="sxs-lookup"><span data-stu-id="d3b58-123">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span>  
  
##  <span data-ttu-id="d3b58-124"><a name="BKMK_HandlingReentrancy"></a>Arbeiten mit Reentranz</span><span class="sxs-lookup"><span data-stu-id="d3b58-124"><a name="BKMK_HandlingReentrancy"></a> Handling Reentrancy</span></span>  
 <span data-ttu-id="d3b58-125">Sie können das erneute Eintreten auf verschiedene Weise behandeln, je nachdem, was von der App ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3b58-125">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="d3b58-126">In diesem Thema werden die folgenden Beispiele zur Veranschaulichung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d3b58-126">This topic presents the following examples:</span></span>  
  
-   [<span data-ttu-id="d3b58-127">Deaktivieren Sie die Schaltfläche "Start"</span><span class="sxs-lookup"><span data-stu-id="d3b58-127">Disable the Start Button</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="d3b58-128">Deaktivieren der **Start** Schaltfläche während der Vorgang ausgeführt wird, sodass der Benutzer ihn nicht unterbrechen kann.</span><span class="sxs-lookup"><span data-stu-id="d3b58-128">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>  
  
-   [<span data-ttu-id="d3b58-129">Abbrechen und Neustarten des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="d3b58-129">Cancel and Restart the Operation</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="d3b58-130">Abbrechen aller Vorgänge, die noch ausgeführt wird, wenn der Benutzer die **Start** erneut auf die Schaltfläche und anschließend fortfahren, sodass nur der zuletzt angeforderte Vorgang.</span><span class="sxs-lookup"><span data-stu-id="d3b58-130">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>  
  
-   [<span data-ttu-id="d3b58-131">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="d3b58-131">Run Multiple Operations and Queue the Output</span></span>](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     <span data-ttu-id="d3b58-132">Alle angeforderten Vorgänge asynchron ausführen lassen, die Anzeige der Ausgabe allerdings koordinieren, damit die Ergebnisse der einzelnen Vorgänge zusammen und in Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3b58-132">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>  
  
###  <span data-ttu-id="d3b58-133"><a name="BKMK_DisableTheStartButton"></a>Deaktivieren Sie die Schaltfläche "Start"</span><span class="sxs-lookup"><span data-stu-id="d3b58-133"><a name="BKMK_DisableTheStartButton"></a> Disable the Start Button</span></span>  
 <span data-ttu-id="d3b58-134">Sie blockieren, können die **starten** Schaltfläche während ein Vorgangs ausgeführt wird, deaktivieren Sie die Schaltfläche am oberen Rand der `StartButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="d3b58-134">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="d3b58-135">Sie können die Schaltfläche aus einem `Finally`-Block erneut aktivieren, sobald der Vorgang beendet ist, damit Benutzer die App erneut ausführen können.</span><span class="sxs-lookup"><span data-stu-id="d3b58-135">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>  
  
 <span data-ttu-id="d3b58-136">Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-136">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="d3b58-137">Sie können die Änderungen am Code am Ende dieses Themas hinzufügen, oder Sie können die fertige app von herunterladen [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span><span class="sxs-lookup"><span data-stu-id="d3b58-137">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="d3b58-138">Der Projektname ist "DisableStartButton".</span><span class="sxs-lookup"><span data-stu-id="d3b58-138">The project name is DisableStartButton.</span></span>  
  
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
  
 <span data-ttu-id="d3b58-139">Aufgrund der Änderungen reagiert die Schaltfläche nicht, während die Websites von `AccessTheWebAsync` heruntergeladen werden, sodass ein erneutes Eintreten in den Prozess nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d3b58-139">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>  
  
###  <span data-ttu-id="d3b58-140"><a name="BKMK_CancelAndRestart"></a>Abbrechen und Neustarten des Vorgangs</span><span class="sxs-lookup"><span data-stu-id="d3b58-140"><a name="BKMK_CancelAndRestart"></a> Cancel and Restart the Operation</span></span>  
 <span data-ttu-id="d3b58-141">Anstatt Deaktivieren der **starten** Schaltfläche, Sie können die Schaltfläche aktiv bleiben, wenn der Benutzer die Schaltfläche erneut auswählt, brechen Sie den Vorgang, der bereits ausgeführt und lassen den zuletzt begonnenen Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-141">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>  
  
 <span data-ttu-id="d3b58-142">Weitere Informationen über das Abbrechen finden Sie unter [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="d3b58-142">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="d3b58-143">Um dieses Szenario einzurichten, nehmen Sie folgende Änderungen am grundlegenden Code, das im bereitgestellten [überprüfen und Ausführen der Beispiel-App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span><span class="sxs-lookup"><span data-stu-id="d3b58-143">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).</span></span> <span data-ttu-id="d3b58-144">Die fertige app von können auch herunterladen [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span><span class="sxs-lookup"><span data-stu-id="d3b58-144">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span> <span data-ttu-id="d3b58-145">Der Name dieses Projekts lautet "CancelAndRestart".</span><span class="sxs-lookup"><span data-stu-id="d3b58-145">The name of this project is CancelAndRestart.</span></span>  
  
1.  <span data-ttu-id="d3b58-146">Deklarieren Sie eine <xref:System.Threading.CancellationTokenSource>-Variable `cts`, die im Bereich für alle Methoden liegt.</xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="d3b58-146">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>  
  
    ```vb  
    Class MainWindow // Or Class MainPage  
  
        ' *** Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="d3b58-147">Bestimmen Sie im Element `StartButton_Click`, ob ein Vorgang bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3b58-147">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="d3b58-148">Wenn der Wert der `cts` ist `Nothing`, kein Vorgang ist bereits aktiv.</span><span class="sxs-lookup"><span data-stu-id="d3b58-148">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="d3b58-149">Wenn der Wert nicht `Nothing`, der Vorgang, der bereits ausgeführt wird, abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="d3b58-149">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>  
  
    ```vb  
    ' *** If a download process is already underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
    ```  
  
3.  <span data-ttu-id="d3b58-150">Legen Sie `cts` auf einen anderen Wert fest, der den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-150">Set `cts` to a different value that represents the current process.</span></span>  
  
    ```vb  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
    ```  
  
4.  <span data-ttu-id="d3b58-151">Am Ende des `StartButton_Click`, der aktuelle Vorgang abgeschlossen ist, so legen Sie den Wert der `cts` an `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d3b58-151">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>  
  
    ```vb  
    ' *** When the process completes, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
    ```  
  
 <span data-ttu-id="d3b58-152">Im folgende Code werden alle Änderungen in `StartButton_Click` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-152">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="d3b58-153">Die Ergänzungen werden mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d3b58-153">The additions are marked with asterisks.</span></span>  
  
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
  
 <span data-ttu-id="d3b58-154">Nehmen Sie dazu in `AccessTheWebAsync`die folgenden Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="d3b58-154">In `AccessTheWebAsync`, make the following changes.</span></span>  
  
-   <span data-ttu-id="d3b58-155">Fügen Sie einen Parameter hinzu, um das Abbruchtoken von `StartButton_Click` zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d3b58-155">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>  
  
-   <span data-ttu-id="d3b58-156">Verwenden der <xref:System.Net.Http.HttpClient.GetAsync%2A>-Methode zum Herunterladen der Websites, da `GetAsync` akzeptiert ein <xref:System.Threading.CancellationToken>Argument.</xref:System.Threading.CancellationToken> </xref:System.Net.Http.HttpClient.GetAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d3b58-156">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>  
  
-   <span data-ttu-id="d3b58-157">Bevor Sie `DisplayResults` aufrufen, um die Ergebnisse für jede heruntergeladene Website anzuzeigen, aktivieren Sie `ct`, um sicherzustellen, dass der aktuelle Vorgang nicht abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="d3b58-157">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>  
  
 <span data-ttu-id="d3b58-158">Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-158">The following code shows these changes, which are marked with asterisks.</span></span>  
  
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
  
 <span data-ttu-id="d3b58-159">Bei Auswahl der **Start** mehrmals die Schaltfläche während diese app ausgeführt wird, es sollten Ergebnisse erzeugen, die der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="d3b58-159">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3b58-160">Zum Ausschließen der Teillisten entfernen Sie die Kommentarmarkierungen der ersten Codezeile in `StartButton_Click`, um das Textfeld bei jedem erneuten Start des Vorgangs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-160">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>  
  
###  <span data-ttu-id="d3b58-161"><a name="BKMK_RunMultipleOperations"></a>Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="d3b58-161"><a name="BKMK_RunMultipleOperations"></a> Run Multiple Operations and Queue the Output</span></span>  
 <span data-ttu-id="d3b58-162">Das dritte Beispiel ist das schwierigste, dass die app ein anderer asynchronen Vorgang jedes Mal gestartet wird, die der Benutzer wählt die **Start** Schaltfläche, und alle Vorgänge, die bis zum Abschluss ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-162">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="d3b58-163">Alle angeforderten Vorgänge laden Websites asynchron aus der Liste herunter, doch die Ausgabe der Vorgänge wird sequenziell dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-163">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="d3b58-164">D. h. die tatsächliche downloadaktivität, wie die Ausgabe in [Erkennen von Reentranz](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) zeigt jedoch die Liste der Ergebnisse für jede Gruppe getrennt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-164">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) shows, but the list of results for each group is presented separately.</span></span>  
  
 <span data-ttu-id="d3b58-165">Die Vorgänge geben global <xref:System.Threading.Tasks.Task>, `pendingWork`, der als Gatekeeper für den anzeigenprozess dient.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="d3b58-165">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>  
  
 <span data-ttu-id="d3b58-166">Sie können dieses Beispiel ausführen, durch Einfügen die Änderungen in den Code in [Erstellen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder befolgen Sie die Anweisungen in [Herunterladen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) , laden Sie das Beispiel, und führen Sie dann das QueueResults-Projekt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-166">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample and then run the QueueResults project.</span></span>  
  
 <span data-ttu-id="d3b58-167">Die folgende Ausgabe zeigt dem Ergebnis, wenn der Benutzer die **Start** Schaltfläche nur einmal.</span><span class="sxs-lookup"><span data-stu-id="d3b58-167">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="d3b58-168">Die buchstabenbezeichnung A gibt an, dass das Ergebnis von der ersten der **Start** Schaltfläche ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="d3b58-168">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="d3b58-169">Die Zahlen geben die Reihenfolge der URL in der Liste der Downloadziele wieder.</span><span class="sxs-lookup"><span data-stu-id="d3b58-169">The numbers show the order of the URLs in the list of download targets.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3b58-170">Wenn der Benutzer die **Start** Schaltfläche dreimal, erzeugt die app eine Ausgabe, die die folgenden Zeilen ähnelt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-170">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="d3b58-171">Die Informationszeilen, die mit einem Nummernzeichen (#) beginnen, verfolgen den Status der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d3b58-171">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>  
  
```  
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
  
 <span data-ttu-id="d3b58-172">Die Gruppen B und C starten, bevor Gruppe A beendet ist, doch die Ausgabe für jede Gruppe wird getrennt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-172">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="d3b58-173">Die gesamte Ausgabe für Gruppe A wird zuerst angezeigt, gefolgt von der gesamten Ausgabe für Gruppe B und dann die gesamte Ausgabe für Gruppe C. Die app immer zeigt die Gruppen in der Reihenfolge und, für jede Gruppe, die Informationen zu den einzelnen Websites in der angegebenen Reihenfolge an, die URLs in der Liste der URLs immer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-173">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>  
  
 <span data-ttu-id="d3b58-174">Sie können die Reihenfolge, in der die Downloads tatsächlich vorkommen, allerdings nicht vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-174">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="d3b58-175">Nachdem mehrere Gruppen gestartet wurden, sind alle von ihnen generierten Downloadtasks aktiv.</span><span class="sxs-lookup"><span data-stu-id="d3b58-175">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="d3b58-176">Sie können nicht davon ausgehen, dass A-1 vor B-1 heruntergeladen wird, und Sie können auch nicht davon ausgehen, dass A-1 vor A-2 heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="d3b58-176">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>  
  
#### <a name="global-definitions"></a><span data-ttu-id="d3b58-177">Globale Definitionen</span><span class="sxs-lookup"><span data-stu-id="d3b58-177">Global Definitions</span></span>  
 <span data-ttu-id="d3b58-178">Im Beispielcode sind die folgenden zwei globalen Deklarationen enthalten, die von allen Methoden sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d3b58-178">The sample code contains the following two global declarations that are visible from all methods.</span></span>  
  
```vb  
Class MainWindow    ' Class MainPage in Windows Store app.  
  
    ' ***Declare the following variables where all methods can access them.   
    Private pendingWork As Task = Nothing  
    Private group As Char = ChrW(AscW("A") - 1)  
```  
  
 <span data-ttu-id="d3b58-179">Mit der `Task`-Variable `pendingWork` wird der Anzeigenprozess beaufsichtigt, und es wird verhindert, dass der Anzeigevorgang einer Gruppe zur Unterbrechung des Anzeigevorgangs einer anderen Gruppe führt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-179">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="d3b58-180">Die Zeichenvariable `group` bezeichnet die Ausgabe von unterschiedlichen Gruppen, um sicherzustellen, dass Ergebnisse in der erwarteten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3b58-180">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>  
  
#### <a name="the-click-event-handler"></a><span data-ttu-id="d3b58-181">Der Click-Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="d3b58-181">The Click Event Handler</span></span>  
 <span data-ttu-id="d3b58-182">Der Ereignishandler `StartButton_Click`, erhöht den Buchstaben der Gruppe Jede Betätigung der **Start** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d3b58-182">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="d3b58-183">Anschließend ruft der Handler zum Ausführen des Downloadingvorgangs das Element `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="d3b58-183">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>  
  
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
  
#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="d3b58-184">Die AccessTheWebAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="d3b58-184">The AccessTheWebAsync Method</span></span>  
 <span data-ttu-id="d3b58-185">In diesem Beispiel wird `AccessTheWebAsync` in zwei Methoden aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-185">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="d3b58-186">Mit der erste Methode, `AccessTheWebAsync`, werden alle Downloadtasks für eine Gruppe gestartet und `pendingWork` wird zum Steuern des Anzeigenprozesses festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-186">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="d3b58-187">Die Methode verwendet eine Language Integrated Query (LINQ-Abfrage) und <xref:System.Linq.Enumerable.ToArray%2A>aller Downloadtasks zur selben Zeit gestartet.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="d3b58-187">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>  
  
 <span data-ttu-id="d3b58-188">`AccessTheWebAsync` ruft dann `FinishOneGroupAsync` auf, um den Abschluss jedes einzelnen Downloads zu erwarten und die Länge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-188">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>  
  
 <span data-ttu-id="d3b58-189">`FinishOneGroupAsync` gibt einen Task zurück, der in `pendingWork` dem Element `AccessTheWebAsync` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d3b58-189">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="d3b58-190">Dieser Wert verhindert die Unterbrechung durch einen anderen Vorgang, bevor die Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d3b58-190">That value prevents interruption by another operation before the task is complete.</span></span>  
  
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
  
#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="d3b58-191">Die FinishOneGroupAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="d3b58-191">The FinishOneGroupAsync Method</span></span>  
 <span data-ttu-id="d3b58-192">Diese Methode durchläuft die Downloadaufgaben in einer Gruppe, erwartet dabei jeden einzelnen Task, zeigt die Länge der heruntergeladenen Website an und addiert diese Länge zur Summe.</span><span class="sxs-lookup"><span data-stu-id="d3b58-192">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>  
  
 <span data-ttu-id="d3b58-193">Die erste Anweisung im `FinishOneGroupAsync` verwendet `pendingWork` sicherstellen, dass die Eingabe der Methode keine stört mit einem Vorgang, der sich bereits im Anzeige- oder im ist.</span><span class="sxs-lookup"><span data-stu-id="d3b58-193">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="d3b58-194">Wenn ein solcher Vorgang ausgeführt wird, wird der eintretende Vorgang solange aufgeschoben, bis er an der Reihe ist.</span><span class="sxs-lookup"><span data-stu-id="d3b58-194">If such an operation is in progress, the entering operation must wait its turn.</span></span>  
  
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
  
 <span data-ttu-id="d3b58-195">Sie können dieses Beispiel ausführen, durch Einfügen die Änderungen in den Code in [Erstellen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder befolgen Sie die Anweisungen in [Herunterladen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) , laden Sie das Beispiel, und führen Sie dann das QueueResults-Projekt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-195">You can run this example by pasting the changes into the code in [Building the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or you can follow the instructions in [Downloading the App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to download the sample, and then run the QueueResults project.</span></span>  
  
#### <a name="points-of-interest"></a><span data-ttu-id="d3b58-196">Relevante Punkte</span><span class="sxs-lookup"><span data-stu-id="d3b58-196">Points of Interest</span></span>  
 <span data-ttu-id="d3b58-197">Die Informationszeilen, die mit einem Nummernzeichen (#) in der Ausgabe beginnen, erläutern die Funktionsweise dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="d3b58-197">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>  
  
 <span data-ttu-id="d3b58-198">Die Ausgabe zeigt die folgenden Muster an.</span><span class="sxs-lookup"><span data-stu-id="d3b58-198">The output shows the following patterns.</span></span>  
  
-   <span data-ttu-id="d3b58-199">Eine Gruppe kann gestartet werden, während die Ausgabe einer vorherigen Gruppe angezeigt wird. Doch die Anzeige der Ausgabe der vorherigen Gruppe wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-199">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>  
  
    ```  
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
  
-   <span data-ttu-id="d3b58-200">Die `pendingWork` Aufgabe `Nothing` zu Beginn der `FinishOneGroupAsync` nur für Gruppe A, die zuerst gestartet.</span><span class="sxs-lookup"><span data-stu-id="d3b58-200">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="d3b58-201">Gruppe A hat bei Erreichen von `FinishOneGroupAsync` einen Erwartungsausdruck noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-201">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="d3b58-202">Daher wurde die Steuerung nicht an `AccessTheWebAsync` zurückgegeben, und die erste Zuweisung zu `pendingWork` ist nicht aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d3b58-202">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>  
  
-   <span data-ttu-id="d3b58-203">Die folgenden zwei Zeilen werden immer zusammen in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-203">The following two lines always appear together in the output.</span></span> <span data-ttu-id="d3b58-204">Der Code wird zwischen dem Starten des Vorgangs einer Gruppe in `StartButton_Click` und dem Zuweisen eines Tasks für die Gruppe zu `pendingWork` nie unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-204">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>  
  
    ```  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
    ```  
  
     <span data-ttu-id="d3b58-205">Nachdem eine Gruppe in `StartButton_Click` eintritt, schließt der Vorgang einen Erwartungsausdruck erst ab, wenn der Vorgang in `FinishOneGroupAsync` eintritt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-205">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="d3b58-206">Daher kann kein weiterer Vorgang während dieses Codeabschnitts die Steuerung übernehmen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-206">Therefore, no other operation can gain control during that segment of code.</span></span>  
  
##  <span data-ttu-id="d3b58-207"><a name="BKMD_SettingUpTheExample"></a>Überprüfen und Ausführen der Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="d3b58-207"><a name="BKMD_SettingUpTheExample"></a> Reviewing and Running the Example App</span></span>  
 <span data-ttu-id="d3b58-208">Zum besseren Verständnis der Beispiel-App können Sie sie herunterladen, sie selbst erstellen oder den Code am Ende dieses Themas überprüfen, ohne die App zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d3b58-208">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3b58-209">Zum Ausführen des Beispiels als eine Windows Presentation Foundation (WPF)-desktop-app müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d3b58-209">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
###  <span data-ttu-id="d3b58-210"><a name="BKMK_DownloadingTheApp"></a>Herunterladen der App</span><span class="sxs-lookup"><span data-stu-id="d3b58-210"><a name="BKMK_DownloadingTheApp"></a> Downloading the App</span></span>  
  
1.  <span data-ttu-id="d3b58-211">Laden Sie die komprimierte Datei von [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span><span class="sxs-lookup"><span data-stu-id="d3b58-211">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](http://go.microsoft.com/fwlink/?LinkId=266571).</span></span>  
  
2.  <span data-ttu-id="d3b58-212">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3b58-212">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
3.  <span data-ttu-id="d3b58-213">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-213">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="d3b58-214">Navigieren Sie zu dem Ordner mit dem dekomprimierten Beispielcode, und öffnen Sie die Projektmappendatei (SLN-Datei).</span><span class="sxs-lookup"><span data-stu-id="d3b58-214">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>  
  
5.  <span data-ttu-id="d3b58-215">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für das Projekt, die Sie verwenden möchten, führen Sie aus, und wählen Sie dann **Set as StartUpProject**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-215">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>  
  
6.  <span data-ttu-id="d3b58-216">Drücken Sie zum Erstellen und Ausführen des Projekts die Tastenkombination "STRG+F5".</span><span class="sxs-lookup"><span data-stu-id="d3b58-216">Choose the CTRL+F5 keys to build and run the project.</span></span>  
  
###  <span data-ttu-id="d3b58-217"><a name="BKMK_BuildingTheApp"></a>Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="d3b58-217"><a name="BKMK_BuildingTheApp"></a> Building the App</span></span>  
 <span data-ttu-id="d3b58-218">Der folgende Abschnitt enthält den Code, um das Beispiel als WPF-app zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3b58-218">The following section provides the code to build the example as a WPF app.</span></span>  
  
##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="d3b58-219">So erstellen Sie eine WPF-App</span><span class="sxs-lookup"><span data-stu-id="d3b58-219">To build a WPF app</span></span>  
  
1.  <span data-ttu-id="d3b58-220">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3b58-220">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d3b58-221">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="d3b58-221">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="d3b58-222">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3b58-222">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d3b58-223">In der **installierte Vorlagen** Bereich, erweitern Sie **Visual Basic**, und erweitern Sie dann **Windows**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-223">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>  
  
4.  <span data-ttu-id="d3b58-224">Wählen Sie in der Liste der Projekttypen, **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-224">In the list of project types, choose **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="d3b58-225">Nennen Sie das Projekt `WebsiteDownloadWPF`, und wählen Sie dann die **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d3b58-225">Name the project `WebsiteDownloadWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="d3b58-226">Das neue Projekt wird im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-226">The new project appears in **Solution Explorer**.</span></span>  
  
6.  <span data-ttu-id="d3b58-227">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="d3b58-227">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="d3b58-228">Wenn die Registerkarte nicht angezeigt wird, öffnen Sie das Kontextmenü für "MainWindow.xaml" im **Projektmappen-Explorer**, und wählen Sie dann **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-228">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
7.  <span data-ttu-id="d3b58-229">In der **XAML** Anzeigen von "MainWindow.xaml", ersetzen Sie den Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="d3b58-229">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
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
  
     <span data-ttu-id="d3b58-230">Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird angezeigt, der **Design** Ansicht von "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="d3b58-230">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
8.  <span data-ttu-id="d3b58-231">Fügen Sie einen Verweis für <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="d3b58-231">Add a reference for <xref:System.Net.Http>.</span></span>  
  
9. <span data-ttu-id="d3b58-232">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="d3b58-232">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
10. <span data-ttu-id="d3b58-233">Ersetzen Sie in "MainWindow.Xaml.vb" den Code durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="d3b58-233">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add the following Imports statements, and add a reference for System.Net.Http.  
    Imports System.Net.Http  
    Imports System.Threading  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
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
                "http://msdn.microsoft.com/library/hh191443.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/jj155761.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/hh524395.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
            Return urls  
        End Function  
  
        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)  
            ' Display the length of each website. The string format is designed  
            ' to be used with a monospaced font, such as Lucida Console or  
            ' Global Monospace.  
  
            ' Strip off the "http:'".  
            Dim displayURL = url.Replace("http://", "")  
            ' Display position in the URL list, the URL, and the number of bytes.  
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)  
        End Sub  
    End Class  
    ```  
  
11. <span data-ttu-id="d3b58-234">Drücken Sie STRG + F5, um das Programm auszuführen, und wählen Sie dann die **Start** mehrmals die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d3b58-234">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>  
  
12. <span data-ttu-id="d3b58-235">Ändern von [deaktivieren Sie die Schaltfläche "Start"](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Abbrechen und Neustarten des Vorgangs](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder [mehrere Vorgänge ausführen und die Ausgabe-Warteschlange](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) erneutem verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3b58-235">Make the changes from [Disable the Start Button](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Cancel and Restart the Operation](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), or [Run Multiple Operations and Queue the Output](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) to handle the reentrancy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b58-236">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3b58-236">See Also</span></span>  
 <span data-ttu-id="d3b58-237">[Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="d3b58-237">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="d3b58-238"> [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)</span><span class="sxs-lookup"><span data-stu-id="d3b58-238"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)</span></span>

