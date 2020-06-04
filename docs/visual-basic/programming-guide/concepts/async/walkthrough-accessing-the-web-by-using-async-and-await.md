---
title: 'Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 41ededd4d4335b78b8d7a33e8fe387c7d632cbee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400744"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="780ad-102">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="780ad-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="780ad-103">Sie können asynchrone Programme mit den Funktionen „Async/Await“ einfacher und intuitiver schreiben.</span><span class="sxs-lookup"><span data-stu-id="780ad-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="780ad-104">Sie können asynchronen Code schreiben, der wie synchroner Code aussieht und veranlassen, dass der Compiler die komplizierten Rückruffunktionen und Fortsetzungen verarbeitet, die durch den asynchronen Code für gewöhnlich verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>

<span data-ttu-id="780ad-105">Weitere Informationen zum Async-Feature finden Sie unter [asynchrone Programmierung mit Async und warten (Visual Basic)](index.md).</span><span class="sxs-lookup"><span data-stu-id="780ad-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](index.md).</span></span>

<span data-ttu-id="780ad-106">Diese exemplarische Vorgehensweise beginnt mit einer synchronen WPF-Anwendung (Windows Presentation Foundation), die die Anzahl der Bytes in einer Liste von Websites summiert.</span><span class="sxs-lookup"><span data-stu-id="780ad-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="780ad-107">In der exemplarischen Vorgehensweise wird die Anwendung dann mithilfe der neuen Funktionen in eine asynchrone Lösung umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="780ad-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>

