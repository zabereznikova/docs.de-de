---
title: Erstellen von Dateien und Verzeichnissen
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: 83dc6ce0d29c1c368c36b51fc84ecad34d72e01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333809"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="e94b9-102">Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e94b9-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>

<span data-ttu-id="e94b9-103">Diese exemplarische Vorgehensweise enthält eine Einführung in die Grundlagen der Datei-E/A in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e94b9-103">This walkthrough provides an introduction to the fundamentals of file I/O in Visual Basic.</span></span> <span data-ttu-id="e94b9-104">Es wird beschrieben, wie Sie eine kleine Anwendung erstellen können, in der Textdateien in einem Verzeichnis aufgelistet und überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="e94b9-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="e94b9-105">Die Anwendung stellt Dateiattribute und die erste Zeile des Inhalts jeder ausgewählten Textdatei zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e94b9-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="e94b9-106">Es besteht die Möglichkeit, Informationen in eine Protokolldatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e94b9-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="e94b9-107">In dieser exemplarischen Vorgehensweise werden Member von `My.Computer.FileSystem Object` verwendet, die in Visual Basic verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e94b9-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in Visual Basic.</span></span> <span data-ttu-id="e94b9-108">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.FileIO.FileSystem>.</span><span class="sxs-lookup"><span data-stu-id="e94b9-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="e94b9-109">Am Ende dieser exemplarischen Vorgehensweise finden Sie ein entsprechendes Beispiel, in dem Klassen aus dem Namespace <xref:System.IO> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e94b9-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="e94b9-110">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="e94b9-110">To create the project</span></span>  
  
1. <span data-ttu-id="e94b9-111">Klicken Sie im Menü **Datei** auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="e94b9-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-112">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="e94b9-113">Erweitern Sie im Bereich **Installierte Vorlagen** **Visual Basic**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="e94b9-114">Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="e94b9-115">Geben Sie im Feld **Name**`FileExplorer` ein, um den Projektnamen festzulegen, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e94b9-116">Visual Studio fügt das Projekt in den **Projektmappen-Explorer** ein. Der Windows Forms-Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e94b9-116">Visual Studio adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4. <span data-ttu-id="e94b9-117">Fügen Sie die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="e94b9-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="e94b9-118">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e94b9-118">Control</span></span>|<span data-ttu-id="e94b9-119">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e94b9-119">Property</span></span>|<span data-ttu-id="e94b9-120">Wert</span><span class="sxs-lookup"><span data-stu-id="e94b9-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="e94b9-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="e94b9-121">**ListBox**</span></span>|<span data-ttu-id="e94b9-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="e94b9-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="e94b9-123">**Button** (Schaltfläche)</span><span class="sxs-lookup"><span data-stu-id="e94b9-123">**Button**</span></span>|<span data-ttu-id="e94b9-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="e94b9-124">**Name**</span></span><br /><br /> <span data-ttu-id="e94b9-125">**Text**</span><span class="sxs-lookup"><span data-stu-id="e94b9-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="e94b9-126">**Browse** (Durchsuchen)</span><span class="sxs-lookup"><span data-stu-id="e94b9-126">**Browse**</span></span>|  
    |<span data-ttu-id="e94b9-127">**Button** (Schaltfläche)</span><span class="sxs-lookup"><span data-stu-id="e94b9-127">**Button**</span></span>|<span data-ttu-id="e94b9-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="e94b9-128">**Name**</span></span><br /><br /> <span data-ttu-id="e94b9-129">**Text**</span><span class="sxs-lookup"><span data-stu-id="e94b9-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="e94b9-130">**Examine** (Untersuchen)</span><span class="sxs-lookup"><span data-stu-id="e94b9-130">**Examine**</span></span>|  
    |<span data-ttu-id="e94b9-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="e94b9-131">**CheckBox**</span></span>|<span data-ttu-id="e94b9-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="e94b9-132">**Name**</span></span><br /><br /> <span data-ttu-id="e94b9-133">**Text**</span><span class="sxs-lookup"><span data-stu-id="e94b9-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="e94b9-134">**Save Results** (Ergebnisse speichern)</span><span class="sxs-lookup"><span data-stu-id="e94b9-134">**Save Results**</span></span>|  
    |<span data-ttu-id="e94b9-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="e94b9-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="e94b9-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="e94b9-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="e94b9-137">So wählen Sie einen Ordner und Listendateien in einem Ordner aus</span><span class="sxs-lookup"><span data-stu-id="e94b9-137">To select a folder, and list files in a folder</span></span>  
  
1. <span data-ttu-id="e94b9-138">Erstellen Sie einen `Click`-Ereignishandler für `browseButton`, indem Sie auf ein Steuerelement im Formular doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="e94b9-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="e94b9-139">Der Code-Editor wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e94b9-139">The Code Editor opens.</span></span>  
  
