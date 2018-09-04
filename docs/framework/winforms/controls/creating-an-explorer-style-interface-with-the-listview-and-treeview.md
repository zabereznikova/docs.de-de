---
title: 'Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 73d3a0bef1ab075aee8e06f676ef17b853773552
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468063"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="c8a62-102">Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="c8a62-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="c8a62-103">Einer der Vorteile von Visual Studio ist die Fähigkeit zum Erstellen von professionell gestaltete Windows Forms-Anwendungen in eine Kurzform der Zeitspanne.</span><span class="sxs-lookup"><span data-stu-id="c8a62-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="c8a62-104">Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) mit <xref:System.Windows.Forms.ListView> und <xref:System.Windows.Forms.TreeView> Steuerelemente, die die Windows-Explorer-Funktion von Windows-Betriebssystemen ähnelt.</span><span class="sxs-lookup"><span data-stu-id="c8a62-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="c8a62-105">Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="c8a62-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8a62-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="c8a62-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c8a62-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c8a62-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c8a62-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c8a62-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="c8a62-109">Um das Formular mit einer ListView und TreeView-Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8a62-109">To create the form containing a ListView and TreeView control</span></span>  
  
1.  <span data-ttu-id="c8a62-110">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c8a62-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="c8a62-111">In der **neues Projekt** Dialogfeld Feld, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c8a62-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c8a62-112">Wählen Sie in die Kategorien entweder **Visual Basic** oder **Visual C#-**.</span><span class="sxs-lookup"><span data-stu-id="c8a62-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2.  <span data-ttu-id="c8a62-113">Wählen Sie in der Liste der Vorlagen, **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="c8a62-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="c8a62-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8a62-114">Click **OK**.</span></span> <span data-ttu-id="c8a62-115">Ein neues Windows Forms-Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="c8a62-115">A new Windows Forms project is created.</span></span>  
  
4.  <span data-ttu-id="c8a62-116">Hinzufügen einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement auf das Formular, und legen Sie dessen <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c8a62-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="c8a62-117">Hinzufügen einer <xref:System.Windows.Forms.ImageList> mit dem Namen `imageList1` auf das Formular und verwenden Sie das Fenster "Eigenschaften" zwei Bilder hinzu: ein Ordner-Image und eine Dokument-Image, in dieser Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8a62-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6.  <span data-ttu-id="c8a62-118">Hinzufügen einer <xref:System.Windows.Forms.TreeView> Steuerelement mit dem Namen `treeview1` auf das Formular, und positionieren Sie sie auf der linken Seite von der <xref:System.Windows.Forms.SplitContainer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c8a62-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="c8a62-119">Im Fenster "Eigenschaften" für `treeView1` gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c8a62-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1.  <span data-ttu-id="c8a62-120">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="c8a62-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="c8a62-121">Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.</span><span class="sxs-lookup"><span data-stu-id="c8a62-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>  
  
7.  <span data-ttu-id="c8a62-122">Hinzufügen einer <xref:System.Windows.Forms.ListView> Steuerelement mit dem Namen `listView1` auf das Formular, und positionieren Sie sie auf der rechten Seite von der <xref:System.Windows.Forms.SplitContainer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c8a62-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="c8a62-123">Im Fenster "Eigenschaften" für `listview1` gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c8a62-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1.  <span data-ttu-id="c8a62-124">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.</span><span class="sxs-lookup"><span data-stu-id="c8a62-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="c8a62-125">Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft auf <xref:System.Windows.Forms.View.Details> fest.</span><span class="sxs-lookup"><span data-stu-id="c8a62-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3.  <span data-ttu-id="c8a62-126">Öffnen Sie den ColumnHeader-Auflistungs-Editor, indem Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) in der <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft **.**</span><span class="sxs-lookup"><span data-stu-id="c8a62-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="c8a62-127">Fügen Sie drei Spalten hinzu, und legen Sie deren <xref:System.Windows.Forms.ColumnHeader.Text%2A> Eigenschaft `Name`, `Type`, und `Last Modified`bzw.</span><span class="sxs-lookup"><span data-stu-id="c8a62-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="c8a62-128">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c8a62-128">Click **OK** to close the dialog box.</span></span>  
  
    4.  <span data-ttu-id="c8a62-129">Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.</span><span class="sxs-lookup"><span data-stu-id="c8a62-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>  
  
8.  <span data-ttu-id="c8a62-130">Implementieren Sie den Code zum Auffüllen der <xref:System.Windows.Forms.TreeView> mit Knoten und die untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="c8a62-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="c8a62-131">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="c8a62-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="c8a62-132">Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende Verwendung oder import-Anweisung am oberen Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="c8a62-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="c8a62-133">Rufen Sie die Setup-Methode aus dem vorherigen Schritt in den Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode.</span><span class="sxs-lookup"><span data-stu-id="c8a62-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="c8a62-134">Fügen Sie diesen Code zum Konstruktor Formulars.</span><span class="sxs-lookup"><span data-stu-id="c8a62-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="c8a62-135">Behandeln der <xref:System.Windows.Forms.TreeView.NodeMouseClick> -Ereignis für `treeview1` **,** und implementieren Sie den Code zum Auffüllen `listview1` mit Inhalt eines Knotens, wenn Sie einen Knoten geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="c8a62-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="c8a62-136">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="c8a62-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="c8a62-137">Wenn Sie c# verwenden, stellen Sie sicher, dass die <xref:System.Windows.Forms.TreeView.NodeMouseClick> Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="c8a62-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="c8a62-138">Fügen Sie diesen Code zum Konstruktor Formulars.</span><span class="sxs-lookup"><span data-stu-id="c8a62-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="c8a62-139">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="c8a62-139">Testing the Application</span></span>  
 <span data-ttu-id="c8a62-140">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="c8a62-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="c8a62-141">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="c8a62-141">To test the form</span></span>  
  
-   <span data-ttu-id="c8a62-142">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8a62-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="c8a62-143">Sie sehen, dass ein Split-Formular mit einer <xref:System.Windows.Forms.TreeView> -Steuerelement, das Ihrem Projektverzeichnis auf der linken Seite angezeigt und eine <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite mit drei Spalten.</span><span class="sxs-lookup"><span data-stu-id="c8a62-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="c8a62-144">Sie durchlaufen können die <xref:System.Windows.Forms.TreeView> durch Auswählen der Directory-Knoten, und die <xref:System.Windows.Forms.ListView> wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="c8a62-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c8a62-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c8a62-145">Next Steps</span></span>  
 <span data-ttu-id="c8a62-146">Diese Anwendung bietet Ihnen ein Beispiel für eine Möglichkeit, Sie können <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="c8a62-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="c8a62-147">Weitere Informationen zu diesen Steuerelementen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c8a62-147">For more information on these controls, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c8a62-148">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c8a62-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [<span data-ttu-id="c8a62-149">Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c8a62-149">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [<span data-ttu-id="c8a62-150">Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten</span><span class="sxs-lookup"><span data-stu-id="c8a62-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="c8a62-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a62-151">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [<span data-ttu-id="c8a62-152">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c8a62-152">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="c8a62-153">Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8a62-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="c8a62-154">Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8a62-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="c8a62-155">Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8a62-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