<span data-ttu-id="780ad-108">Wenn Sie die Anwendungen nicht selbst erstellen möchten, können Sie das „Thema mit einem asynchronen Beispiel für die exemplarische Vorgehensweise für den Internetzugriff (C# und Visual Basic)“ in englischer Sprache über [Entwickler-Codebeispiele](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="780ad-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

<span data-ttu-id="780ad-109">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="780ad-109">In this walkthrough, you complete the following tasks:</span></span>

> [!div class="checklist"]
>
> - [<span data-ttu-id="780ad-110">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="780ad-110">Create a WPF application</span></span>](#create-a-wpf-application)
> - [<span data-ttu-id="780ad-111">Entwerfen eines einfachen WPF-MainWindows</span><span class="sxs-lookup"><span data-stu-id="780ad-111">Design a simple WPF MainWindow</span></span>](#design-a-simple-wpf-mainwindow)
> - [<span data-ttu-id="780ad-112">Hinzufügen eines Verweises</span><span class="sxs-lookup"><span data-stu-id="780ad-112">Add a reference</span></span>](#add-a-reference)
> - [<span data-ttu-id="780ad-113">Erforderliche Imports-Anweisungen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="780ad-113">Add necessary Imports statements</span></span>](#add-necessary-imports-statements)
> - [<span data-ttu-id="780ad-114">Erstellen einer synchronen Anwendung</span><span class="sxs-lookup"><span data-stu-id="780ad-114">Create a synchronous application</span></span>](#create-a-synchronous-application)
> - [<span data-ttu-id="780ad-115">Testen der synchronen Lösung</span><span class="sxs-lookup"><span data-stu-id="780ad-115">Test the synchronous solution</span></span>](#test-the-synchronous-solution)
> - [<span data-ttu-id="780ad-116">Konvertieren von „GetURLContents“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-116">Convert GetURLContents to an asynchronous method</span></span>](#convert-geturlcontents-to-an-asynchronous-method)
> - [<span data-ttu-id="780ad-117">Konvertieren von „SumPageSizes“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-117">Convert SumPageSizes to an asynchronous method</span></span>](#convert-sumpagesizes-to-an-asynchronous-method)
> - [<span data-ttu-id="780ad-118">Konvertieren von „startButton_Click“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-118">Convert startButton_Click to an asynchronous method</span></span>](#convert-startbutton_click-to-an-asynchronous-method)
> - [<span data-ttu-id="780ad-119">Testen der asynchronen Lösung</span><span class="sxs-lookup"><span data-stu-id="780ad-119">Test the asynchronous solution</span></span>](#test-the-asynchronous-solution)
> - [<span data-ttu-id="780ad-120">Ersetzen der geturlcontentsasync-Methode durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-120">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

<span data-ttu-id="780ad-121">Das komplette asynchrone Beispiel finden Sie im [Beispiel](#example) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="780ad-121">See the [Example](#example) section for the complete asynchronous example.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="780ad-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="780ad-122">Prerequisites</span></span>

<span data-ttu-id="780ad-123">Visual Studio 2012 oder höher muss auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="780ad-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="780ad-124">Weitere Informationen finden Sie auf der Visual Studio- [Download](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) Seite.</span><span class="sxs-lookup"><span data-stu-id="780ad-124">For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

## <a name="create-a-wpf-application"></a><span data-ttu-id="780ad-125">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="780ad-125">Create a WPF application</span></span>

1. <span data-ttu-id="780ad-126">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="780ad-126">Start Visual Studio.</span></span>

2. <span data-ttu-id="780ad-127">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="780ad-128">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="780ad-128">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="780ad-129">Wählen Sie im Bereich **installierte Vorlagen** die Option Visual Basic aus, und wählen Sie dann in der Liste der Projekttypen die Option **WPF-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="780ad-130">Geben Sie im Textfeld **Name**`AsyncExampleWPF` ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>

    <span data-ttu-id="780ad-131">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="780ad-131">The new project appears in **Solution Explorer**.</span></span>

## <a name="design-a-simple-wpf-mainwindow"></a><span data-ttu-id="780ad-132">Entwerfen eines einfachen WPF-MainWindows</span><span class="sxs-lookup"><span data-stu-id="780ad-132">Design a simple WPF MainWindow</span></span>

1. <span data-ttu-id="780ad-133">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

2. <span data-ttu-id="780ad-134">Wenn das Fenster **Toolbox** nicht sichtbar ist, öffnen Sie das Menü **Ansicht**, und wählen Sie dann **Toolbox** aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>

3. <span data-ttu-id="780ad-135">Fügen Sie dem Fenster **MainWindow** ein **Button**-Steuerelement und ein **TextBox**-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="780ad-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>

4. <span data-ttu-id="780ad-136">Markieren Sie das **TextBox**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="780ad-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="780ad-137">Legen Sie die Eigenschaft **Name**auf `resultsTextBox` fest.</span><span class="sxs-lookup"><span data-stu-id="780ad-137">Set the **Name** property to `resultsTextBox`.</span></span>

    - <span data-ttu-id="780ad-138">Legen Sie die Eigenschaft **Height** auf „250“ fest.</span><span class="sxs-lookup"><span data-stu-id="780ad-138">Set the **Height** property to 250.</span></span>

    - <span data-ttu-id="780ad-139">Legen Sie die Eigenschaft **Width** auf „500“ fest.</span><span class="sxs-lookup"><span data-stu-id="780ad-139">Set the **Width** property to 500.</span></span>

    - <span data-ttu-id="780ad-140">Geben Sie auf der Registerkarte **Text** eine Festbreitenschriftart wie Lucida Console oder Global Monospace an.</span><span class="sxs-lookup"><span data-stu-id="780ad-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>

5. <span data-ttu-id="780ad-141">Markieren Sie das **Button**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="780ad-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>

    - <span data-ttu-id="780ad-142">Legen Sie die Eigenschaft **Name**auf `startButton` fest.</span><span class="sxs-lookup"><span data-stu-id="780ad-142">Set the **Name** property to `startButton`.</span></span>

    - <span data-ttu-id="780ad-143">Ändern Sie den Wert der Eigenschaft **Content** von **Button** zu **Start**.</span><span class="sxs-lookup"><span data-stu-id="780ad-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>

6. <span data-ttu-id="780ad-144">Positionieren Sie das Textfeld und die Schaltfläche so, dass beide im Fenster **MainWindow** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>

    <span data-ttu-id="780ad-145">Weitere Informationen über den WPF-XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="780ad-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>

## <a name="add-a-reference"></a><span data-ttu-id="780ad-146">Hinzufügen eines Verweises</span><span class="sxs-lookup"><span data-stu-id="780ad-146">Add a reference</span></span>

1. <span data-ttu-id="780ad-147">Markieren Sie im **Projektmappen-Explorer** den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="780ad-147">In **Solution Explorer**, highlight your project's name.</span></span>

2. <span data-ttu-id="780ad-148">Wählen Sie in der Menüleiste die Optionen **Projekt** und **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>

    <span data-ttu-id="780ad-149">Das Dialogfeld **Verweis-Manager** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="780ad-149">The **Reference Manager** dialog box appears.</span></span>

3. <span data-ttu-id="780ad-150">Stellen Sie oben im Dialogfeld sicher, dass Ihr Projekt auf .NET Framework 4.5 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="780ad-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>

4. <span data-ttu-id="780ad-151">Wählen Sie im Bereich **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>

5. <span data-ttu-id="780ad-152">Aktivieren Sie in der Liste der Namen das Kontrollkästchen **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="780ad-152">In the list of names, select the **System.Net.Http** check box.</span></span>

6. <span data-ttu-id="780ad-153">Wählen Sie die Schaltfläche **OK** aus, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="780ad-153">Choose the **OK** button to close the dialog box.</span></span>

## <a name="add-necessary-imports-statements"></a><span data-ttu-id="780ad-154">Erforderliche Imports-Anweisungen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="780ad-154">Add necessary Imports statements</span></span>

1. <span data-ttu-id="780ad-155">Öffnen Sie in **Projektmappen-Explorer**das Kontextmenü für "MainWindow. XAML. vb", und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

2. <span data-ttu-id="780ad-156">Fügen `Imports` Sie am Anfang der Codedatei die folgenden-Anweisungen hinzu, wenn Sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="780ad-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a><span data-ttu-id="780ad-157">Erstellen einer synchronen Anwendung</span><span class="sxs-lookup"><span data-stu-id="780ad-157">Create a synchronous application</span></span>

1. <span data-ttu-id="780ad-158">Doppelklicken Sie im Entwurfs Fenster MainWindow. XAML auf die Schaltfläche **Start** , um den `startButton_Click` Ereignishandler in "MainWindow. XAML. vb" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="780ad-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="780ad-159">Kopieren Sie den folgenden Code in "MainWindow. XAML. vb" in den Text von `startButton_Click` :</span><span class="sxs-lookup"><span data-stu-id="780ad-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    <span data-ttu-id="780ad-160">Der Code ruft die Methode `SumPageSizes` auf, die die Anwendung steuert und zeigt eine Meldung an, wenn das Steuerelement zu `startButton_Click` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>

3. <span data-ttu-id="780ad-161">Der Code für die synchrone Lösung enthält die folgenden vier Methoden:</span><span class="sxs-lookup"><span data-stu-id="780ad-161">The code for the synchronous solution contains the following four methods:</span></span>

    - <span data-ttu-id="780ad-162">`SumPageSizes`. Enthält eine Liste von Webseiten-URLs aus `SetUpURLList` und ruft dann `GetURLContents` und `DisplayResults` auf, um jede URL zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="780ad-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>

    - <span data-ttu-id="780ad-163">`SetUpURLList`. Erstellt und gibt eine Liste der Webadressen zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>

    - <span data-ttu-id="780ad-164">`GetURLContents`. Lädt Inhalte jeder Website herunter und gibt die Inhalte als ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>

    - <span data-ttu-id="780ad-165">`DisplayResults`. Zeigt die Anzahl der Bytes im Bytearray für jede URL an.</span><span class="sxs-lookup"><span data-stu-id="780ad-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>

    <span data-ttu-id="780ad-166">Kopieren Sie die folgenden vier Methoden, und fügen Sie Sie dann unter dem- `startButton_Click` Ereignishandler in MainWindow. XAML. vb ein:</span><span class="sxs-lookup"><span data-stu-id="780ad-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a><span data-ttu-id="780ad-167">Testen der synchronen Lösung</span><span class="sxs-lookup"><span data-stu-id="780ad-167">Test the synchronous solution</span></span>

1. <span data-ttu-id="780ad-168">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="780ad-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="780ad-169">Die Ausgabe sollte der folgenden Liste ähnlich sein:</span><span class="sxs-lookup"><span data-stu-id="780ad-169">Output that resembles the following list should appear:</span></span>

    ```console
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
    msdn.microsoft.com                                            33964
    msdn.microsoft.com/library/hh290136.aspx               225793
    msdn.microsoft.com/library/ee256749.aspx               143577
    msdn.microsoft.com/library/hh290138.aspx               237372
    msdn.microsoft.com/library/hh290140.aspx               128279
    msdn.microsoft.com/library/dd470362.aspx               157649
    msdn.microsoft.com/library/aa578028.aspx               204457
    msdn.microsoft.com/library/ms404677.aspx               176405
    msdn.microsoft.com/library/ff730837.aspx               143474

    Total bytes returned:  1834802

    Control returned to startButton_Click.
    ```

    <span data-ttu-id="780ad-170">Beachten Sie, dass es ein paar Sekunden dauert, bis die Zahlen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="780ad-171">Während dieser Zeit ist der Benutzeroberflächenthread blockiert, während auf das Herunterladen von angeforderten Ressourcen gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="780ad-172">Daher können Sie das Anzeigefenster weder verschieben, maximieren, minimieren noch schließen, nachdem Sie die Schaltfläche **Start** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="780ad-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="780ad-173">Diese Bemühungen sind nicht erfolgreich, bis der Bytezähler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="780ad-174">Wenn eine Website nicht antwortet, erhalten Sie keinen Hinweis darüber, welche Site fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="780ad-175">Es ist sogar schwierig, mit dem Warten aufzuhören und das Programm zu schließen.</span><span class="sxs-lookup"><span data-stu-id="780ad-175">It is difficult even to stop waiting and close the program.</span></span>

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a><span data-ttu-id="780ad-176">Konvertieren von „GetURLContents“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-176">Convert GetURLContents to an asynchronous method</span></span>

1. <span data-ttu-id="780ad-177">Um die synchrone Projekt Mappe in eine asynchrone Lösung zu konvertieren, ist der beste Ausgangspunkt, `GetURLContents` da bei den Aufrufen der <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> -Methode und der- <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> Methode der Zugriff der Anwendung auf das Internet erfolgt.</span><span class="sxs-lookup"><span data-stu-id="780ad-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web.</span></span> <span data-ttu-id="780ad-178">.NET Framework erleichtert die Konvertierung, indem asynchrone Versionen beider Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>

    <span data-ttu-id="780ad-179">Weitere Informationen über die in `GetURLContents` verwendeten Methoden finden Sie unter <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="780ad-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="780ad-180">Beim Befolgen der Schritte in dieser exemplarischen Vorgehensweise treten verschiedene Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="780ad-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="780ad-181">Sie können diese ignorieren und mit der exemplarischen Vorgehensweise fortfahren.</span><span class="sxs-lookup"><span data-stu-id="780ad-181">You can ignore them and continue with the walkthrough.</span></span>

    <span data-ttu-id="780ad-182">Ändern Sie die Methode, die aufgerufen wird, in der dritten Zeile von `GetURLContents` von `GetResponse` zur asynchronen, aufgabenbasierten <xref:System.Net.WebRequest.GetResponseAsync%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="780ad-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. <span data-ttu-id="780ad-183">`GetResponseAsync` gibt einen Wert vom Typ <xref:System.Threading.Tasks.Task%601> zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="780ad-184">In diesem Fall weist die *Aufgaben Rückgabe Variable*, `TResult` , den-Typ auf <xref:System.Net.WebResponse> .</span><span class="sxs-lookup"><span data-stu-id="780ad-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="780ad-185">Mit dieser Aufgabe soll ein tatsächliches `WebResponse`-Objekt erstellt werden, nachdem die angeforderten Daten heruntergeladen und das Ausführen der Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="780ad-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>

    <span data-ttu-id="780ad-186">Zum Abrufen des `WebResponse` Werts aus der Aufgabe wenden Sie einen [Await](../../../language-reference/operators/await-operator.md) Erwartungs Operator auf den Aufrufen von an `GetResponseAsync` , wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="780ad-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    <span data-ttu-id="780ad-187">Der `Await`-Operator hält die Ausführung der aktuellen Methode `GetURLContents` an, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-187">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="780ad-188">In der Zwischenzeit kehrt die Steuerung zum Aufrufer der aktuellen Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="780ad-189">In diesem Beispiel lautet die aktuelle Methode `GetURLContents`, und der Aufrufer ist `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="780ad-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="780ad-190">Wenn die Aufgabe abgeschlossen ist, wird das zugesicherte `WebResponse`-Objekt als Wert der erwarteten Aufgabe erstellt und zur Variable `response` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="780ad-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>

    <span data-ttu-id="780ad-191">Die vorherige Anweisung kann in die folgenden zwei Anweisungen getrennt werden, um zu verdeutlichen, was geschieht.</span><span class="sxs-lookup"><span data-stu-id="780ad-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    <span data-ttu-id="780ad-192">Durch den Aufruf von `webReq.GetResponseAsync` wird `Task(Of WebResponse)` oder `Task<WebResponse>` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="780ad-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="780ad-193">Anschließend wird ein- `Await` Operator auf die Aufgabe angewendet, um den `WebResponse` Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="780ad-193">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>

    <span data-ttu-id="780ad-194">Wenn Ihre asynchrone Methode Aktionen vornehmen muss, die nicht von der Fertigstellung der Aufgabe abhängen, kann die Methode diese Aktionen zwischen zwei Anweisungen fortsetzen, und zwar nach dem Aufruf der asynchronen Methode und vor dem Anwenden des await-Operators.</span><span class="sxs-lookup"><span data-stu-id="780ad-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied.</span></span> <span data-ttu-id="780ad-195">Beispiele finden Sie unter Gewusst [wie: Paralleles Erstellen mehrerer Webanforderungen mit Async und warten (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) und Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehens [Weise mithilfe von "Task. alle" (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="780ad-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

3. <span data-ttu-id="780ad-196">Da Sie den Operator `Await` im vorherigen Schritt hinzugefügt haben, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="780ad-196">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="780ad-197">Der-Operator kann nur in Methoden verwendet werden, die mit dem [Async](../../../language-reference/modifiers/async.md) -Modifizierer markiert sind.</span><span class="sxs-lookup"><span data-stu-id="780ad-197">The operator can be used only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="780ad-198">Ignorieren Sie den Fehler, während Sie die Konvertierungsschritte zum Ersetzen des Aufrufs von `CopyTo` mit einem Aufruf von `CopyToAsync` wiederholen.</span><span class="sxs-lookup"><span data-stu-id="780ad-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>

    - <span data-ttu-id="780ad-199">Ändern Sie den Namen der Methode, die für <xref:System.IO.Stream.CopyToAsync%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>

    - <span data-ttu-id="780ad-200">Die Methode `CopyTo` oder `CopyToAsync` kopiert Bytes zu ihrem Argument `content` und gibt keinen sinnvollen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="780ad-201">In der synchronen Version ist der Aufruf von `CopyTo` eine einfache Anweisung, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="780ad-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="780ad-202">Die asynchrone Version `CopyToAsync` gibt ein <xref:System.Threading.Tasks.Task> zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="780ad-203">Die Aufgabe funktioniert wie „Task(void)“ und ermöglicht, dass auf die Methode gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="780ad-204">Wenden Sie `Await` oder `await` auf den Aufruf von `CopyToAsync` an, wie dies im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         <span data-ttu-id="780ad-205">Die vorherige Anweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="780ad-205">The previous statement abbreviates the following two lines of code.</span></span>

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. <span data-ttu-id="780ad-206">Somit muss nur noch die Methodensignatur in `GetURLContents` angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="780ad-207">Der-Operator kann `Await` nur in Methoden verwendet werden, die mit dem [Async](../../../language-reference/modifiers/async.md) -Modifizierer markiert sind.</span><span class="sxs-lookup"><span data-stu-id="780ad-207">You can use the `Await` operator only in methods that are marked with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="780ad-208">Fügen Sie den Modifizierer hinzu, um die Methode als eine *async*-Methode zu markieren, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="780ad-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. <span data-ttu-id="780ad-209">Der Rückgabetyp einer Async-Methode kann nur <xref:System.Threading.Tasks.Task> , sein <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="780ad-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="780ad-210">In Visual Basic muss die Methode eine `Function` sein, die eine `Task` oder eine `Task(Of T)` zurückgibt, oder die Methode muss ein `Sub` sein.</span><span class="sxs-lookup"><span data-stu-id="780ad-210">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="780ad-211">In der Regel `Sub` wird eine Methode nur in einem asynchronen Ereignishandler verwendet, wobei `Sub` erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-211">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="780ad-212">In anderen Fällen verwenden Sie, `Task(T)` Wenn die abgeschlossene Methode eine [Return](../../../language-reference/statements/return-statement.md) -Anweisung aufweist, die einen Wert vom Typ T zurückgibt und Sie verwenden, `Task` Wenn die abgeschlossene Methode keinen sinnvollen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="780ad-212">In other cases, you use `Task(T)` if the completed method has a [Return](../../../language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>

    <span data-ttu-id="780ad-213">Weitere Informationen finden Sie unter [Async-Rückgabe Typen (Visual Basic)](async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="780ad-213">For more information, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>

    <span data-ttu-id="780ad-214">Die Methode `GetURLContents` verfügt über eine return-Anweisung, und die Anweisung gibt ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="780ad-215">Daher ist der Rückgabetyp der der asynchronen Version „Task(T)“, wobei „T“ ein Bytearray ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="780ad-216">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="780ad-216">Make the following changes in the method signature:</span></span>

    - <span data-ttu-id="780ad-217">Ändern Sie den Rückgabetyp zu `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="780ad-217">Change the return type to `Task(Of Byte())`.</span></span>

    - <span data-ttu-id="780ad-218">Asynchrone Methoden verfügen gemäß der Konvention über Namen, die auf „Async“ enden. Benennen Sie also die Methode `GetURLContentsAsync` um.</span><span class="sxs-lookup"><span data-stu-id="780ad-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>

    <span data-ttu-id="780ad-219">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="780ad-219">The following code shows these changes.</span></span>

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    <span data-ttu-id="780ad-220">Mit diesen wenigen Änderungen ist die Konvertierung von `GetURLContents` zu einer asynchronen Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="780ad-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a><span data-ttu-id="780ad-221">Konvertieren von „SumPageSizes“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-221">Convert SumPageSizes to an asynchronous method</span></span>

1. <span data-ttu-id="780ad-222">Wiederholen Sie die Schritte des vorherigen Verfahrens für `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="780ad-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="780ad-223">Ändern Sie zunächst den Aufruf von `GetURLContents` zu einem asynchronen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="780ad-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>

    - <span data-ttu-id="780ad-224">Ändern Sie den Namen der Methode, die aufgerufen wird, von `GetURLContents` zu `GetURLContentsAsync`, sofern Sie dies nicht bereits getan haben.</span><span class="sxs-lookup"><span data-stu-id="780ad-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>

    - <span data-ttu-id="780ad-225">Wenden Sie `Await` auf die Aufgabe an, die durch `GetURLContentsAsync` zurückgegeben wird, um den Bytearraywert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="780ad-225">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>

    <span data-ttu-id="780ad-226">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="780ad-226">The following code shows these changes.</span></span>

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    <span data-ttu-id="780ad-227">Die vorherige Zuweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="780ad-227">The previous assignment abbreviates the following two lines of code.</span></span>

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. <span data-ttu-id="780ad-228">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="780ad-228">Make the following changes in the method's signature:</span></span>

    - <span data-ttu-id="780ad-229">Markieren Sie die Methode mit dem Modifizierer `Async`.</span><span class="sxs-lookup"><span data-stu-id="780ad-229">Mark the method with the `Async` modifier.</span></span>

    - <span data-ttu-id="780ad-230">Fügen Sie dem Methodennamen „Async“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="780ad-230">Add "Async" to the method name.</span></span>

    - <span data-ttu-id="780ad-231">Diesmal gibt es keine Task Rückgabe Variable, d. h., da keinen `SumPageSizesAsync` Wert für t zurückgibt (die Methode hat keine `Return` Anweisung.) Die-Methode muss jedoch eine zurückgeben `Task` , die zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="780ad-232">Ändern Sie daher den Methodentyp von `Sub` in `Function` .</span><span class="sxs-lookup"><span data-stu-id="780ad-232">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="780ad-233">Der Rückgabetyp der Funktion lautet `Task`.</span><span class="sxs-lookup"><span data-stu-id="780ad-233">The return type of the function is `Task`.</span></span>

    <span data-ttu-id="780ad-234">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="780ad-234">The following code shows these changes.</span></span>

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    <span data-ttu-id="780ad-235">Die Konvertierung von `SumPageSizes` zu `SumPageSizesAsync` ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="780ad-235">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a><span data-ttu-id="780ad-236">Konvertieren von „startButton_Click“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-236">Convert startButton_Click to an asynchronous method</span></span>

1. <span data-ttu-id="780ad-237">Ändern Sie im Ereignishandler den Namen der aufgerufenen Methode von `SumPageSizes` zu `SumPageSizesAsync`, sofern Sie dies nicht bereits vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="780ad-237">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>

2. <span data-ttu-id="780ad-238">Da es sich bei `SumPageSizesAsync` um eine asynchrone Methode handelt, ändern Sie den Code im Ereignishandler, um auf das Ergebnis zu warten.</span><span class="sxs-lookup"><span data-stu-id="780ad-238">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>

    <span data-ttu-id="780ad-239">Der Aufruf von `SumPageSizesAsync` spiegelt den Aufruf von `CopyToAsync` in `GetURLContentsAsync` wider.</span><span class="sxs-lookup"><span data-stu-id="780ad-239">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="780ad-240">Der Aufruf gibt eine `Task` und keine `Task(T)` zurück.</span><span class="sxs-lookup"><span data-stu-id="780ad-240">The call returns a `Task`, not a `Task(T)`.</span></span>

    <span data-ttu-id="780ad-241">Analog zu den vorherigen Vorgehensweisen können Sie den Aufruf mithilfe von einer oder zwei Anweisungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="780ad-241">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="780ad-242">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="780ad-242">The following code shows these changes.</span></span>

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. <span data-ttu-id="780ad-243">Um den versehentlichen Neustart des Vorgangs zu verhindern, fügen Sie oben in `startButton_Click` die folgende Anweisung ein, um die Schaltfläche **Start** zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="780ad-243">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    <span data-ttu-id="780ad-244">Sie können die Schaltfläche am Ende des Ereignishandlers wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="780ad-244">You can reenable the button at the end of the event handler.</span></span>

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    <span data-ttu-id="780ad-245">Weitere Informationen zum erneuten eintreten finden Sie unter [Handling Reentrancy in Async Apps (Visual Basic)](handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="780ad-245">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](handling-reentrancy-in-async-apps.md).</span></span>

4. <span data-ttu-id="780ad-246">Fügen Sie der Deklaration abschließend den Modifizierer `Async` hinzu, sodass der Ereignishandler auf `SumPagSizesAsync` warten kann.</span><span class="sxs-lookup"><span data-stu-id="780ad-246">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    <span data-ttu-id="780ad-247">In der Regel werden die Namen der Ereignishandler nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="780ad-247">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="780ad-248">Der Rückgabetyp wird nicht in geändert, `Task` da Ereignishandler `Sub` in Visual Basic Prozeduren sein müssen.</span><span class="sxs-lookup"><span data-stu-id="780ad-248">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>

    <span data-ttu-id="780ad-249">Die Konvertierung des Projekts von der synchronen zu asynchronen Verarbeitung ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="780ad-249">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>

## <a name="test-the-asynchronous-solution"></a><span data-ttu-id="780ad-250">Testen der asynchronen Lösung</span><span class="sxs-lookup"><span data-stu-id="780ad-250">Test the asynchronous solution</span></span>

1. <span data-ttu-id="780ad-251">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="780ad-251">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

2. <span data-ttu-id="780ad-252">Es sollte eine Ausgabe angezeigt werden, die der Ausgabe der synchronen Lösung gleicht.</span><span class="sxs-lookup"><span data-stu-id="780ad-252">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="780ad-253">Folgende Unterschiede sind jedoch zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="780ad-253">However, notice the following differences.</span></span>

    - <span data-ttu-id="780ad-254">Die Ergebnisse treten nicht alle gleichzeitig auf, nachdem die Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="780ad-254">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="780ad-255">Beispielsweise enthalten beide Programme eine Zeile in `startButton_Click`, die das Textfeld löscht.</span><span class="sxs-lookup"><span data-stu-id="780ad-255">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="780ad-256">Es ist vorgesehen, das Textfeld zwischen zwei Ausführungen zu löschen, wenn Sie die Schaltfläche **Start** ein zweites Mal auswählen, nachdem ein Ergebnissatz angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="780ad-256">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="780ad-257">In der synchronen Version wird das Textfeld unmittelbar vor der zweiten Anzeige des Zählers gelöscht, wenn die Downloads abgeschlossen sind und der UI-Thread für die Verarbeitung anderer Aktionen frei ist.</span><span class="sxs-lookup"><span data-stu-id="780ad-257">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="780ad-258">In der asynchronen Version wird das Textfeld unmittelbar gelöscht, nachdem Sie die Schaltfläche **Start** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="780ad-258">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>

    - <span data-ttu-id="780ad-259">Das Wichtigste ist jedoch, dass der UI-Thread nicht blockiert wird, während Downloads vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-259">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="780ad-260">Sie können das Fenster verschieben oder dessen Größe anpassen, während die Webressourcen heruntergeladen, gezählt und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="780ad-260">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="780ad-261">Wenn eine der Websites langsam ist oder nicht antwortet, können Sie den Vorgang abbrechen, indem Sie die Schaltfläche **Schließen** (das x im roten Feld in der oberen rechten Ecke) auswählen.</span><span class="sxs-lookup"><span data-stu-id="780ad-261">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a><span data-ttu-id="780ad-262">Ersetzen der geturlcontentsasync-Methode durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="780ad-262">Replace the GetURLContentsAsync method with a .NET Framework method</span></span>

1. <span data-ttu-id="780ad-263">Der .NET Framework bietet viele Async-Methoden, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="780ad-263">The .NET Framework provides many async methods that you can use.</span></span> <span data-ttu-id="780ad-264">Eine dieser Methoden, die- <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> Methode, erledigt genau das, was Sie für diese exemplarische Vorgehensweise benötigen.</span><span class="sxs-lookup"><span data-stu-id="780ad-264">One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough.</span></span> <span data-ttu-id="780ad-265">Sie können sie anstelle der `GetURLContentsAsync`-Methode verwenden, die Sie in einer vorherigen Vorgehensweise erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="780ad-265">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>

    <span data-ttu-id="780ad-266">Der erste Schritt besteht darin, ein- <xref:System.Net.Http.HttpClient> Objekt in der-Methode zu erstellen `SumPageSizesAsync` .</span><span class="sxs-lookup"><span data-stu-id="780ad-266">The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="780ad-267">Fügen Sie am Anfang der Methode die folgende Deklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="780ad-267">Add the following declaration at the start of the method.</span></span>

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. <span data-ttu-id="780ad-268">Ersetzen Sie in `SumPageSizesAsync,` den Aufruf zu Ihrer `GetURLContentsAsync`-Methode durch einen Aufruf zur Methode `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="780ad-268">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. <span data-ttu-id="780ad-269">Entfernen Sie die von Ihnen geschriebene `GetURLContentsAsync`-Methode, oder kommentieren Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="780ad-269">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>

4. <span data-ttu-id="780ad-270">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="780ad-270">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="780ad-271">Das Verhalten dieser Version des Projekts sollte mit dem Verhalten übereinstimmen, das in der Vorgehensweise „So testen Sie die asynchrone Lösung“ beschrieben wird, es sollte aber weniger Aufwand Ihrerseits nötig sein.</span><span class="sxs-lookup"><span data-stu-id="780ad-271">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>

## <a name="example"></a><span data-ttu-id="780ad-272">Beispiel</span><span class="sxs-lookup"><span data-stu-id="780ad-272">Example</span></span>

<span data-ttu-id="780ad-273">Im folgenden finden Sie das vollständige Beispiel für die konvertierte asynchrone Projekt Mappe, die die asynchrone- `GetURLContentsAsync` Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="780ad-273">The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method.</span></span> <span data-ttu-id="780ad-274">Beachten Sie, dass sie der ursprünglichen synchronen Lösung sehr stark ähnelt.</span><span class="sxs-lookup"><span data-stu-id="780ad-274">Notice that it strongly resembles the original, synchronous solution.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

<span data-ttu-id="780ad-275">Der folgende Code umfasst das vollständige Beispiel der Lösung, die die `HttpClient`-Methode `GetByteArrayAsync` verwendet.</span><span class="sxs-lookup"><span data-stu-id="780ad-275">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a><span data-ttu-id="780ad-276">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="780ad-276">See also</span></span>

- [<span data-ttu-id="780ad-277">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic) (Asynchrones Beispiel: Webzugriff – Exemplarische Vorgehensweise (C# und Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="780ad-277">Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [<span data-ttu-id="780ad-278">Erwartungs Operator</span><span class="sxs-lookup"><span data-stu-id="780ad-278">Await Operator</span></span>](../../../language-reference/operators/await-operator.md)
- [<span data-ttu-id="780ad-279">Async</span><span class="sxs-lookup"><span data-stu-id="780ad-279">Async</span></span>](../../../language-reference/modifiers/async.md)
- [<span data-ttu-id="780ad-280">Asynchronous Programming with Async and Await (Visual Basic) (Asynchrone Programmierung mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="780ad-280">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="780ad-281">[Async Return Types (Visual Basic)](async-return-types.md) (Asynchrone Rückgabetypen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="780ad-281">[Async Return Types (Visual Basic)](async-return-types.md)</span></span>
- [<span data-ttu-id="780ad-282">Aufgabenbasiertes asynchrones Programmieren (TAP)</span><span class="sxs-lookup"><span data-stu-id="780ad-282">Task-based Asynchronous Programming (TAP)</span></span>](https://www.microsoft.com/download/details.aspx?id=19957)
- <span data-ttu-id="780ad-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="780ad-283">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
- <span data-ttu-id="780ad-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Gewusst wie: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="780ad-284">[How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
