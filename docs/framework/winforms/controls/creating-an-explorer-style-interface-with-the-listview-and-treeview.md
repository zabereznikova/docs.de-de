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
ms.openlocfilehash: 540226dbbada0373854144ac874d2164208ad943
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039913"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="74a84-102">Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="74a84-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="74a84-103">Einer der Vorteile von Visual Studio ist die Möglichkeit, in einem kurzen Zeitraum professionell aussehende Windows Forms Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74a84-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="74a84-104">Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) <xref:System.Windows.Forms.ListView> mit <xref:System.Windows.Forms.TreeView> -und-Steuerelementen, die der Windows-Explorer-Funktion von Windows-Betriebssystemen ähneln.</span><span class="sxs-lookup"><span data-stu-id="74a84-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="74a84-105">Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="74a84-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>


### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="74a84-106">So erstellen Sie das Formular mit einem ListView-und TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-106">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="74a84-107">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="74a84-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="74a84-108">Führen Sie im Dialogfeld **Neues Projekt** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="74a84-108">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="74a84-109">Wählen Sie in den Kategorien entweder **Visual Basic** oder **Visualisierung C#** aus.</span><span class="sxs-lookup"><span data-stu-id="74a84-109">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="74a84-110">Wählen Sie in der Liste der Vorlagen **Windows Forms Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="74a84-110">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="74a84-111">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="74a84-111">Click **OK**.</span></span> <span data-ttu-id="74a84-112">Ein neues Windows Forms Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="74a84-112">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="74a84-113">Fügen Sie <xref:System.Windows.Forms.SplitContainer> dem Formular ein Steuerelement hinzu, <xref:System.Windows.Forms.SplitContainer.Dock%2A> und legen <xref:System.Windows.Forms.DockStyle.Fill>Sie dessen-Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-113">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="74a84-114">Fügen Sie <xref:System.Windows.Forms.ImageList> dem `imageList1` Formular einen mit dem Namen hinzu, und verwenden Sie die Eigenschaftenfenster, um zwei Bilder hinzuzufügen: ein Ordner Image und ein Dokument Bild in dieser Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="74a84-114">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="74a84-115">Fügen Sie <xref:System.Windows.Forms.TreeView> dem Formular `treeview1` ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es <xref:System.Windows.Forms.SplitContainer> auf der linken Seite des-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="74a84-115">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="74a84-116">Gehen Sie im Eigenschaftenfenster `treeView1` für wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="74a84-116">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="74a84-117">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-117">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="74a84-118">Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-118">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="74a84-119">Fügen Sie <xref:System.Windows.Forms.ListView> dem Formular `listView1` ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es <xref:System.Windows.Forms.SplitContainer> auf der rechten Seite des-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="74a84-119">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="74a84-120">Gehen Sie im Eigenschaftenfenster `listview1` für wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="74a84-120">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="74a84-121">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-121">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="74a84-122">Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf <xref:System.Windows.Forms.View.Details>fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-122">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="74a84-123">Öffnen Sie den ColumnHeader-Auflistungs-Editor,![indem Sie in <xref:System.Windows.Forms.ListView.Columns%2A> der-Eigenschaft auf die Auslassungs Punkte (die Schaltfläche mit](./media/visual-studio-ellipsis-button.png)den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio klicken.</span><span class="sxs-lookup"><span data-stu-id="74a84-123">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="74a84-124">Fügen Sie drei Spalten hinzu, <xref:System.Windows.Forms.ColumnHeader.Text%2A> und legen `Name`Sie `Type`die zugehörige-Eigenschaft auf, `Last Modified`bzw. fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-124">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="74a84-125">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="74a84-125">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="74a84-126">Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.</span><span class="sxs-lookup"><span data-stu-id="74a84-126">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="74a84-127">Implementieren Sie den Code, um die <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="74a84-127">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="74a84-128">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="74a84-128">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="74a84-129">Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende using-oder Import-Anweisung am Anfang des Formulars hinzu.</span><span class="sxs-lookup"><span data-stu-id="74a84-129">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="74a84-130">Ruft die Setup Methode aus dem vorherigen Schritt im Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> der Ereignis Behandlungsmethode auf.</span><span class="sxs-lookup"><span data-stu-id="74a84-130">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="74a84-131">Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="74a84-131">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="74a84-132">Behandeln Sie <xref:System.Windows.Forms.TreeView.NodeMouseClick> das -Ereignis`treeview1`für **,** und implementieren Sie den Code, um den Inhalt eines Knotens aufzufüllen ,wennaufeinenKnotengeklickt`listview1` wird.</span><span class="sxs-lookup"><span data-stu-id="74a84-132">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="74a84-133">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="74a84-133">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="74a84-134">Wenn Sie verwenden C#, stellen Sie sicher, dass das <xref:System.Windows.Forms.TreeView.NodeMouseClick> -Ereignis mit seiner Ereignis Behandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="74a84-134">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="74a84-135">Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="74a84-135">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="74a84-136">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="74a84-136">Testing the Application</span></span>

<span data-ttu-id="74a84-137">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="74a84-137">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="74a84-138">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="74a84-138">To test the form</span></span>

- <span data-ttu-id="74a84-139">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74a84-139">Press F5 to run the application.</span></span>

     <span data-ttu-id="74a84-140">Sie sehen ein geteiltes Formular, das <xref:System.Windows.Forms.TreeView> ein Steuerelement enthält, das Ihr Projektverzeichnis auf der linken Seite <xref:System.Windows.Forms.ListView> anzeigt, und ein Steuerelement auf der rechten Seite mit drei Spalten.</span><span class="sxs-lookup"><span data-stu-id="74a84-140">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="74a84-141">Sie können den <xref:System.Windows.Forms.TreeView> durchlaufen, indem Sie Verzeichnis Knoten auswählen <xref:System.Windows.Forms.ListView> , und wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="74a84-141">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74a84-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="74a84-142">Next Steps</span></span>

<span data-ttu-id="74a84-143">Diese Anwendung bietet ein Beispiel dafür, wie Sie und- <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> Steuerelemente gleichzeitig verwenden können.</span><span class="sxs-lookup"><span data-stu-id="74a84-143">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="74a84-144">Weitere Informationen zu diesen Steuerelementen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="74a84-144">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="74a84-145">Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="74a84-145">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="74a84-146">Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-146">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="74a84-147">Vorgehensweise: Anfügen eines Kontextmenüs an einen TreeView-Knoten</span><span class="sxs-lookup"><span data-stu-id="74a84-147">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="74a84-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a84-148">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="74a84-149">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-149">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="74a84-150">Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem Windows Forms TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-150">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="74a84-151">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="74a84-152">Vorgehensweise: Hinzufügen von Spalten zum Windows Forms ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74a84-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
