---
title: Ablaufinvarianz in asynchronen Anwendungen (C#)
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: 67fbbd294ffe6219b58065f974543b2dd483a92c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451862"
---
# <a name="handling-reentrancy-in-async-apps-c"></a><span data-ttu-id="9a5da-102">Ablaufinvarianz in asynchronen Anwendungen (C#)</span><span class="sxs-lookup"><span data-stu-id="9a5da-102">Handling Reentrancy in Async Apps (C#)</span></span>

<span data-ttu-id="9a5da-103">Wenn Sie asynchronen Code in der App einschließen, sollten Sie erneutes Eintreten, also den erneuten Beginn eines asynchronen Vorgangs vor seinem Abschließen, berücksichtigen und möglicherweise verhindern.</span><span class="sxs-lookup"><span data-stu-id="9a5da-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="9a5da-104">Wenn Sie Möglichkeiten für erneutes Eintreten nicht identifizieren und behandeln, kann dies zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

<span data-ttu-id="9a5da-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="9a5da-105">**In this topic**</span></span>

- [<span data-ttu-id="9a5da-106">Erkennen von Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="9a5da-106">Recognizing Reentrancy</span></span>](#BKMK_RecognizingReentrancy)

- [<span data-ttu-id="9a5da-107">Umgang mit Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="9a5da-107">Handling Reentrancy</span></span>](#BKMK_HandlingReentrancy)

  - [<span data-ttu-id="9a5da-108">Die Schaltfläche „Start“ deaktivieren</span><span class="sxs-lookup"><span data-stu-id="9a5da-108">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  - [<span data-ttu-id="9a5da-109">Den Vorgang abbrechen und neu starten</span><span class="sxs-lookup"><span data-stu-id="9a5da-109">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  - [<span data-ttu-id="9a5da-110">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="9a5da-110">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

- [<span data-ttu-id="9a5da-111">Die Beispiel-App überprüfen und ausführen</span><span class="sxs-lookup"><span data-stu-id="9a5da-111">Reviewing and Running the Example App</span></span>](#BKMD_SettingUpTheExample)

> [!NOTE]
> <span data-ttu-id="9a5da-112">Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="9a5da-112">To run the example, you must have Visual Studio 2012 or newer and .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5da-113">Für die App-Entwicklung ist ab sofort mindestens Transport Layer Security (TLS) Version 1.2 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9a5da-113">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="9a5da-114">Wenn Ihre App für eine .NET Framework-Version vor 4.7 vorgesehen ist, lesen Sie den Artikel [Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="9a5da-114">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="BKMK_RecognizingReentrancy"></a> <span data-ttu-id="9a5da-115">Erkennen von Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="9a5da-115">Recognizing Reentrancy</span></span>

<span data-ttu-id="9a5da-116">Im Beispiel in diesem Thema entscheiden sich Benutzer für eine Schaltfläche **Start**, um eine asynchrone App zu initiieren, mit der eine Reihe von Websites heruntergeladen und die Gesamtanzahl der heruntergeladenen Bytes berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-116">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="9a5da-117">Eine synchrone Version des Beispiels würde auf die gleiche Weise reagieren, unabhängig davon, wie oft ein Benutzer die Schaltfläche auswählt, da diese Ereignisse nach dem ersten Mal vom UI-Thread ignoriert werden, bis die Anwendung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9a5da-117">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="9a5da-118">In einer asynchronen App reagiert der UI-Thread weiterhin, und Sie können möglicherweise erneut in den asynchronen Vorgang eintreten, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9a5da-118">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="9a5da-119">Im folgenden Beispiel wird die erwartete Ausgabe bei einmaliger Betätigung der Schaltfläche **Start** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-119">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="9a5da-120">Eine Liste der heruntergeladenen Websites wird mit der Größe, in Bytes für jede Site, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-120">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="9a5da-121">Die Gesamtanzahl von Bytes wird am Ende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-121">The total number of bytes appears at the end.</span></span>

```output
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

<span data-ttu-id="9a5da-122">Wenn der Benutzer die Schaltfläche allerdings mehrmals auswählt, wird der Ereignishandler wiederholt aufgerufen, und der Downloadvorgang beginnt jedes Mal erneut.</span><span class="sxs-lookup"><span data-stu-id="9a5da-122">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="9a5da-123">Daher werden mehrere asynchrone Vorgänge gleichzeitig ausgeführt, die Ausgabe überlappt mit den Ergebnissen, und die Gesamtzahl der Bytes ist verwirrend.</span><span class="sxs-lookup"><span data-stu-id="9a5da-123">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```output
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

<span data-ttu-id="9a5da-124">Sie können den Code, der diese Ausgabe erzeugt, überprüfen, indem Sie einen Bildlauf zum Ende dieses Themas durchführen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-124">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="9a5da-125">Sie können mit dem Code experimentieren, indem Sie die Lösung auf den lokalen Computer herunterladen und das WebsiteDownload-Projekt ausführen oder den Code am Ende dieses Themas zum Erstellen Ihres eigenen Projekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-125">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project.</span></span> <span data-ttu-id="9a5da-126">Weitere Informationen und Anleitungen finden Sie unter [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="9a5da-126">For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="9a5da-127">Umgang mit Ablaufinvarianz</span><span class="sxs-lookup"><span data-stu-id="9a5da-127">Handling Reentrancy</span></span>

<span data-ttu-id="9a5da-128">Sie können das erneute Eintreten auf verschiedene Weise behandeln, je nachdem, was von der App ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a5da-128">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="9a5da-129">In diesem Thema werden die folgenden Beispiele zur Veranschaulichung verwendet:</span><span class="sxs-lookup"><span data-stu-id="9a5da-129">This topic presents the following examples:</span></span>

- [<span data-ttu-id="9a5da-130">Die Schaltfläche „Start“ deaktivieren</span><span class="sxs-lookup"><span data-stu-id="9a5da-130">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="9a5da-131">Deaktivieren der Schaltfläche **Start**, während der Vorgang ausgeführt wird, sodass der Benutzer ihn nicht unterbrechen kann</span><span class="sxs-lookup"><span data-stu-id="9a5da-131">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="9a5da-132">Den Vorgang abbrechen und neu starten</span><span class="sxs-lookup"><span data-stu-id="9a5da-132">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="9a5da-133">Abbrechen aller Vorgänge, die noch ausgeführt werden, wenn der Benutzer die Schaltfläche **Start** erneut anklickt, sodass nur der zuletzt angeforderte Vorgang fortgesetzt wird</span><span class="sxs-lookup"><span data-stu-id="9a5da-133">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="9a5da-134">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="9a5da-134">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="9a5da-135">Alle angeforderten Vorgänge asynchron ausführen lassen, die Anzeige der Ausgabe allerdings koordinieren, damit die Ergebnisse der einzelnen Vorgänge zusammen und in Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-135">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="BKMK_DisableTheStartButton"></a> <span data-ttu-id="9a5da-136">Die Schaltfläche „Start“ deaktivieren</span><span class="sxs-lookup"><span data-stu-id="9a5da-136">Disable the Start Button</span></span>

<span data-ttu-id="9a5da-137">Sie können die Schaltfläche **Start** während eines ausführenden Vorgangs blockieren, indem Sie die Schaltfläche oben im `StartButton_Click`-Ereignishandler deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9a5da-137">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="9a5da-138">Sie können die Schaltfläche aus einem `finally`-Block erneut aktivieren, sobald der Vorgang beendet ist, damit Benutzer die App erneut ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9a5da-138">You can then reenable the button from within a  `finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="9a5da-139">Um dieses Szenario festzulegen, nehmen Sie am grundlegenden Code aus [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample) folgende Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9a5da-139">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="9a5da-140">Sie können die fertige App auch unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-140">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="9a5da-141">Der Projektname ist „DisableStartButton“.</span><span class="sxs-lookup"><span data-stu-id="9a5da-141">The name of the project is DisableStartButton.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Text = "";

    // ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = false;

    try
    {
        await AccessTheWebAsync();
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
    // ***Enable the Start button in case you want to run the program again.
    finally
    {
        StartButton.IsEnabled = true;
    }
}
```

<span data-ttu-id="9a5da-142">Aufgrund der Änderungen reagiert die Schaltfläche nicht, während die Websites von `AccessTheWebAsync` heruntergeladen werden, sodass ein erneutes Eintreten in den Prozess nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="9a5da-142">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="9a5da-143">Den Vorgang abbrechen und neu starten</span><span class="sxs-lookup"><span data-stu-id="9a5da-143">Cancel and Restart the Operation</span></span>

<span data-ttu-id="9a5da-144">Anstatt die Schaltfläche **Start** zu deaktivieren, kann die Schaltfläche aktiv bleiben. Wenn der Benutzer die Schaltfläche dann erneut anklickt, brechen Sie den bereits ausgeführten Vorgang ab und lassen den zuletzt begonnenen Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-144">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="9a5da-145">Weitere Informationen zum Abbrechen finden Sie unter [Fine-Tuning Your Async Application (C#) (Abstimmen der asynchronen Anwendung (C#))](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="9a5da-145">For more information about cancellation, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="9a5da-146">Um dieses Szenario festzulegen, nehmen Sie am grundlegenden Code aus [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample) folgende Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9a5da-146">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="9a5da-147">Sie können die fertige App auch unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-147">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="9a5da-148">Der Name des Projekts lautet „CancelAndRestart“.</span><span class="sxs-lookup"><span data-stu-id="9a5da-148">The name of the project is CancelAndRestart.</span></span>

1. <span data-ttu-id="9a5da-149">Deklarieren Sie eine <xref:System.Threading.CancellationTokenSource>-Variable, `cts`, die im Bereich für alle Methoden liegt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-149">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="9a5da-150">Bestimmen Sie im Element `StartButton_Click`, ob ein Vorgang bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a5da-150">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="9a5da-151">Wenn der Wert von `cts` 0 (null) lautet, ist noch kein Vorgang aktiv.</span><span class="sxs-lookup"><span data-stu-id="9a5da-151">If the value of `cts` is null, no operation is already active.</span></span> <span data-ttu-id="9a5da-152">Wenn der Wert nicht NULL ist, wird der Vorgang, der bereits ausgeführt wird, abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-152">If the value isn't null, the operation that is already running is canceled.</span></span>

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. <span data-ttu-id="9a5da-153">Legen Sie `cts` auf einen anderen Wert fest, der den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-153">Set `cts` to a different value that represents the current process.</span></span>

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. <span data-ttu-id="9a5da-154">Am Ende von `StartButton_Click` ist der aktuelle Prozess abgeschlossen. Setzen Sie den Wert für `cts` also zurück auf NULL.</span><span class="sxs-lookup"><span data-stu-id="9a5da-154">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to null.</span></span>

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

<span data-ttu-id="9a5da-155">Im folgende Code werden alle Änderungen in `StartButton_Click` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-155">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="9a5da-156">Die Ergänzungen werden mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="9a5da-156">The additions are marked with asterisks.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Clear();

    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }

    // *** Now set cts to cancel the current process if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;

    try
    {
        // ***Send cts.Token to carry the message if there is a cancellation request.
        await AccessTheWebAsync(cts.Token);

    }
    // *** Catch cancellations separately.
    catch (OperationCanceledException)
    {
        ResultsTextBox.Text += "\r\nDownloads canceled.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.\r\n";
    }
    // *** When the process is complete, signal that another process can proceed.
    if (cts == newCTS)
        cts = null;
}
```

<span data-ttu-id="9a5da-157">Nehmen Sie dazu in `AccessTheWebAsync`die folgenden Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9a5da-157">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="9a5da-158">Fügen Sie einen Parameter hinzu, um das Abbruchtoken von `StartButton_Click` zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="9a5da-158">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="9a5da-159">Verwenden Sie die <xref:System.Net.Http.HttpClient.GetAsync%2A>-Methode zum Herunterladen der Websites, da `GetAsync` ein <xref:System.Threading.CancellationToken> Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9a5da-159">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="9a5da-160">Bevor Sie `DisplayResults` aufrufen, um die Ergebnisse für jede heruntergeladene Website anzuzeigen, aktivieren Sie `ct`, um sicherzustellen, dass der aktuelle Vorgang nicht abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="9a5da-160">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

<span data-ttu-id="9a5da-161">Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-161">The following code shows these changes, which are marked with asterisks.</span></span>

```csharp
// *** Provide a parameter for the CancellationToken from StartButton_Click.
async Task AccessTheWebAsync(CancellationToken ct)
{
    // Declare an HttpClient object.
    HttpClient client = new HttpClient();

    // Make a list of web addresses.
    List<string> urlList = SetUpURLList();

    var total = 0;
    var position = 0;

    foreach (var url in urlList)
    {
        // *** Use the HttpClient.GetAsync method because it accepts a
        // cancellation token.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // *** Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // *** Check for cancellations before displaying information about the
        // latest site.
        ct.ThrowIfCancellationRequested();

        DisplayResults(url, urlContents, ++position);

        // Update the total.
        total += urlContents.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

<span data-ttu-id="9a5da-162">Wenn Sie die Schaltfläche **Start** mehrmals anklicken, während diese App ausgeführt wird, sollten Ergebnisse erzeugt werden, die der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="9a5da-162">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>

```output
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

<span data-ttu-id="9a5da-163">Zum Ausschließen der Teillisten entfernen Sie die Kommentarmarkierungen der ersten Codezeile in `StartButton_Click`, um das Textfeld bei jedem erneuten Start des Vorgangs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-163">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="BKMK_RunMultipleOperations"></a> <span data-ttu-id="9a5da-164">Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen</span><span class="sxs-lookup"><span data-stu-id="9a5da-164">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="9a5da-165">Das dritte Beispiel ist das schwierigste, da von der App jedes Mal, wenn der Benutzer die Schaltfläche **Start** anklickt, ein anderer asynchroner Vorgang gestartet wird und alle Vorgänge vollständig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-165">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="9a5da-166">Alle angeforderten Vorgänge laden Websites asynchron aus der Liste herunter, doch die Ausgabe der Vorgänge wird sequenziell dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-166">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="9a5da-167">Das bedeutet, die tatsächliche Downloadaktivität überlappt, wie es die Ausgabe in [Erkennen von Ablaufinvarianz](#BKMK_RecognizingReentrancy) zeigt, die Ergebnislisten für jede Gruppe aber getrennt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-167">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="9a5da-168">Die Vorgänge geben global <xref:System.Threading.Tasks.Task>, `pendingWork` frei, der als Gatekeeper für den Anzeigenprozess dient.</span><span class="sxs-lookup"><span data-stu-id="9a5da-168">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="9a5da-169">Um dieses Szenario festzulegen, nehmen Sie am grundlegenden Code aus [Überprüfen und Ausführen der Beispiel-App](#BKMD_SettingUpTheExample) folgende Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="9a5da-169">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="9a5da-170">Sie können die fertige App auch unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-170">You also can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="9a5da-171">Der Name des Projekts lautet „QueueResults“.</span><span class="sxs-lookup"><span data-stu-id="9a5da-171">The name of the project is QueueResults.</span></span>

<span data-ttu-id="9a5da-172">Die folgende Ausgabe zeigt das Ergebnis bei einmaliger Betätigung der Schaltfläche **Start**.</span><span class="sxs-lookup"><span data-stu-id="9a5da-172">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="9a5da-173">Die Buchstabenbezeichnung „A“ gibt an, dass das Ergebnis vom ersten Klick auf die Schaltfläche **Start** stammt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-173">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="9a5da-174">Die Zahlen geben die Reihenfolge der URL in der Liste der Downloadziele wieder.</span><span class="sxs-lookup"><span data-stu-id="9a5da-174">The numbers show the order of the URLs in the list of download targets.</span></span>

```output
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

<span data-ttu-id="9a5da-175">Wenn der Benutzer die Schaltfläche **Start** dreimal anklickt, erzeugt die App eine Ausgabe, die den folgenden Zeilen ähnelt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-175">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="9a5da-176">Die Informationszeilen, die mit einem Nummernzeichen (#) beginnen, verfolgen den Status der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9a5da-176">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```output
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

<span data-ttu-id="9a5da-177">Die Gruppen B und C starten, bevor Gruppe A beendet ist, doch die Ausgabe für jede Gruppe wird getrennt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-177">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="9a5da-178">Die gesamte Ausgabe für Gruppe A wird zuerst angezeigt, gefolgt von der gesamten Ausgabe für Gruppe B und dann die gesamte Ausgabe für Gruppe C. Die App zeigt die Gruppen immer in Reihenfolge an, und die Informationen zu den einzelnen Websites werden immer in der Reihenfolge angezeigt, in der die URLs in der URL-Liste aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-178">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="9a5da-179">Sie können die Reihenfolge, in der die Downloads tatsächlich vorkommen, allerdings nicht vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-179">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="9a5da-180">Nachdem mehrere Gruppen gestartet wurden, sind alle von ihnen generierten Downloadtasks aktiv.</span><span class="sxs-lookup"><span data-stu-id="9a5da-180">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="9a5da-181">Sie können nicht davon ausgehen, dass A-1 vor B-1 heruntergeladen wird, und Sie können auch nicht davon ausgehen, dass A-1 vor A-2 heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="9a5da-181">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="9a5da-182">Globale Definitionen</span><span class="sxs-lookup"><span data-stu-id="9a5da-182">Global Definitions</span></span>

<span data-ttu-id="9a5da-183">Im Beispielcode sind die folgenden zwei globalen Deklarationen enthalten, die von allen Methoden sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="9a5da-183">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

<span data-ttu-id="9a5da-184">Mit der `Task`-Variable `pendingWork` wird der Anzeigenprozess beaufsichtigt, und es wird verhindert, dass der Anzeigevorgang einer Gruppe zur Unterbrechung des Anzeigevorgangs einer anderen Gruppe führt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-184">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="9a5da-185">Die Zeichenvariable `group` bezeichnet die Ausgabe von unterschiedlichen Gruppen, um sicherzustellen, dass Ergebnisse in der erwarteten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a5da-185">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="9a5da-186">Der Click-Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="9a5da-186">The Click Event Handler</span></span>

<span data-ttu-id="9a5da-187">Mit dem Ereignishandler `StartButton_Click` wird der Gruppenbuchstabe bei jedem Auswählen der Schaltfläche **Start** erhöht.</span><span class="sxs-lookup"><span data-stu-id="9a5da-187">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="9a5da-188">Anschließend ruft der Handler zum Ausführen des Downloadingvorgangs das Element `AccessTheWebAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="9a5da-188">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // ***Verify that each group's results are displayed together, and that
    // the groups display in order, by marking each group with a letter.
    group = (char)(group + 1);
    ResultsTextBox.Text += $"\r\n\r\n#Starting group {group}.";

    try
    {
        // *** Pass the group value to AccessTheWebAsync.
        char finishedGroup = await AccessTheWebAsync(group);

        // The following line verifies a successful return from the download and
        // display procedures.
        ResultsTextBox.Text += $"\r\n\r\n#Group {finishedGroup} is complete.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
}
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="9a5da-189">Die AccessTheWebAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="9a5da-189">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="9a5da-190">In diesem Beispiel wird `AccessTheWebAsync` in zwei Methoden aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-190">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="9a5da-191">Mit der erste Methode, `AccessTheWebAsync`, werden alle Downloadtasks für eine Gruppe gestartet und `pendingWork` wird zum Steuern des Anzeigenprozesses festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-191">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="9a5da-192">Die Methode verwendet zum gleichzeitigen Starten aller Downloadtasks eine LINQ-Abfrage (Language-Integrated Query) sowie <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a5da-192">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="9a5da-193">`AccessTheWebAsync` ruft dann `FinishOneGroupAsync` auf, um den Abschluss jedes einzelnen Downloads zu erwarten und die Länge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-193">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="9a5da-194">`FinishOneGroupAsync` gibt einen Task zurück, der in `pendingWork` dem Element `AccessTheWebAsync` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9a5da-194">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="9a5da-195">Dieser Wert verhindert die Unterbrechung durch einen anderen Vorgang, bevor die Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9a5da-195">That value prevents interruption by another operation before the task is complete.</span></span>

```csharp
private async Task<char> AccessTheWebAsync(char grp)
{
    HttpClient client = new HttpClient();

    // Make a list of the web addresses to download.
    List<string> urlList = SetUpURLList();

    // ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Task<byte[]>[] getContentTasks = urlList.Select(url => client.GetByteArrayAsync(url)).ToArray();

    // ***Call the method that awaits the downloads and displays the results.
    // Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp);

    ResultsTextBox.Text += $"\r\n#Task assigned for group {grp}. Download tasks are active.\r\n";

    // ***This task is complete when a group has finished downloading and displaying.
    await pendingWork;

    // You can do other work here or just return.
    return grp;
}
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="9a5da-196">Die FinishOneGroupAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="9a5da-196">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="9a5da-197">Diese Methode durchläuft die Downloadaufgaben in einer Gruppe, erwartet dabei jeden einzelnen Task, zeigt die Länge der heruntergeladenen Website an und addiert diese Länge zur Summe.</span><span class="sxs-lookup"><span data-stu-id="9a5da-197">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="9a5da-198">Die erste Anweisung in `FinishOneGroupAsync` verwendet `pendingWork`, um sicherzustellen, dass die Eingabe der Methode keinen Vorgang behindert, der sich bereits im Anzeige- oder im Warteprozess befindet.</span><span class="sxs-lookup"><span data-stu-id="9a5da-198">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="9a5da-199">Wenn ein solcher Vorgang ausgeführt wird, wird der eintretende Vorgang solange aufgeschoben, bis er an der Reihe ist.</span><span class="sxs-lookup"><span data-stu-id="9a5da-199">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```csharp
private async Task FinishOneGroupAsync(List<string> urls, Task<byte[]>[] contentTasks, char grp)
{
    // ***Wait for the previous group to finish displaying results.
    if (pendingWork != null) await pendingWork;

    int total = 0;

    // contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    for (int i = 0; i < contentTasks.Length; i++)
    {
        // Await the download of a particular URL, and then display the URL and
        // its length.
        byte[] content = await contentTasks[i];
        DisplayResults(urls[i], content, i, grp);
        total += content.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

#### <a name="points-of-interest"></a><span data-ttu-id="9a5da-200">Relevante Punkte</span><span class="sxs-lookup"><span data-stu-id="9a5da-200">Points of Interest</span></span>

<span data-ttu-id="9a5da-201">Die Informationszeilen, die mit einem Nummernzeichen (#) in der Ausgabe beginnen, erläutern die Funktionsweise dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="9a5da-201">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="9a5da-202">Die Ausgabe zeigt die folgenden Muster an.</span><span class="sxs-lookup"><span data-stu-id="9a5da-202">The output shows the following patterns.</span></span>

- <span data-ttu-id="9a5da-203">Eine Gruppe kann gestartet werden, während die Ausgabe einer vorherigen Gruppe angezeigt wird. Doch die Anzeige der Ausgabe der vorherigen Gruppe wird nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-203">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

    ```output
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

- <span data-ttu-id="9a5da-204">Die `pendingWork`-Aufgabe ist zu Beginn von `FinishOneGroupAsync` nur für Gruppe A, die zuerst gestartet wurde, 0 (null).</span><span class="sxs-lookup"><span data-stu-id="9a5da-204">The `pendingWork` task is null  at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="9a5da-205">Gruppe A hat bei Erreichen von `FinishOneGroupAsync` einen Erwartungsausdruck noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-205">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="9a5da-206">Daher wurde die Steuerung nicht an `AccessTheWebAsync` zurückgegeben, und die erste Zuweisung zu `pendingWork` ist nicht aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9a5da-206">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="9a5da-207">Die folgenden zwei Zeilen werden immer zusammen in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-207">The following two lines always appear together in the output.</span></span> <span data-ttu-id="9a5da-208">Der Code wird zwischen dem Starten des Vorgangs einer Gruppe in `StartButton_Click` und dem Zuweisen eines Tasks für die Gruppe zu `pendingWork` nie unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-208">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    <span data-ttu-id="9a5da-209">Nachdem eine Gruppe in `StartButton_Click` eintritt, schließt der Vorgang einen Erwartungsausdruck erst ab, wenn der Vorgang in `FinishOneGroupAsync` eintritt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-209">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="9a5da-210">Daher kann kein weiterer Vorgang während dieses Codeabschnitts die Steuerung übernehmen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-210">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="BKMD_SettingUpTheExample"></a> <span data-ttu-id="9a5da-211">Die Beispiel-App überprüfen und ausführen</span><span class="sxs-lookup"><span data-stu-id="9a5da-211">Reviewing and Running the Example App</span></span>

<span data-ttu-id="9a5da-212">Zum besseren Verständnis der Beispiel-App können Sie sie herunterladen, sie selbst erstellen oder den Code am Ende dieses Themas überprüfen, ohne die App zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9a5da-212">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5da-213">Um die App des Beispiels als WPF-Desktop-App (Windows Presentation Foundation) auszuführen, muss Visual Studio 2012 oder höher oder .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="9a5da-213">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="9a5da-214">Herunterladen der App</span><span class="sxs-lookup"><span data-stu-id="9a5da-214">Downloading the App</span></span>

1. <span data-ttu-id="9a5da-215">Sie können die komprimierte Datei unter [Async Samples: Reentrancy in .NET Desktop Apps (Asynchrone Beispiele: Ablaufinvarianz in .NET-Desktop-Apps)](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-215">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="9a5da-216">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a5da-216">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="9a5da-217">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="9a5da-217">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="9a5da-218">Navigieren Sie zu dem Ordner mit dem dekomprimierten Beispielcode, und öffnen Sie die Projektmappendatei (SLN-Datei).</span><span class="sxs-lookup"><span data-stu-id="9a5da-218">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="9a5da-219">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, das Sie ausführen möchten, und wählen Sie dann **Set as StartUpProject** (Als StartUpProject festlegen) aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-219">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="9a5da-220">Drücken Sie zum Erstellen und Ausführen des Projekts die Tastenkombination "STRG+F5".</span><span class="sxs-lookup"><span data-stu-id="9a5da-220">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="9a5da-221">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="9a5da-221">Building the App</span></span>

<span data-ttu-id="9a5da-222">Der folgende Abschnitt enthält den Code, um das Beispiel als WPF-App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-222">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="9a5da-223">So erstellen Sie eine WPF-App</span><span class="sxs-lookup"><span data-stu-id="9a5da-223">To build a WPF app</span></span>

1. <span data-ttu-id="9a5da-224">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a5da-224">Start Visual Studio.</span></span>

2. <span data-ttu-id="9a5da-225">Wählen Sie in der Menüleiste **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-225">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="9a5da-226">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-226">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="9a5da-227">Erweitern Sie im Bereich **Installed Templates** (Installierte Vorlagen) den Eintrag **Visual C#** , und erweitern Sie dann **Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a5da-227">In the **Installed Templates** pane, expand **Visual C#**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="9a5da-228">Wählen Sie in der Liste der Projekttypen **WPF-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-228">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="9a5da-229">Benennen Sie das Projekt `WebsiteDownloadWPF`, wählen Sie die .NET Framework-Version 4.6 oder höher aus, und klicken Sie dann auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a5da-229">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="9a5da-230">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-230">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="9a5da-231">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-231">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="9a5da-232">Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-232">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="9a5da-233">Ersetzen Sie den automatisch generierten Code in der **XAML**-Ansicht der Datei „MainWindow.xaml“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="9a5da-233">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```csharp
    <Window x:Class="WebsiteDownloadWPF.MainWindow"
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

     <span data-ttu-id="9a5da-234">Ein einfaches Fenster, das ein Textfeld und eine Schaltfläche enthält, wird in der **Entwurfsansicht** der Datei „MainWindow.xaml“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5da-234">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="9a5da-235">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Verweise**, und klicken Sie anschließend auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9a5da-235">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="9a5da-236">Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu, sofern dieser nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="9a5da-236">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="9a5da-237">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-237">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

10. <span data-ttu-id="9a5da-238">Ersetzen Sie den Code in „MainWindow.xaml.cs“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="9a5da-238">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

    // Add the following using directives, and add a reference for System.Net.Http.
    using System.Net.Http;
    using System.Threading;

    namespace WebsiteDownloadWPF
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                System.Net.ServicePointManager.SecurityProtocol |= System.Net.SecurityProtocolType.Tls12;
                InitializeComponent();
            }

            private async void StartButton_Click(object sender, RoutedEventArgs e)
            {
                // This line is commented out to make the results clearer in the output.
                //ResultsTextBox.Text = "";

                try
                {
                    await AccessTheWebAsync();
                }
                catch (Exception)
                {
                    ResultsTextBox.Text += "\r\nDownloads failed.";
                }
            }

            private async Task AccessTheWebAsync()
            {
                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                // Make a list of web addresses.
                List<string> urlList = SetUpURLList();

                var total = 0;
                var position = 0;

                foreach (var url in urlList)
                {
                    // GetByteArrayAsync returns a task. At completion, the task
                    // produces a byte array.
                    byte[] urlContents = await client.GetByteArrayAsync(url);

                    DisplayResults(url, urlContents, ++position);

                    // Update the total.
                    total += urlContents.Length;
                }

                // Display the total count for all of the websites.
                ResultsTextBox.Text +=
                    $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
            }

            private List<string> SetUpURLList()
            {
                List<string> urls = new List<string>
                {
                    "https://msdn.microsoft.com/library/hh191443.aspx",
                    "https://msdn.microsoft.com/library/aa578028.aspx",
                    "https://msdn.microsoft.com/library/jj155761.aspx",
                    "https://msdn.microsoft.com/library/hh290140.aspx",
                    "https://msdn.microsoft.com/library/hh524395.aspx",
                    "https://msdn.microsoft.com/library/ms404677.aspx",
                    "https://msdn.microsoft.com",
                    "https://msdn.microsoft.com/library/ff730837.aspx"
                };
                return urls;
            }

            private void DisplayResults(string url, byte[] content, int pos)
            {
                // Display the length of each website. The string format is designed
                // to be used with a monospaced font, such as Lucida Console or
                // Global Monospace.

                // Strip off the "https://".
                var displayURL = url.Replace("https://", "");
                // Display position in the URL list, the URL, and the number of bytes.
                ResultsTextBox.Text += $"\n{pos}. {displayURL,-58} {content.Length,8}";
            }
        }
    }
    ```

11. <span data-ttu-id="9a5da-239">Wählen Sie zum Ausführen des Programms die Tastenkombination „STRG+F5“ aus, und wählen Sie dann mehrmals die Schaltfläche **Start** aus.</span><span class="sxs-lookup"><span data-stu-id="9a5da-239">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="9a5da-240">Nehmen Sie die Änderungen aus [Die Schaltfläche „Start“ deaktivieren](#BKMK_DisableTheStartButton), [Den Vorgang abbrechen und neu starten](#BKMK_CancelAndRestart) oder [Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange stellen](#BKMK_RunMultipleOperations) vor, um mit Ablaufinvarianz umzugehen.</span><span class="sxs-lookup"><span data-stu-id="9a5da-240">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a5da-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a5da-241">See also</span></span>

- [<span data-ttu-id="9a5da-242">Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="9a5da-242">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="9a5da-243">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="9a5da-243">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
