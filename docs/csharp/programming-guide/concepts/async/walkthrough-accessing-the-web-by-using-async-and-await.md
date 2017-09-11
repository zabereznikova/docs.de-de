---
title: 'Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7c03cad060e2ba459277c28f929df88be70e4044
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a><span data-ttu-id="a279d-102">Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)</span><span class="sxs-lookup"><span data-stu-id="a279d-102">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>
<span data-ttu-id="a279d-103">Sie können asynchrone Programme mit den Funktionen „Async/Await“ einfacher und intuitiver schreiben.</span><span class="sxs-lookup"><span data-stu-id="a279d-103">You can write asynchronous programs more easily and intuitively by using async/await features.</span></span> <span data-ttu-id="a279d-104">Sie können asynchronen Code schreiben, der wie synchroner Code aussieht und veranlassen, dass der Compiler die komplizierten Rückruffunktionen und Fortsetzungen verarbeitet, die durch den asynchronen Code für gewöhnlich verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="a279d-105">Weitere Informationen über die Funktion „Async“ finden Sie unter [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](../../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a279d-105">For more information about the Async feature, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="a279d-106">Diese exemplarische Vorgehensweise beginnt mit einer synchronen WPF-Anwendung (Windows Presentation Foundation), die die Anzahl der Bytes in einer Liste von Websites summiert.</span><span class="sxs-lookup"><span data-stu-id="a279d-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="a279d-107">In der exemplarischen Vorgehensweise wird die Anwendung dann mithilfe der neuen Funktionen in eine asynchrone Lösung umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="a279d-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="a279d-108">Wenn Sie die Anwendungen nicht selbst erstellen möchten, können Sie das „Thema mit einem asynchronen Beispiel für die exemplarische Vorgehensweise für den Internetzugriff (C# und Visual Basic)“ in englischer Sprache über [Entwickler-Codebeispiele](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a279d-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="a279d-109">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="a279d-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="a279d-110">So erstellen Sie eine WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a279d-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="a279d-111">So entwerfen Sie ein einfaches WPF-MainWindow</span><span class="sxs-lookup"><span data-stu-id="a279d-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="a279d-112">So fügen Sie einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="a279d-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="a279d-113">So fügen Sie erforderliche using-Anweisungen hinzu</span><span class="sxs-lookup"><span data-stu-id="a279d-113">To add necessary using directives</span></span>](#usingDir)  
  
-   [<span data-ttu-id="a279d-114">So erstellen Sie eine synchrone Anwendung</span><span class="sxs-lookup"><span data-stu-id="a279d-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="a279d-115">So testen Sie die synchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="a279d-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="a279d-116">So konvertieren Sie „GetURLContents“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="a279d-117">So konvertieren Sie „SumPageSizes“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="a279d-118">So konvertieren Sie „startButton_Click“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="a279d-119">So testen Sie die asynchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="a279d-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="a279d-120">So ersetzen Sie die Methode „GetURLContentsAsync“ durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="a279d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a279d-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="a279d-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a279d-122">Prerequisites</span></span>  
 <span data-ttu-id="a279d-123">Visual Studio 2012 oder höher muss auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="a279d-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="a279d-124">Weitere Informationen finden Sie auf der [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkId=235233).</span><span class="sxs-lookup"><span data-stu-id="a279d-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="a279d-125"><a name="CreateWPFApp"></a> So erstellen Sie eine WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a279d-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="a279d-126">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a279d-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a279d-127">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="a279d-128">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a279d-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a279d-129">Wählen Sie im Bereich **Installierte Vorlagen** den Eintrag Visual C# aus, und wählen Sie dann in der Liste der Projekttypen **WPF-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-129">In the **Installed Templates** pane, choose Visual C#, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="a279d-130">Geben Sie im Textfeld **Name** `AsyncExampleWPF` ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="a279d-131">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a279d-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="a279d-132"><a name="MainWindow"></a> So entwerfen Sie ein einfaches WPF-MainWindow</span><span class="sxs-lookup"><span data-stu-id="a279d-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="a279d-133">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="a279d-134">Wenn das Fenster **Toolbox** nicht sichtbar ist, öffnen Sie das Menü **Ansicht**, und wählen Sie dann **Toolbox** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="a279d-135">Fügen Sie dem Fenster **MainWindow** ein **Button**-Steuerelement und ein **TextBox**-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="a279d-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="a279d-136">Markieren Sie das **TextBox**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="a279d-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="a279d-137">Legen Sie die Eigenschaft **Name** auf `resultsTextBox` fest.</span><span class="sxs-lookup"><span data-stu-id="a279d-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="a279d-138">Legen Sie die Eigenschaft **Height** auf „250“ fest.</span><span class="sxs-lookup"><span data-stu-id="a279d-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="a279d-139">Legen Sie die Eigenschaft **Width** auf „500“ fest.</span><span class="sxs-lookup"><span data-stu-id="a279d-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="a279d-140">Geben Sie auf der Registerkarte **Text** eine Festbreitenschriftart wie Lucida Console oder Global Monospace an.</span><span class="sxs-lookup"><span data-stu-id="a279d-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="a279d-141">Markieren Sie das **Button**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="a279d-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="a279d-142">Legen Sie die Eigenschaft **Name** auf `startButton` fest.</span><span class="sxs-lookup"><span data-stu-id="a279d-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="a279d-143">Ändern Sie den Wert der Eigenschaft **Content** von **Button** zu **Start**.</span><span class="sxs-lookup"><span data-stu-id="a279d-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="a279d-144">Positionieren Sie das Textfeld und die Schaltfläche so, dass beide im Fenster **MainWindow** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="a279d-145">Weitere Informationen über den WPF-XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a279d-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="a279d-146"><a name="AddRef"></a> So fügen Sie einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="a279d-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="a279d-147">Markieren Sie im **Projektmappen-Explorer** den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a279d-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="a279d-148">Wählen Sie in der Menüleiste die Optionen **Projekt** und **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="a279d-149">Das Dialogfeld **Verweis-Manager** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a279d-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="a279d-150">Stellen Sie oben im Dialogfeld sicher, dass Ihr Projekt auf .NET Framework 4.5 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="a279d-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="a279d-151">Wählen Sie im Bereich **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="a279d-152">Aktivieren Sie in der Liste der Namen das Kontrollkästchen **System.Net.Http**.</span><span class="sxs-lookup"><span data-stu-id="a279d-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="a279d-153">Wählen Sie die Schaltfläche **OK** aus, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a279d-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="a279d-154"><a name="usingDir"></a> So fügen Sie erforderliche using-Anweisungen hinzu</span><span class="sxs-lookup"><span data-stu-id="a279d-154"><a name="usingDir"></a> To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="a279d-155">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="a279d-156">Fügen Sie die folgenden `using`-Anweisungen am Anfang der Codedatei ein, wenn sie noch nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a279d-156">Add the following `using` directives at the top of the code file if they’re not already present.</span></span>  
  
    ```csharp  
    using System.Net.Http;  
    using System.Net;  
    using System.IO;  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="a279d-157"><a name="synchronous"></a> So erstellen Sie eine synchrone Anwendung</span><span class="sxs-lookup"><span data-stu-id="a279d-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="a279d-158">Doppelklicken Sie im Entwurfsfenster „MainWindow.xaml“ auf die Schaltfläche **Start**, um den `startButton_Click`-Ereignishandler in „MainWindow.xaml.cs“ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a279d-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="a279d-159">Kopieren Sie in „MainWindow.xaml.cs“ den folgenden Code in den Textteil von `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="a279d-159">In MainWindow.xaml.cs, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    SumPageSizes();  
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";  
    ```  
  
     <span data-ttu-id="a279d-160">Der Code ruft die Methode `SumPageSizes` auf, die die Anwendung steuert und zeigt eine Meldung an, wenn das Steuerelement zu `startButton_Click` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="a279d-161">Der Code für die synchrone Lösung enthält die folgenden vier Methoden:</span><span class="sxs-lookup"><span data-stu-id="a279d-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="a279d-162">`SumPageSizes`. Enthält eine Liste von Webseiten-URLs aus `SetUpURLList` und ruft dann `GetURLContents` und `DisplayResults` auf, um jede URL zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a279d-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="a279d-163">`SetUpURLList`. Erstellt und gibt eine Liste der Webadressen zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="a279d-164">`GetURLContents`. Lädt Inhalte jeder Website herunter und gibt die Inhalte als ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="a279d-165">`DisplayResults`. Zeigt die Anzahl der Bytes im Bytearray für jede URL an.</span><span class="sxs-lookup"><span data-stu-id="a279d-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="a279d-166">Kopieren Sie die folgenden vier Methoden, und fügen Sie sie dann unter dem `startButton_Click`-Ereignishandler in „MainWindow.xaml.cs“ ein:</span><span class="sxs-lookup"><span data-stu-id="a279d-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.cs:</span></span>  
  
    ```csharp  
    private void SumPageSizes()  
    {  
        // Make a list of web addresses.  
        List<string> urlList = SetUpURLList();   
  
        var total = 0;  
        foreach (var url in urlList)  
        {  
            // GetURLContents returns the contents of url as a byte array.  
            byte[] urlContents = GetURLContents(url);  
  
            DisplayResults(url, urlContents);  
  
            // Update the total.  
            total += urlContents.Length;  
        }  
  
        // Display the total count for all of the web addresses.  
        resultsTextBox.Text +=   
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
  
    private List<string> SetUpURLList()  
    {  
        var urls = new List<string>   
        {   
            "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
            "http://msdn.microsoft.com",  
            "http://msdn.microsoft.com/library/hh290136.aspx",  
            "http://msdn.microsoft.com/library/ee256749.aspx",  
            "http://msdn.microsoft.com/library/hh290138.aspx",  
            "http://msdn.microsoft.com/library/hh290140.aspx",  
            "http://msdn.microsoft.com/library/dd470362.aspx",  
            "http://msdn.microsoft.com/library/aa578028.aspx",  
            "http://msdn.microsoft.com/library/ms404677.aspx",  
            "http://msdn.microsoft.com/library/ff730837.aspx"  
        };  
        return urls;  
    }  
  
    private byte[] GetURLContents(string url)  
    {  
        // The downloaded resource ends up in the variable named content.  
        var content = new MemoryStream();  
  
        // Initialize an HttpWebRequest for the current URL.  
        var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
        // Send the request to the Internet resource and wait for  
        // the response.  
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        using (WebResponse response = webReq.GetResponse())  
        {  
            // Get the data stream that is associated with the specified URL.  
            using (Stream responseStream = response.GetResponseStream())  
            {  
                // Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content);  
            }  
        }  
  
        // Return the result as a byte array.  
        return content.ToArray();  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format   
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <span data-ttu-id="a279d-167"><a name="testSynch"></a> So testen Sie die synchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="a279d-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="a279d-168">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="a279d-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a279d-169">Die Ausgabe sollte der folgenden Liste gleichen.</span><span class="sxs-lookup"><span data-stu-id="a279d-169">Output that resembles the following list should appear.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="a279d-170">Beachten Sie, dass es ein paar Sekunden dauert, bis die Zahlen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="a279d-171">Während dieser Zeit ist der Benutzeroberflächenthread blockiert, während auf das Herunterladen von angeforderten Ressourcen gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="a279d-172">Daher können Sie das Anzeigefenster weder verschieben, maximieren, minimieren noch schließen, nachdem Sie die Schaltfläche **Start** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a279d-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="a279d-173">Diese Bemühungen sind nicht erfolgreich, bis der Bytezähler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="a279d-174">Wenn eine Website nicht antwortet, erhalten Sie keinen Hinweis darüber, welche Site fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="a279d-175">Es ist sogar schwierig, mit dem Warten aufzuhören und das Programm zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a279d-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="a279d-176"><a name="GetURLContents"></a> So konvertieren Sie „GetURLContents“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a279d-177">Für das Konvertieren der synchronen Projektmappe in eine asynchrone Projektmappe empfiehlt es sich, in `GetURLContents` zu beginnen, da die Aufrufe der <xref:System.Net.HttpWebRequest>-Methode <xref:System.Net.HttpWebRequest.GetResponse%2A> und der <xref:System.IO.Stream>-Methode <xref:System.IO.Stream.CopyTo%2A> dort erfolgen, wo die Anwendung auf das Web zugreift.</span><span class="sxs-lookup"><span data-stu-id="a279d-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="a279d-178">.NET Framework erleichtert die Konvertierung, indem asynchrone Versionen beider Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="a279d-179">Weitere Informationen über die in `GetURLContents` verwendeten Methoden finden Sie unter <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="a279d-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a279d-180">Beim Befolgen der Schritte in dieser exemplarischen Vorgehensweise treten verschiedene Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a279d-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="a279d-181">Sie können diese ignorieren und mit der exemplarischen Vorgehensweise fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a279d-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="a279d-182">Ändern Sie die Methode, die aufgerufen wird, in der dritten Zeile von `GetURLContents` von `GetResponse` zur asynchronen, aufgabenbasierten <xref:System.Net.WebRequest.GetResponseAsync%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="a279d-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```csharp  
    using (WebResponse response = webReq.GetResponseAsync())  
    ```  
  
2.  <span data-ttu-id="a279d-183">`GetResponseAsync` gibt einen Wert vom Typ <xref:System.Threading.Tasks.Task%601> zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="a279d-184">In diesem Fall weist die *Aufgabenrückgabevariable*, `TResult`, den Typ <xref:System.Net.WebResponse> auf.</span><span class="sxs-lookup"><span data-stu-id="a279d-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="a279d-185">Mit dieser Aufgabe soll ein tatsächliches `WebResponse`-Objekt erstellt werden, nachdem die angeforderten Daten heruntergeladen und das Ausführen der Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a279d-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="a279d-186">Wenden Sie analog zur Darstellung im folgenden Code zum Abrufen des `WebResponse`-Werts aus der Aufgabe einen [await](../../../../csharp/language-reference/keywords/await.md)-Operator für den Aufruf von `GetResponseAsync` an.</span><span class="sxs-lookup"><span data-stu-id="a279d-186">To retrieve the `WebResponse` value from the task, apply an [await](../../../../csharp/language-reference/keywords/await.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
    ```csharp  
    using (WebResponse response = await webReq.GetResponseAsync())  
    ```  
  
     <span data-ttu-id="a279d-187">Der `await`-Operator hält die Ausführung der aktuellen Methode `GetURLContents` an, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-187">The `await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="a279d-188">In der Zwischenzeit kehrt die Steuerung zum Aufrufer der aktuellen Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-188">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="a279d-189">In diesem Beispiel lautet die aktuelle Methode `GetURLContents`, und der Aufrufer ist `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="a279d-189">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="a279d-190">Wenn die Aufgabe abgeschlossen ist, wird das zugesicherte `WebResponse`-Objekt als Wert der erwarteten Aufgabe erstellt und zur Variable `response` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a279d-190">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     <span data-ttu-id="a279d-191">Die vorherige Anweisung kann in die folgenden zwei Anweisungen getrennt werden, um zu verdeutlichen, was geschieht.</span><span class="sxs-lookup"><span data-stu-id="a279d-191">The previous statement can be separated into the following two statements to clarify what happens.</span></span>  
  
    ```csharp  
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
    //using (WebResponse response = await responseTask)  
    ```  
  
     <span data-ttu-id="a279d-192">Durch den Aufruf von `webReq.GetResponseAsync` wird `Task(Of WebResponse)` oder `Task<WebResponse>` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a279d-192">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="a279d-193">Anschließend wird ein await-Operator auf die Aufgabe angewendet, um den `WebResponse`-Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a279d-193">Then an await operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     <span data-ttu-id="a279d-194">Wenn Ihre asynchrone Methode Aktionen vornehmen muss, die nicht von der Fertigstellung der Aufgabe abhängen, kann die Methode diese Aktionen zwischen zwei Anweisungen fortsetzen, und zwar nach dem Aufruf der asynchronen Methode und vor dem Anwenden des `await`-Operators.</span><span class="sxs-lookup"><span data-stu-id="a279d-194">If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the `await` operator is applied.</span></span> <span data-ttu-id="a279d-195">Beispiele finden Sie unter [How to: Make Multiple Web Requests in Parallel by Using async and await (C#) (Vorgehensweise: Gleichzeitiges Erstellen von mehreren Webanforderungen mit „Async“ und „Await“ (C#))](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) und [Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="a279d-195">For examples, see [How to: Make Multiple Web Requests in Parallel by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
3.  <span data-ttu-id="a279d-196">Da Sie den Operator `await` im vorherigen Schritt hinzugefügt haben, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a279d-196">Because you added the `await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="a279d-197">Der Operator kann nur in Methoden verwendet werden, die mit dem Modifizierer [async](../../../../csharp/language-reference/keywords/async.md) markiert sind.</span><span class="sxs-lookup"><span data-stu-id="a279d-197">The operator can be used only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="a279d-198">Ignorieren Sie den Fehler, während Sie die Konvertierungsschritte zum Ersetzen des Aufrufs von `CopyTo` mit einem Aufruf von `CopyToAsync` wiederholen.</span><span class="sxs-lookup"><span data-stu-id="a279d-198">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="a279d-199">Ändern Sie den Namen der Methode, die für <xref:System.IO.Stream.CopyToAsync%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-199">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="a279d-200">Die Methode `CopyTo` oder `CopyToAsync` kopiert Bytes zu ihrem Argument `content` und gibt keinen sinnvollen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-200">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="a279d-201">In der synchronen Version ist der Aufruf von `CopyTo` eine einfache Anweisung, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a279d-201">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="a279d-202">Die asynchrone Version `CopyToAsync` gibt ein <xref:System.Threading.Tasks.Task> zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-202">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="a279d-203">Die Aufgabe funktioniert wie „Task(void)“ und ermöglicht, dass auf die Methode gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-203">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="a279d-204">Wenden Sie `Await` oder `await` auf den Aufruf von `CopyToAsync` an, wie dies im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-204">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
        ```csharp  
        await responseStream.CopyToAsync(content);  
        ```  
  
         <span data-ttu-id="a279d-205">Die vorherige Anweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="a279d-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
        ```csharp  
        // CopyToAsync returns a Task, not a Task<T>.  
        //Task copyTask = responseStream.CopyToAsync(content);  
  
        // When copyTask is completed, content contains a copy of  
        // responseStream.  
        //await copyTask;  
        ```  
  
4.  <span data-ttu-id="a279d-206">Somit muss nur noch die Methodensignatur in `GetURLContents` angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-206">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="a279d-207">Der `await`-Operator kann nur in Methoden verwendet werden, die mit dem Modifizierer [async](../../../../csharp/language-reference/keywords/async.md) markiert sind.</span><span class="sxs-lookup"><span data-stu-id="a279d-207">You can use the `await` operator only in methods that are marked with the [async](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="a279d-208">Fügen Sie den Modifizierer hinzu, um die Methode als eine *async*-Methode zu markieren, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a279d-208">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
    ```csharp  
    private async byte[] GetURLContents(string url)  
    ```  
  
5.  <span data-ttu-id="a279d-209">Der Rückgabetype einer async-Methode kann nur <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> oder `void` in C# sein.</span><span class="sxs-lookup"><span data-stu-id="a279d-209">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `void` in C#.</span></span> <span data-ttu-id="a279d-210">Für gewöhnlich wird ein Rückgabetyp `void` nur in einem asynchronen Ereignishandler verwendet, bei dem `void` erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-210">Typically, a return type of `void` is used only in an async event handler, where `void` is required.</span></span> <span data-ttu-id="a279d-211">In anderen Fällen verwenden Sie `Task(T)`, wenn die abgeschlossene Methode eine [return](../../../../csharp/language-reference/keywords/return.md)-Anweisung aufweist, die einen Wert vom Typ T zurückgibt. Verwenden Sie `Task`, wenn die abgeschlossene Methode keinen sinnvollen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a279d-211">In other cases, you use `Task(T)` if the completed method has a [return](../../../../csharp/language-reference/keywords/return.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span> <span data-ttu-id="a279d-212">Sie können sich den `Task`-Rückgabetyp wie „Task(void)“ vorstellen.</span><span class="sxs-lookup"><span data-stu-id="a279d-212">You can think of the `Task` return type as meaning "Task(void)."</span></span>  
  
     <span data-ttu-id="a279d-213">Weitere Informationen finden Sie unter [Async Return Types (C#) (Asynchrone Rückgabetypen (C#))](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="a279d-213">For more information, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="a279d-214">Die Methode `GetURLContents` verfügt über eine return-Anweisung, und die Anweisung gibt ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-214">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="a279d-215">Daher ist der Rückgabetyp der der asynchronen Version „Task(T)“, wobei „T“ ein Bytearray ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-215">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="a279d-216">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="a279d-216">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="a279d-217">Ändern Sie den Rückgabetyp zu `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="a279d-217">Change the return type to `Task<byte[]>`.</span></span>  
  
    -   <span data-ttu-id="a279d-218">Asynchrone Methoden verfügen gemäß der Konvention über Namen, die auf „Async“ enden. Benennen Sie also die Methode `GetURLContentsAsync` um.</span><span class="sxs-lookup"><span data-stu-id="a279d-218">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="a279d-219">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a279d-219">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task<byte[]> GetURLContentsAsync(string url)  
    ```  
  
     <span data-ttu-id="a279d-220">Mit diesen wenigen Änderungen ist die Konvertierung von `GetURLContents` zu einer asynchronen Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a279d-220">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="a279d-221"><a name="SumPageSizes"></a> So konvertieren Sie „SumPageSizes“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-221"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a279d-222">Wiederholen Sie die Schritte des vorherigen Verfahrens für `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="a279d-222">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="a279d-223">Ändern Sie zunächst den Aufruf von `GetURLContents` zu einem asynchronen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="a279d-223">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="a279d-224">Ändern Sie den Namen der Methode, die aufgerufen wird, von `GetURLContents` zu `GetURLContentsAsync`, sofern Sie dies nicht bereits getan haben.</span><span class="sxs-lookup"><span data-stu-id="a279d-224">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="a279d-225">Wenden Sie `await` auf die Aufgabe an, die durch `GetURLContentsAsync` zurückgegeben wird, um den Bytearraywert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a279d-225">Apply `await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="a279d-226">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a279d-226">The following code shows these changes.</span></span>  
  
    ```csharp  
    byte[] urlContents = await GetURLContentsAsync(url);  
    ```  
  
     <span data-ttu-id="a279d-227">Die vorherige Zuweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="a279d-227">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```csharp  
    // GetURLContentsAsync returns a Task<T>. At completion, the task  
    // produces a byte array.  
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
    //byte[] urlContents = await getContentsTask;  
    ```  
  
2.  <span data-ttu-id="a279d-228">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="a279d-228">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="a279d-229">Markieren Sie die Methode mit dem Modifizierer `async`.</span><span class="sxs-lookup"><span data-stu-id="a279d-229">Mark the method with the `async` modifier.</span></span>  
  
    -   <span data-ttu-id="a279d-230">Fügen Sie dem Methodennamen „Async“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a279d-230">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="a279d-231">Es ist dieses Mal keine Aufgabenrückgabevariable „T“ vorhanden, da `SumPageSizesAsync` keinen Wert für „T“ zurückgibt. (Die Methode weist keine `return`-Anweisung auf.) Die Methode muss jedoch eine `Task` zurückgeben, die awaitable ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-231">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="a279d-232">Ändern Sie daher den Rückgabetyp der Methode von `void` in `Task`.</span><span class="sxs-lookup"><span data-stu-id="a279d-232">Therefore, change the return type of the method from `void` to `Task`.</span></span>  
  
     <span data-ttu-id="a279d-233">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a279d-233">The following code shows these changes.</span></span>  
  
    ```csharp  
    private async Task SumPageSizesAsync()  
    ```  
  
     <span data-ttu-id="a279d-234">Die Konvertierung von `SumPageSizes` zu `SumPageSizesAsync` ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a279d-234">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="a279d-235"><a name="startButton"></a> So konvertieren Sie „startButton_Click“ in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-235"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="a279d-236">Ändern Sie im Ereignishandler den Namen der aufgerufenen Methode von `SumPageSizes` zu `SumPageSizesAsync`, sofern Sie dies nicht bereits vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="a279d-236">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="a279d-237">Da es sich bei `SumPageSizesAsync` um eine asynchrone Methode handelt, ändern Sie den Code im Ereignishandler, um auf das Ergebnis zu warten.</span><span class="sxs-lookup"><span data-stu-id="a279d-237">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="a279d-238">Der Aufruf von `SumPageSizesAsync` spiegelt den Aufruf von `CopyToAsync` in `GetURLContentsAsync` wider.</span><span class="sxs-lookup"><span data-stu-id="a279d-238">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="a279d-239">Der Aufruf gibt eine `Task` und keine `Task(T)` zurück.</span><span class="sxs-lookup"><span data-stu-id="a279d-239">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="a279d-240">Analog zu den vorherigen Vorgehensweisen können Sie den Aufruf mithilfe von einer oder zwei Anweisungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a279d-240">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="a279d-241">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a279d-241">The following code shows these changes.</span></span>  
  
    ```csharp  
    // One-step async call.  
    await SumPageSizesAsync();  
  
    // Two-step async call.  
    //Task sumTask = SumPageSizesAsync();  
    //await sumTask;  
    ```  
  
3.  <span data-ttu-id="a279d-242">Um den versehentlichen Neustart des Vorgangs zu verhindern, fügen Sie oben in `startButton_Click` die folgende Anweisung ein, um die Schaltfläche **Start** zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a279d-242">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```csharp  
    // Disable the button until the operation is complete.  
    startButton.IsEnabled = false;  
    ```  
  
     <span data-ttu-id="a279d-243">Sie können die Schaltfläche am Ende des Ereignishandlers wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a279d-243">You can reenable the button at the end of the event handler.</span></span>  
  
    ```csharp  
    // Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = true;  
    ```  
  
     <span data-ttu-id="a279d-244">Weitere Informationen zum erneuten Eintreten finden Sie unter [Handling Reentrancy in Async Apps (C#) (Ablauf des erneuten Eintretens in asynchronen Anwendungen (C#))](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a279d-244">For more information about reentrancy, see [Handling Reentrancy in Async Apps (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="a279d-245">Fügen Sie der Deklaration abschließend den Modifizierer `async` hinzu, sodass der Ereignishandler auf `SumPagSizesAsync` warten kann.</span><span class="sxs-lookup"><span data-stu-id="a279d-245">Finally, add the `async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```csharp  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    ```  
  
     <span data-ttu-id="a279d-246">In der Regel werden die Namen der Ereignishandler nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a279d-246">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="a279d-247">Der Rückgabetyp wird nicht zu `Task` geändert, da Ereignishandler `void` zurückgeben müssen.</span><span class="sxs-lookup"><span data-stu-id="a279d-247">The return type isn’t changed to `Task` because event handlers must return `void`.</span></span>  
  
     <span data-ttu-id="a279d-248">Die Konvertierung des Projekts von der synchronen zu asynchronen Verarbeitung ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a279d-248">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="a279d-249"><a name="testAsynch"></a> So testen Sie die asynchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="a279d-249"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="a279d-250">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="a279d-250">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="a279d-251">Es sollte eine Ausgabe angezeigt werden, die der Ausgabe der synchronen Lösung gleicht.</span><span class="sxs-lookup"><span data-stu-id="a279d-251">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="a279d-252">Folgende Unterschiede sind jedoch zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="a279d-252">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="a279d-253">Die Ergebnisse treten nicht alle gleichzeitig auf, nachdem die Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a279d-253">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="a279d-254">Beispielsweise enthalten beide Programme eine Zeile in `startButton_Click`, die das Textfeld löscht.</span><span class="sxs-lookup"><span data-stu-id="a279d-254">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="a279d-255">Es ist vorgesehen, das Textfeld zwischen zwei Ausführungen zu löschen, wenn Sie die Schaltfläche **Start** ein zweites Mal auswählen, nachdem ein Ergebnissatz angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="a279d-255">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="a279d-256">In der synchronen Version wird das Textfeld unmittelbar vor der zweiten Anzeige des Zählers gelöscht, wenn die Downloads abgeschlossen sind und der UI-Thread für die Verarbeitung anderer Aktionen frei ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-256">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="a279d-257">In der asynchronen Version wird das Textfeld unmittelbar gelöscht, nachdem Sie die Schaltfläche **Start** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a279d-257">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="a279d-258">Das Wichtigste ist jedoch, dass der UI-Thread nicht blockiert wird, während Downloads vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-258">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="a279d-259">Sie können das Fenster verschieben oder dessen Größe anpassen, während die Webressourcen heruntergeladen, gezählt und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a279d-259">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="a279d-260">Wenn eine der Websites langsam ist oder nicht antwortet, können Sie den Vorgang abbrechen, indem Sie die Schaltfläche **Schließen** (das x im roten Feld in der oberen rechten Ecke) auswählen.</span><span class="sxs-lookup"><span data-stu-id="a279d-260">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="a279d-261"><a name="GetURLContentsAsync"></a> So ersetzen Sie die Methode „GetURLContentsAsync“ durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="a279d-261"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="a279d-262">.NET Framework 4.5 bietet viele asynchrone Methoden, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a279d-262">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="a279d-263">Eine davon, die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> erfüllt genau das, was in dieser exemplarischen Vorgehensweise nötig ist.</span><span class="sxs-lookup"><span data-stu-id="a279d-263">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="a279d-264">Sie können sie anstelle der `GetURLContentsAsync`-Methode verwenden, die Sie in einer vorherigen Vorgehensweise erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a279d-264">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="a279d-265">Der erste Schritt besteht darin, ein `HttpClient`-Objekt in der Methode `SumPageSizesAsync` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a279d-265">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="a279d-266">Fügen Sie am Anfang der Methode die folgende Deklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="a279d-266">Add the following declaration at the start of the method.</span></span>  
  
    ```csharp  
    // Declare an HttpClient object and increase the buffer size. The  
    // default buffer size is 65,536.  
    HttpClient client =  
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
    ```  
  
2.  <span data-ttu-id="a279d-267">Ersetzen Sie in `SumPageSizesAsync,` den Aufruf zu Ihrer `GetURLContentsAsync`-Methode durch einen Aufruf zur Methode `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="a279d-267">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```csharp  
    byte[] urlContents = await client.GetByteArrayAsync(url);  
    ```  
  
3.  <span data-ttu-id="a279d-268">Entfernen Sie die von Ihnen geschriebene `GetURLContentsAsync`-Methode, oder kommentieren Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="a279d-268">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="a279d-269">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="a279d-269">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a279d-270">Das Verhalten dieser Version des Projekts sollte mit dem Verhalten übereinstimmen, das in der Vorgehensweise „So testen Sie die asynchrone Lösung“ beschrieben wird, es sollte aber weniger Aufwand Ihrerseits nötig sein.</span><span class="sxs-lookup"><span data-stu-id="a279d-270">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="a279d-271"><a name="BKMK_CompleteCodeExamples"></a> Beispiel</span><span class="sxs-lookup"><span data-stu-id="a279d-271"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="a279d-272">Der folgende Code enthält das vollständige Beispiel der Konvertierung von einer synchronen zu einer asynchronen Lösung mithilfe der von Ihnen geschriebenen asynchronen `GetURLContentsAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a279d-272">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="a279d-273">Beachten Sie, dass sie der ursprünglichen synchronen Lösung sehr stark ähnelt.</span><span class="sxs-lookup"><span data-stu-id="a279d-273">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            resultsTextBox.Clear();  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            // Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                byte[] urlContents = await GetURLContentsAsync(url);  
  
                // The previous line abbreviates the following two assignment statements.  
  
                // GetURLContentsAsync returns a Task<T>. At completion, the task  
                // produces a byte array.  
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.            
                total += urlContents.Length;  
            }  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        private async Task<byte[]> GetURLContentsAsync(string url)  
        {  
            // The downloaded resource ends up in the variable named content.  
            var content = new MemoryStream();  
  
            // Initialize an HttpWebRequest for the current URL.  
            var webReq = (HttpWebRequest)WebRequest.Create(url);  
  
            // Send the request to the Internet resource and wait for  
            // the response.                  
            using (WebResponse response = await webReq.GetResponseAsync())  
  
            // The previous statement abbreviates the following two statements.  
  
            //Task<WebResponse> responseTask = webReq.GetResponseAsync();  
            //using (WebResponse response = await responseTask)  
            {  
                // Get the data stream that is associated with the specified url.  
                using (Stream responseStream = response.GetResponseStream())  
                {  
                    // Read the bytes in responseStream and copy them to content.   
                    await responseStream.CopyToAsync(content);  
  
                    // The previous statement abbreviates the following two statements.  
  
                    // CopyToAsync returns a Task, not a Task<T>.  
                    //Task copyTask = responseStream.CopyToAsync(content);  
  
                    // When copyTask is completed, content contains a copy of  
                    // responseStream.  
                    //await copyTask;  
                }  
            }  
            // Return the result as a byte array.  
            return content.ToArray();  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="a279d-274">Der folgende Code umfasst das vollständige Beispiel der Lösung, die die `HttpClient`-Methode `GetByteArrayAsync` verwendet.</span><span class="sxs-lookup"><span data-stu-id="a279d-274">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
using System.IO;  
using System.Net;  
  
namespace AsyncExampleWPF  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
  
            // Disable the button until the operation is complete.  
            startButton.IsEnabled = false;  
  
            // One-step async call.  
            await SumPageSizesAsync();  
  
            //// Two-step async call.  
            //Task sumTask = SumPageSizesAsync();  
            //await sumTask;  
  
            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";  
  
            // Reenable the button in case you want to run the operation again.  
            startButton.IsEnabled = true;  
        }  
  
        private async Task SumPageSizesAsync()  
        {  
            // Declare an HttpClient object and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            var total = 0;  
  
            foreach (var url in urlList)  
            {  
                // GetByteArrayAsync returns a task. At completion, the task  
                // produces a byte array.  
                byte[] urlContents = await client.GetByteArrayAsync(url);                 
  
                // The following two lines can replace the previous assignment statement.  
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);  
                //byte[] urlContents = await getContentsTask;  
  
                DisplayResults(url, urlContents);  
  
                // Update the total.  
                total += urlContents.Length;  
            }  
  
            // Display the total count for all of the websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a279d-275">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a279d-275">See Also</span></span>  
 <span data-ttu-id="a279d-276">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic) (Asynchrones Beispiel für die exemplarische Vorgehensweise für den Internetzugriff (C# und Visual Basic))](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="a279d-276">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
 <span data-ttu-id="a279d-277">[async](../../../../csharp/language-reference/keywords/async.md) </span><span class="sxs-lookup"><span data-stu-id="a279d-277">[async](../../../../csharp/language-reference/keywords/async.md) </span></span>  
 <span data-ttu-id="a279d-278">[await](../../../../csharp/language-reference/keywords/await.md) </span><span class="sxs-lookup"><span data-stu-id="a279d-278">[await](../../../../csharp/language-reference/keywords/await.md) </span></span>  
 <span data-ttu-id="a279d-279">[Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](../../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="a279d-279">[Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
 <span data-ttu-id="a279d-280">[Async Return Types (C#) (Asynchrone Rückgabetypen (C#))](../../../../csharp/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="a279d-280">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md) </span></span>  
 <span data-ttu-id="a279d-281">[Task-based Asynchronous Programming (TAP) (Aufgabenbasiertes asynchrones Programmieren (TAP))](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="a279d-281">[Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
 <span data-ttu-id="a279d-282">[How to: Extend the async Walkthrough by Using Task.WhenAll (C#) (Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#))](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="a279d-282">[How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
 [<span data-ttu-id="a279d-283">How to: Make Multiple Web Requests in Parallel by Using async and await (C#) (Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (C#))</span><span class="sxs-lookup"><span data-stu-id="a279d-283">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)

