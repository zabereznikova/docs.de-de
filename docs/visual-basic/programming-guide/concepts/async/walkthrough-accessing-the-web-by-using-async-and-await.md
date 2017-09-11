---
title: Zugreifen auf das Web mit Async und Await (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
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
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="d23b8-102">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d23b8-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="d23b8-103">Sie können asynchrone Programme mehr einfach und intuitiv schreiben, in eingeführten, Funktionen mit [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d23b8-103">You can write asynchronous programs more easily and intuitively by using features that were introduced in [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span></span> <span data-ttu-id="d23b8-104">Sie können asynchronen Code schreiben, der wie synchroner Code aussieht und veranlassen, dass der Compiler die komplizierten Rückruffunktionen und Fortsetzungen verarbeitet, die durch den asynchronen Code für gewöhnlich verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="d23b8-105">Weitere Informationen zum Feature "Async" finden Sie unter [asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="d23b8-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="d23b8-106">Diese exemplarische Vorgehensweise beginnt mit einer synchronen WPF-Anwendung (Windows Presentation Foundation), die die Anzahl der Bytes in einer Liste von Websites summiert.</span><span class="sxs-lookup"><span data-stu-id="d23b8-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="d23b8-107">In der exemplarischen Vorgehensweise wird die Anwendung dann mithilfe der neuen Funktionen in eine asynchrone Lösung umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="d23b8-108">Wenn Sie die Anwendung selbst erstellen möchten, können Sie herunterladen "Async-Beispiel: Zugreifen auf die Web-Exemplarische Vorgehensweise (C#- und Visual Basic)" von [Codebeispielen für Entwickler](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="d23b8-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="d23b8-109">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="d23b8-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="d23b8-110">Zum Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d23b8-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="d23b8-111">So entwerfen ein einfaches WPF-MainWindow</span><span class="sxs-lookup"><span data-stu-id="d23b8-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="d23b8-112">Einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="d23b8-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="d23b8-113">Erforderliche Imports-Anweisungen hinzu</span><span class="sxs-lookup"><span data-stu-id="d23b8-113">To add necessary Imports statements</span></span>](#ImportsState)  
  
-   [<span data-ttu-id="d23b8-114">Erstellen Sie eine synchrone Anwendung</span><span class="sxs-lookup"><span data-stu-id="d23b8-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="d23b8-115">So testen Sie die synchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="d23b8-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="d23b8-116">So konvertieren Sie GetURLContents in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="d23b8-117">So konvertieren Sie SumPageSizes in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="d23b8-118">So konvertieren Sie StartButton_Click in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="d23b8-119">So testen Sie die asynchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="d23b8-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="d23b8-120">Zum Ersetzen der Methode "geturlcontentsasync" durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="d23b8-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d23b8-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="d23b8-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="d23b8-122">Prerequisites</span></span>  
 <span data-ttu-id="d23b8-123">Visual Studio 2012 oder höher muss auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="d23b8-124">Weitere Informationen finden Sie unter der [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkId=235233).</span><span class="sxs-lookup"><span data-stu-id="d23b8-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="d23b8-125"><a name="CreateWPFApp"></a>Zum Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d23b8-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="d23b8-126">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d23b8-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d23b8-127">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="d23b8-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="d23b8-128">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d23b8-129">In der **installierte Vorlagen** Bereich Wählen Sie Visual Basic, und wählen Sie dann **WPF-Anwendung** aus der Liste der Projekttypen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="d23b8-130">In der **Namen** Text geben `AsyncExampleWPF`, und wählen Sie dann die **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d23b8-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="d23b8-131">Das neue Projekt wird im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d23b8-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="d23b8-132"><a name="MainWindow"></a>So entwerfen ein einfaches WPF-MainWindow</span><span class="sxs-lookup"><span data-stu-id="d23b8-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="d23b8-133">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="d23b8-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="d23b8-134">Wenn der **Toolbox** Fenster ist nicht sichtbar ist, öffnen Sie die **Ansicht** Menü, und wählen Sie dann **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="d23b8-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="d23b8-135">Hinzufügen einer **Schaltfläche** Steuerelement und ein **Textfeld** die Steuerung an die **MainWindow** Fenster.</span><span class="sxs-lookup"><span data-stu-id="d23b8-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="d23b8-136">Markieren Sie die **Textfeld** Steuerelement und klicken Sie in der **Eigenschaften** legen die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="d23b8-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="d23b8-137">Legen Sie die **Namen** -Eigenschaft `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="d23b8-138">Legen Sie die **Höhe** Eigenschaft auf 250.</span><span class="sxs-lookup"><span data-stu-id="d23b8-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="d23b8-139">Legen Sie die **Breite** Eigenschaft auf 500.</span><span class="sxs-lookup"><span data-stu-id="d23b8-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="d23b8-140">Auf der **Text** geben eine Festbreitenschriftart, z. B. Lucida Console oder globale Festbreitenschriftart.</span><span class="sxs-lookup"><span data-stu-id="d23b8-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="d23b8-141">Markieren Sie die **Schaltfläche** Steuerelement und klicken Sie in der **Eigenschaften** legen die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="d23b8-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="d23b8-142">Legen Sie die **Namen** -Eigenschaft `startButton`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="d23b8-143">Ändern Sie den Wert von der **Content** Eigenschaft von **Schaltfläche** auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="d23b8-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="d23b8-144">Das Textfeld und die Schaltfläche positionieren, sodass beide, in angezeigt der **MainWindow** Fenster.</span><span class="sxs-lookup"><span data-stu-id="d23b8-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="d23b8-145">Weitere Informationen über den WPF-XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit XAML-Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d23b8-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="d23b8-146"><a name="AddRef"></a>Einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="d23b8-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="d23b8-147">In **Projektmappen-Explorer**, markieren Sie den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="d23b8-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="d23b8-148">Wählen Sie auf der Menüleiste **Projekt**, **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d23b8-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="d23b8-149">Die **Verweis-Manager** das Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="d23b8-150">Am oberen Rand des Dialogfelds stellen Sie sicher, dass Ihr Projekt auf .NET Framework 4.5 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="d23b8-151">In der **Assemblys** Bereich wählen **Framework** , wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="d23b8-152">Wählen Sie in der Liste der Namen, die **System.Net.Http** das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="d23b8-153">Wählen Sie die **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="d23b8-154"><a name="ImportsState"></a>Erforderliche Imports-Anweisungen hinzu</span><span class="sxs-lookup"><span data-stu-id="d23b8-154"><a name="ImportsState"></a> To add necessary Imports statements</span></span>  
  
1.  <span data-ttu-id="d23b8-155">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="d23b8-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="d23b8-156">Fügen Sie die folgenden `Imports` -Anweisungen am Anfang der Codedatei, wenn sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d23b8-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="d23b8-157"><a name="synchronous"></a>Erstellen Sie eine synchrone Anwendung</span><span class="sxs-lookup"><span data-stu-id="d23b8-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="d23b8-158">Doppelklicken Sie im Entwurfsfenster "MainWindow.xaml", auf die **Start** Schaltfläche zum Erstellen der `startButton_Click` -Ereignishandler in "MainWindow.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="d23b8-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d23b8-159">Klicken Sie in "MainWindow.Xaml.vb", kopieren Sie den folgenden Code in den Text der `startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="d23b8-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     <span data-ttu-id="d23b8-160">Der Code ruft die Methode `SumPageSizes` auf, die die Anwendung steuert und zeigt eine Meldung an, wenn das Steuerelement zu `startButton_Click` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="d23b8-161">Der Code für die synchrone Lösung enthält die folgenden vier Methoden:</span><span class="sxs-lookup"><span data-stu-id="d23b8-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="d23b8-162">`SumPageSizes`. Enthält eine Liste von Webseiten-URLs aus `SetUpURLList` und ruft dann `GetURLContents` und `DisplayResults` auf, um jede URL zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d23b8-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="d23b8-163">`SetUpURLList`. Erstellt und gibt eine Liste der Webadressen zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="d23b8-164">`GetURLContents`. Lädt Inhalte jeder Website herunter und gibt die Inhalte als ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="d23b8-165">`DisplayResults`. Zeigt die Anzahl der Bytes im Bytearray für jede URL an.</span><span class="sxs-lookup"><span data-stu-id="d23b8-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="d23b8-166">Kopieren Sie die folgenden vier Methoden, und fügen Sie sie unter der `startButton_Click` -Ereignishandler in "MainWindow.Xaml.vb":</span><span class="sxs-lookup"><span data-stu-id="d23b8-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <span data-ttu-id="d23b8-167"><a name="testSynch"></a>So testen Sie die synchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="d23b8-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="d23b8-168">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="d23b8-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="d23b8-169">Die Ausgabe sollte der folgenden Liste gleichen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-169">Output that resembles the following list should appear.</span></span>  
  
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
  
     <span data-ttu-id="d23b8-170">Beachten Sie, dass es ein paar Sekunden dauert, bis die Zahlen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="d23b8-171">Während dieser Zeit ist der Benutzeroberflächenthread blockiert, während auf das Herunterladen von angeforderten Ressourcen gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="d23b8-172">Daher kann nicht verschoben werden, zu maximieren, minimieren oder sogar das Fenster schließen, nachdem Sie ausgewählt haben die **Start** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d23b8-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="d23b8-173">Diese Bemühungen sind nicht erfolgreich, bis der Bytezähler angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="d23b8-174">Wenn eine Website nicht antwortet, erhalten Sie keinen Hinweis darüber, welche Site fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="d23b8-175">Es ist sogar schwierig, mit dem Warten aufzuhören und das Programm zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="d23b8-176"><a name="GetURLContents"></a>So konvertieren Sie GetURLContents in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="d23b8-177">Um die synchrone Lösung in einer asynchronen Lösung zu konvertieren, wird der beste Ausgangspunkt `GetURLContents` da die Aufrufe an die <xref:System.Net.HttpWebRequest>Methode <xref:System.Net.HttpWebRequest.GetResponse%2A>und die <xref:System.IO.Stream>Methode <xref:System.IO.Stream.CopyTo%2A>sind, in dem die Anwendung auf das Internet zugreift.</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest></span><span class="sxs-lookup"><span data-stu-id="d23b8-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="d23b8-178">.NET Framework erleichtert die Konvertierung, indem asynchrone Versionen beider Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="d23b8-179">Weitere Informationen zu den Methoden, die in verwendeten `GetURLContents`, finden Sie unter <xref:System.Net.WebRequest>.</xref:System.Net.WebRequest></span><span class="sxs-lookup"><span data-stu-id="d23b8-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d23b8-180">Beim Befolgen der Schritte in dieser exemplarischen Vorgehensweise treten verschiedene Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d23b8-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="d23b8-181">Sie können diese ignorieren und mit der exemplarischen Vorgehensweise fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d23b8-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="d23b8-182">Ändern Sie die Methode, die aufgerufen wird, in der dritten Zeile der `GetURLContents` von `GetResponse` auf den asynchronen aufgabenbasierte <xref:System.Net.WebRequest.GetResponseAsync%2A>-Methode.</xref:System.Net.WebRequest.GetResponseAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d23b8-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  <span data-ttu-id="d23b8-183">`GetResponseAsync`Gibt eine <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="d23b8-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="d23b8-184">In diesem Fall die *Aufgabe Rückgabevariablen*, `TResult`, weist den Typ <xref:System.Net.WebResponse>.</xref:System.Net.WebResponse></span><span class="sxs-lookup"><span data-stu-id="d23b8-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="d23b8-185">Mit dieser Aufgabe soll ein tatsächliches `WebResponse`-Objekt erstellt werden, nachdem die angeforderten Daten heruntergeladen und das Ausführen der Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d23b8-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="d23b8-186">Zum Abrufen der `WebResponse` -Wert von der Aufgabe, gelten eine ["await"](../../../../visual-basic/language-reference/operators/await-operator.md) Operator, um den Aufruf von `GetResponseAsync`, wie der folgende Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="d23b8-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d23b8-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="d23b8-188">Die `Await` -Operator hält die Ausführung der aktuellen Methode `GetURLContents`, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-188">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="d23b8-189">In der Zwischenzeit kehrt die Steuerung zum Aufrufer der aktuellen Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-189">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="d23b8-190">In diesem Beispiel lautet die aktuelle Methode `GetURLContents`, und der Aufrufer ist `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-190">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="d23b8-191">Wenn die Aufgabe abgeschlossen ist, wird das zugesicherte `WebResponse`-Objekt als Wert der erwarteten Aufgabe erstellt und zur Variable `response` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-191">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<span data-ttu-id="d23b8-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d23b8-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="d23b8-193">Durch den Aufruf von `webReq.GetResponseAsync` wird `Task(Of WebResponse)` oder `Task<WebResponse>` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d23b8-193">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="d23b8-194">Ein `Await` Operator gilt für den Task zum Abrufen der `WebResponse` Wert.</span><span class="sxs-lookup"><span data-stu-id="d23b8-194">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  <span data-ttu-id="d23b8-195">Da Sie erweitert die `Await` Operator im vorherigen Schritt, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d23b8-195">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="d23b8-196">Der-Operator kann verwendet werden, nur in Methoden, die mit der [Async](../../../../visual-basic/language-reference/modifiers/async.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d23b8-196">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="d23b8-197">Ignorieren Sie den Fehler, während Sie die Konvertierungsschritte zum Ersetzen des Aufrufs von `CopyTo` mit einem Aufruf von `CopyToAsync` wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-197">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="d23b8-198">Ändern Sie den Namen der Methode, die aufgerufen wird, um <xref:System.IO.Stream.CopyToAsync%2A>.</xref:System.IO.Stream.CopyToAsync%2A></span><span class="sxs-lookup"><span data-stu-id="d23b8-198">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="d23b8-199">Die Methode `CopyTo` oder `CopyToAsync` kopiert Bytes zu ihrem Argument `content` und gibt keinen sinnvollen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-199">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="d23b8-200">In der synchronen Version ist der Aufruf von `CopyTo` eine einfache Anweisung, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-200">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="d23b8-201">Die asynchrone Version `CopyToAsync`, gibt eine <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="d23b8-201">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="d23b8-202">Die Aufgabe funktioniert wie „Task(void)“ und ermöglicht, dass auf die Methode gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-202">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="d23b8-203">Wenden Sie `Await` oder `await` auf den Aufruf von `CopyToAsync` an, wie dies im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-203">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="d23b8-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d23b8-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
         <span data-ttu-id="d23b8-205">Die vorherige Anweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
<span data-ttu-id="d23b8-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d23b8-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="d23b8-207">Somit muss nur noch die Methodensignatur in `GetURLContents` angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-207">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="d23b8-208">Können Sie die `Await` Operator nur in Methoden, die mit der [Async](../../../../visual-basic/language-reference/modifiers/async.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d23b8-208">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="d23b8-209">Fügen Sie den Modifizierer, um die Methode als Markieren einer *Async-Methode*, wie der folgende Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-209">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
<span data-ttu-id="d23b8-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d23b8-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
5.  <span data-ttu-id="d23b8-211">Der Rückgabetyp einer Async-Methode kann nur <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> sein.</span><span class="sxs-lookup"><span data-stu-id="d23b8-211">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="d23b8-212">In Visual Basic muss die Methode eine `Function` sein, die eine `Task` oder eine `Task(Of T)` zurückgibt, oder die Methode muss ein `Sub` sein.</span><span class="sxs-lookup"><span data-stu-id="d23b8-212">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="d23b8-213">In der Regel eine `Sub` Methode wird nur in einem asynchronen Ereignishandler verwendet, in denen `Sub` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d23b8-213">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="d23b8-214">In anderen Fällen verwenden Sie `Task(T)` verfügt die vollständige Methode eine [zurückgeben](../../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung, die den Wert zurückgibt, Typ T, und Sie verwenden `Task` Wenn die vollständige Methode einen sinnvollen Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-214">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>  
  
     <span data-ttu-id="d23b8-215">Weitere Informationen finden Sie unter [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="d23b8-215">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="d23b8-216">Die Methode `GetURLContents` verfügt über eine return-Anweisung, und die Anweisung gibt ein Bytearray zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-216">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="d23b8-217">Daher ist der Rückgabetyp der der asynchronen Version „Task(T)“, wobei „T“ ein Bytearray ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-217">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="d23b8-218">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="d23b8-218">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="d23b8-219">Ändern Sie den Rückgabetyp in `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-219">Change the return type to `Task(Of Byte())`.</span></span>  
  
    -   <span data-ttu-id="d23b8-220">Asynchrone Methoden verfügen gemäß der Konvention über Namen, die auf „Async“ enden. Benennen Sie also die Methode `GetURLContentsAsync` um.</span><span class="sxs-lookup"><span data-stu-id="d23b8-220">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="d23b8-221">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-221">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     <span data-ttu-id="d23b8-222">Mit diesen wenigen Änderungen ist die Konvertierung von `GetURLContents` zu einer asynchronen Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-222">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="d23b8-223"><a name="SumPageSizes"></a>So konvertieren Sie SumPageSizes in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-223"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="d23b8-224">Wiederholen Sie die Schritte des vorherigen Verfahrens für `SumPageSizes`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-224">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="d23b8-225">Ändern Sie zunächst den Aufruf von `GetURLContents` zu einem asynchronen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="d23b8-225">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="d23b8-226">Ändern Sie den Namen der Methode, die aufgerufen wird, von `GetURLContents` zu `GetURLContentsAsync`, sofern Sie dies nicht bereits getan haben.</span><span class="sxs-lookup"><span data-stu-id="d23b8-226">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="d23b8-227">Anwenden `Await` für die Aufgabe, die `GetURLContentsAsync` gibt die Byte abrufen Arraywert.</span><span class="sxs-lookup"><span data-stu-id="d23b8-227">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="d23b8-228">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-228">The following code shows these changes.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     <span data-ttu-id="d23b8-229">Die vorherige Zuweisung kürzt die folgenden zwei Codezeilen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-229">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  <span data-ttu-id="d23b8-230">Nehmen Sie folgende Änderungen in der Methodensignatur vor:</span><span class="sxs-lookup"><span data-stu-id="d23b8-230">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="d23b8-231">Markieren Sie die Methode mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d23b8-231">Mark the method with the `Async` modifier.</span></span>  
  
    -   <span data-ttu-id="d23b8-232">Fügen Sie dem Methodennamen „Async“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="d23b8-232">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="d23b8-233">Es ist dieses Mal keine Aufgabenrückgabevariable „T“ vorhanden, da `SumPageSizesAsync` keinen Wert für „T“ zurückgibt. (Die Methode verfügt über keine `Return` Anweisung.) Die Methode muss jedoch eine `Task` zurückgeben, die awaitable ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-233">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="d23b8-234">Daher ändern, den Typ von `Sub` auf `Function`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-234">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="d23b8-235">Der Rückgabetyp der Funktion lautet `Task`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-235">The return type of the function is `Task`.</span></span>  
  
     <span data-ttu-id="d23b8-236">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-236">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     <span data-ttu-id="d23b8-237">Die Konvertierung von `SumPageSizes` zu `SumPageSizesAsync` ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-237">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="d23b8-238"><a name="startButton"></a>So konvertieren Sie StartButton_Click in eine asynchrone Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-238"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="d23b8-239">Ändern Sie im Ereignishandler den Namen der aufgerufenen Methode von `SumPageSizes` zu `SumPageSizesAsync`, sofern Sie dies nicht bereits vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="d23b8-239">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="d23b8-240">Da es sich bei `SumPageSizesAsync` um eine asynchrone Methode handelt, ändern Sie den Code im Ereignishandler, um auf das Ergebnis zu warten.</span><span class="sxs-lookup"><span data-stu-id="d23b8-240">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="d23b8-241">Der Aufruf von `SumPageSizesAsync` spiegelt den Aufruf von `CopyToAsync` in `GetURLContentsAsync` wider.</span><span class="sxs-lookup"><span data-stu-id="d23b8-241">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="d23b8-242">Der Aufruf gibt eine `Task` und keine `Task(T)` zurück.</span><span class="sxs-lookup"><span data-stu-id="d23b8-242">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="d23b8-243">Analog zu den vorherigen Vorgehensweisen können Sie den Aufruf mithilfe von einer oder zwei Anweisungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d23b8-243">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="d23b8-244">Im folgenden Code sind diese Änderungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-244">The following code shows these changes.</span></span>  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  <span data-ttu-id="d23b8-245">Um zu verhindern, dass versehentlich erneuten Beginn des Vorgangs, fügen Sie die folgende Anweisung am Anfang `startButton_Click` So deaktivieren Sie die **Start** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d23b8-245">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     <span data-ttu-id="d23b8-246">Sie können die Schaltfläche am Ende des Ereignishandlers wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d23b8-246">You can reenable the button at the end of the event handler.</span></span>  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     <span data-ttu-id="d23b8-247">Weitere Informationen zu Reentranz, finden Sie unter [Behandlung von Eintrittsinvarianz in Async-Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span><span class="sxs-lookup"><span data-stu-id="d23b8-247">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="d23b8-248">Fügen Sie abschließend die `Async` Modifizierer, um die Deklaration, damit der Ereignishandler await kann `SumPagSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-248">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     <span data-ttu-id="d23b8-249">In der Regel werden die Namen der Ereignishandler nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="d23b8-249">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="d23b8-250">Der Rückgabetyp wird nicht geändert, um `Task` da Ereignishandler sein müssen `Sub` Prozeduren in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d23b8-250">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>  
  
     <span data-ttu-id="d23b8-251">Die Konvertierung des Projekts von der synchronen zu asynchronen Verarbeitung ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-251">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="d23b8-252"><a name="testAsynch"></a>So testen Sie die asynchrone Lösung</span><span class="sxs-lookup"><span data-stu-id="d23b8-252"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="d23b8-253">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="d23b8-253">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="d23b8-254">Es sollte eine Ausgabe angezeigt werden, die der Ausgabe der synchronen Lösung gleicht.</span><span class="sxs-lookup"><span data-stu-id="d23b8-254">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="d23b8-255">Folgende Unterschiede sind jedoch zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-255">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="d23b8-256">Die Ergebnisse treten nicht alle gleichzeitig auf, nachdem die Verarbeitung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d23b8-256">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="d23b8-257">Beispielsweise enthalten beide Programme eine Zeile in `startButton_Click`, die das Textfeld löscht.</span><span class="sxs-lookup"><span data-stu-id="d23b8-257">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="d23b8-258">Ziel ist es, das Kontrollkästchen zwischen der Ausführung zu deaktivieren, falls gewünscht die **Start** Schaltfläche ein zweites Mal, sobald ein Satz von Ergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d23b8-258">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="d23b8-259">In der synchronen Version wird das Textfeld unmittelbar vor der zweiten Anzeige des Zählers gelöscht, wenn die Downloads abgeschlossen sind und der UI-Thread für die Verarbeitung anderer Aktionen frei ist.</span><span class="sxs-lookup"><span data-stu-id="d23b8-259">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="d23b8-260">Die asynchrone Version im Textfeld löscht sofort nach dem Auswählen der **Start** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d23b8-260">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="d23b8-261">Das Wichtigste ist jedoch, dass der UI-Thread nicht blockiert wird, während Downloads vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-261">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="d23b8-262">Sie können das Fenster verschieben oder dessen Größe anpassen, während die Webressourcen heruntergeladen, gezählt und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d23b8-262">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="d23b8-263">Wenn eine Website langsam ist oder nicht reagiert, Sie den Vorgang durch Auswählen abbrechen können der **schließen** Schaltfläche (das x im roten Feld in der oberen rechten Ecke).</span><span class="sxs-lookup"><span data-stu-id="d23b8-263">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="d23b8-264"><a name="GetURLContentsAsync"></a>Zum Ersetzen der Methode "geturlcontentsasync" durch eine .NET Framework-Methode</span><span class="sxs-lookup"><span data-stu-id="d23b8-264"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="d23b8-265">.NET Framework 4.5 bietet viele asynchrone Methoden, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d23b8-265">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="d23b8-266">Die <xref:System.Net.Http.HttpClient>Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, ist genau für diese exemplarische Vorgehensweise das richtige.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="d23b8-266">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="d23b8-267">Sie können sie anstelle der `GetURLContentsAsync`-Methode verwenden, die Sie in einer vorherigen Vorgehensweise erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d23b8-267">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="d23b8-268">Der erste Schritt besteht darin, ein `HttpClient`-Objekt in der Methode `SumPageSizesAsync` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d23b8-268">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="d23b8-269">Fügen Sie am Anfang der Methode die folgende Deklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="d23b8-269">Add the following declaration at the start of the method.</span></span>  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  <span data-ttu-id="d23b8-270">Ersetzen Sie in `SumPageSizesAsync,` den Aufruf zu Ihrer `GetURLContentsAsync`-Methode durch einen Aufruf zur Methode `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="d23b8-270">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  <span data-ttu-id="d23b8-271">Entfernen Sie die von Ihnen geschriebene `GetURLContentsAsync`-Methode, oder kommentieren Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="d23b8-271">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="d23b8-272">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="d23b8-272">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="d23b8-273">Das Verhalten dieser Version des Projekts sollte mit dem Verhalten übereinstimmen, das in der Vorgehensweise „So testen Sie die asynchrone Lösung“ beschrieben wird, es sollte aber weniger Aufwand Ihrerseits nötig sein.</span><span class="sxs-lookup"><span data-stu-id="d23b8-273">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="d23b8-274"><a name="BKMK_CompleteCodeExamples"></a>Beispiel</span><span class="sxs-lookup"><span data-stu-id="d23b8-274"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="d23b8-275">Der folgende Code enthält das vollständige Beispiel der Konvertierung von einer synchronen zu einer asynchronen Lösung mithilfe der von Ihnen geschriebenen asynchronen `GetURLContentsAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d23b8-275">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="d23b8-276">Beachten Sie, dass sie der ursprünglichen synchronen Lösung sehr stark ähnelt.</span><span class="sxs-lookup"><span data-stu-id="d23b8-276">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 <span data-ttu-id="d23b8-277">Der folgende Code umfasst das vollständige Beispiel der Lösung, die die `HttpClient`-Methode `GetByteArrayAsync` verwendet.</span><span class="sxs-lookup"><span data-stu-id="d23b8-277">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
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
  
        '' Two-step async call.  
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
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="d23b8-278">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d23b8-278">See Also</span></span>  
 <span data-ttu-id="d23b8-279">[ASYNC-Beispiel: Zugreifen auf die Web-Exemplarische Vorgehensweise (C#- und Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="d23b8-279">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
<span data-ttu-id="d23b8-280"> [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d23b8-280"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="d23b8-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="d23b8-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="d23b8-282"> [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="d23b8-282"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="d23b8-283"> [Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="d23b8-283"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="d23b8-284"> [Aufgabenbasierte asynchrone Programmierung (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="d23b8-284"> [Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
<span data-ttu-id="d23b8-285"> [Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="d23b8-285"> [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
<span data-ttu-id="d23b8-286"> [Gewusst wie: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="d23b8-286"> [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