2. <span data-ttu-id="e94b9-140">Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     <span data-ttu-id="e94b9-141">Mit dem Aufruf `FolderBrowserDialog1.ShowDialog` wird das Dialogfeld **Ordner suchen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e94b9-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="e94b9-142">Sobald der Benutzer auf **OK** klickt, wird die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft als Argument an die `ListFiles`-Methode gesendet, die im nächsten Schritt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e94b9-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3. <span data-ttu-id="e94b9-143">Fügen Sie die folgende `ListFiles`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     <span data-ttu-id="e94b9-144">Dieser Code löscht zuerst **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="e94b9-145">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>-Methode ruft anschließend eine Auflistung von Zeichenfolgen ab, eine für jede Datei im Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e94b9-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="e94b9-146">Die Methode `GetFiles` akzeptiert ein Suchmusterargument, um Dateien abzurufen, die mit einem bestimmten Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e94b9-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="e94b9-147">In diesem Beispiel werden nur Dateien mit der Dateiendung „.txt“ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e94b9-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="e94b9-148">Die Zeichenfolgen, die von der Methode `GetFiles` zurückgegeben werden, werden anschließend zu **ListBox** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4. <span data-ttu-id="e94b9-149">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-149">Run the application.</span></span> <span data-ttu-id="e94b9-150">Klicken Sie auf die Schaltfläche **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-150">Click the **Browse** button.</span></span> <span data-ttu-id="e94b9-151">Navigieren Sie im Dialogfeld **Ordner suchen** zu einem Ordner, der .txt-Dateien enthält. Wählen Sie den Ordner anschließend aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="e94b9-152">`ListBox` enthält eine Liste von .txt-Dateien im ausgewählten Ordner.</span><span class="sxs-lookup"><span data-stu-id="e94b9-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5. <span data-ttu-id="e94b9-153">Beenden Sie die Ausführung der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e94b9-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="e94b9-154">So rufen Sie Attribute einer Datei und Inhalt einer Textdatei ab</span><span class="sxs-lookup"><span data-stu-id="e94b9-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1. <span data-ttu-id="e94b9-155">Erstellen Sie einen `Click`-Ereignishandler für `examineButton`, indem Sie auf ein Steuerelement im Formular doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="e94b9-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2. <span data-ttu-id="e94b9-156">Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     <span data-ttu-id="e94b9-157">Der Code stellt sicher, dass ein Element in `ListBox` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="e94b9-158">Anschließend ruft er den Eintrag des Dateipfads aus `ListBox` ab.</span><span class="sxs-lookup"><span data-stu-id="e94b9-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="e94b9-159">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A>-Methode wird verwendet, um zu überprüfen, ob die Datei noch vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="e94b9-160">Der Dateipfad wird als Argument an die `GetTextForOutput`-Methode gesendet, die im nächsten Schritt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e94b9-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="e94b9-161">Diese Methode gibt eine Zeichenfolge zurück, die Dateiinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="e94b9-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="e94b9-162">Die Dateiinformationen werden in einer **MessageBox** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-162">The file information appears in a **MessageBox**.</span></span>  
  
3. <span data-ttu-id="e94b9-163">Fügen Sie die folgende `GetTextForOutput`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     <span data-ttu-id="e94b9-164">Der Code verwendet die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>-Methode zum Abrufen von Dateiparametern.</span><span class="sxs-lookup"><span data-stu-id="e94b9-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="e94b9-165">Die Dateiparameter werden einem <xref:System.Text.StringBuilder> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="e94b9-166">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>-Methode liest den Dateiinhalt in ein <xref:System.IO.StreamReader>-Element aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="e94b9-167">Die erste Zeile des Inhalts wird von `StreamReader` abgerufen und zu `StringBuilder` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4. <span data-ttu-id="e94b9-168">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-168">Run the application.</span></span> <span data-ttu-id="e94b9-169">Klicken Sie auf **Durchsuchen**, und suchen Sie nach einem Ordner, der .txt-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="e94b9-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="e94b9-170">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e94b9-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="e94b9-171">Wählen Sie eine Datei aus `ListBox` aus, und klicken Sie anschließend auf **Examine** (Untersuchen).</span><span class="sxs-lookup"><span data-stu-id="e94b9-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="e94b9-172">Die Dateiinformationen werden von `MessageBox` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-172">A `MessageBox` shows the file information.</span></span>  
  
5. <span data-ttu-id="e94b9-173">Beenden Sie die Ausführung der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e94b9-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="e94b9-174">So fügen Sie einen Protokolleintrag hinzu</span><span class="sxs-lookup"><span data-stu-id="e94b9-174">To add a log entry</span></span>  
  
1. <span data-ttu-id="e94b9-175">Fügen Sie am Ende des `examineButton_Click`-Ereignishandlers folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     <span data-ttu-id="e94b9-176">Der Protokolldateipfad wird vom Code so festgelegt, dass die Protokolldatei in dem Verzeichnis gespeichert wird, das auch das Verzeichnis der ausgewählten Datei ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="e94b9-177">Der Text der Protokolldatei wird auf das aktuelle Datum und die Uhrzeit sowie die Dateiinformationen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="e94b9-178">Zum Erstellen des Protokolleintrags wird die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode verwendet, deren `append`-Argument auf `True` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2. <span data-ttu-id="e94b9-179">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-179">Run the application.</span></span> <span data-ttu-id="e94b9-180">Navigieren Sie zu einer Textdatei, wählen Sie diese in `ListBox` aus, aktivieren Sie das Kontrollkästchen **Save Results** (Ergebnisse speichern), und klicken Sie auf **Examine** (Untersuchen).</span><span class="sxs-lookup"><span data-stu-id="e94b9-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="e94b9-181">Stellen Sie sicher, dass der Protokolleintrag in die `log.txt`-Datei geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3. <span data-ttu-id="e94b9-182">Beenden Sie die Ausführung der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e94b9-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="e94b9-183">So verwenden Sie das aktuelle Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="e94b9-183">To use the current directory</span></span>  
  
1. <span data-ttu-id="e94b9-184">Erstellen Sie einen Ereignishandler für `Form1_Load`, indem Sie auf das Formular doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="e94b9-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2. <span data-ttu-id="e94b9-185">Fügen Sie dem Ereignishandler folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     <span data-ttu-id="e94b9-186">Durch diesen Code wird das Standardverzeichnis auf den Browser des Ordners zum aktuellen Verzeichnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e94b9-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3. <span data-ttu-id="e94b9-187">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-187">Run the application.</span></span> <span data-ttu-id="e94b9-188">Wenn Sie zum ersten Mal auf **Durchsuchen** klicken, wird das Dialogfeld **Ordner suchen** im aktuellen Verzeichnis geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e94b9-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4. <span data-ttu-id="e94b9-189">Beenden Sie die Ausführung der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e94b9-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="e94b9-190">So aktivieren Sie Steuerelemente selektiv</span><span class="sxs-lookup"><span data-stu-id="e94b9-190">To selectively enable controls</span></span>  
  
1. <span data-ttu-id="e94b9-191">Fügen Sie die folgende `SetEnabled`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     <span data-ttu-id="e94b9-192">Die Methode `SetEnabled` aktiviert oder deaktiviert Steuerelemente. Dies hängt davon ab, ob ein Element in `ListBox` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2. <span data-ttu-id="e94b9-193">Erstellen Sie einen `SelectedIndexChanged`-Ereignishandler für `filesListBox`, indem Sie auf das Steuerelement `ListBox` im Formular doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="e94b9-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3. <span data-ttu-id="e94b9-194">Fügen Sie im Ereignishandler `filesListBox_SelectedIndexChanged` einen Aufruf von `SetEnabled` hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4. <span data-ttu-id="e94b9-195">Fügen Sie am Ende des Ereignishandlers `browseButton_Click` einen Aufruf von `SetEnabled` hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5. <span data-ttu-id="e94b9-196">Fügen Sie am Ende des Ereignishandlers `Form1_Load` einen Aufruf von `SetEnabled` hinzu.</span><span class="sxs-lookup"><span data-stu-id="e94b9-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6. <span data-ttu-id="e94b9-197">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e94b9-197">Run the application.</span></span> <span data-ttu-id="e94b9-198">Das Kontrollkästchen **Save Results** (Ergebnisse speichern) und die Schaltfläche **Examine** (Untersuchen) sind deaktiviert, wenn ein Element nicht in `ListBox` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e94b9-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="e94b9-199">Ausführliches Beispiel mit Verwendung von „My.Computer.FileSystem“</span><span class="sxs-lookup"><span data-stu-id="e94b9-199">Full example using My.Computer.FileSystem</span></span>  

 <span data-ttu-id="e94b9-200">Im Folgenden sehen Sie das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e94b9-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="e94b9-201">Ausführliches Beispiel mit Verwendung von „System.IO“</span><span class="sxs-lookup"><span data-stu-id="e94b9-201">Full example using System.IO</span></span>  

 <span data-ttu-id="e94b9-202">Im folgenden entsprechenden Beispiel werden Klassen aus dem Namespace <xref:System.IO> anstelle von `My.Computer.FileSystem`-Objekten verwendet.</span><span class="sxs-lookup"><span data-stu-id="e94b9-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a><span data-ttu-id="e94b9-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e94b9-203">See also</span></span>

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [<span data-ttu-id="e94b9-204">Exemplarische Vorgehensweise: Bearbeiten von Dateien mit .NET Framework-Methoden</span><span class="sxs-lookup"><span data-stu-id="e94b9-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)
