---
title: 'Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer'
description: Erfahren Sie, wie Sie eine Explorer-stilschnittstelle mit den Windows Forms ListView-und TreeView-Steuerelementen mithilfe des Designers erstellen.
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
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174626"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="6827c-103">Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="6827c-103">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="6827c-104">Einer der Vorteile von Visual Studio ist die Möglichkeit, in einem kurzen Zeitraum professionell aussehende Windows Forms Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6827c-104">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="6827c-105">Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) mit <xref:System.Windows.Forms.ListView> -und-Steuer <xref:System.Windows.Forms.TreeView> Elementen, die der Windows-Explorer-Funktion von Windows-Betriebssystemen ähneln.</span><span class="sxs-lookup"><span data-stu-id="6827c-105">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="6827c-106">Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="6827c-106">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="6827c-107">So erstellen Sie das Formular mit einem ListView-und TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6827c-107">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="6827c-108">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="6827c-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="6827c-109">Führen Sie im Dialogfeld **Neues Projekt** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6827c-109">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="6827c-110">Wählen Sie in den Kategorien entweder **Visual Basic** oder **Visual c#** aus.</span><span class="sxs-lookup"><span data-stu-id="6827c-110">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="6827c-111">Wählen Sie in der Liste der Vorlagen **Windows Forms Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="6827c-111">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="6827c-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6827c-112">Click **OK**.</span></span> <span data-ttu-id="6827c-113">Ein neues Windows Forms Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="6827c-113">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="6827c-114">Fügen Sie <xref:System.Windows.Forms.SplitContainer> dem Formular ein Steuerelement hinzu, und legen Sie dessen- <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft auf fest <xref:System.Windows.Forms.DockStyle.Fill> .</span><span class="sxs-lookup"><span data-stu-id="6827c-114">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="6827c-115">Fügen Sie <xref:System.Windows.Forms.ImageList> dem Formular einen mit dem Namen hinzu `imageList1` , und verwenden Sie die Eigenschaftenfenster, um zwei Bilder hinzuzufügen: ein Ordner Image und ein Dokument Bild in dieser Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="6827c-115">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="6827c-116">Fügen Sie <xref:System.Windows.Forms.TreeView> `treeview1` dem Formular ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es auf der linken Seite des- <xref:System.Windows.Forms.SplitContainer> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="6827c-116">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="6827c-117">Gehen Sie im Eigenschaftenfenster für wie `treeView1` folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6827c-117">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="6827c-118">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-118">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="6827c-119">Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-119">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="6827c-120">Fügen Sie <xref:System.Windows.Forms.ListView> `listView1` dem Formular ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es auf der rechten Seite des- <xref:System.Windows.Forms.SplitContainer> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="6827c-120">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="6827c-121">Gehen Sie im Eigenschaftenfenster für wie `listview1` folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6827c-121">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="6827c-122">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-122">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="6827c-123">Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf <xref:System.Windows.Forms.View.Details>fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-123">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="6827c-124">Öffnen Sie den ColumnHeader-Auflistungs-Editor, indem Sie in der-Eigenschaft auf die Auslassungs Punkte ( ![ die Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio klicken. ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Columns%2A> **.**</span><span class="sxs-lookup"><span data-stu-id="6827c-124">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="6827c-125">Fügen Sie drei Spalten hinzu, und legen Sie die zugehörige- <xref:System.Windows.Forms.ColumnHeader.Text%2A> Eigenschaft auf `Name` , `Type` `Last Modified` bzw. fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-125">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="6827c-126">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6827c-126">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="6827c-127">Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.</span><span class="sxs-lookup"><span data-stu-id="6827c-127">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="6827c-128">Implementieren Sie den Code, um die <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="6827c-128">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="6827c-129">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="6827c-129">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="6827c-130">Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende using-oder Import-Anweisung am Anfang des Formulars hinzu.</span><span class="sxs-lookup"><span data-stu-id="6827c-130">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="6827c-131">Ruft die Setup Methode aus dem vorherigen Schritt im Konstruktor des Formulars oder der <xref:System.Windows.Forms.Form.Load> Ereignis Behandlungsmethode auf.</span><span class="sxs-lookup"><span data-stu-id="6827c-131">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="6827c-132">Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="6827c-132">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="6827c-133">Behandeln <xref:System.Windows.Forms.TreeView.NodeMouseClick> Sie das-Ereignis für `treeview1` **,** und implementieren Sie den Code, um den `listview1` Inhalt eines Knotens aufzufüllen, wenn auf einen Knoten geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="6827c-133">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="6827c-134">Fügen Sie diesen Code zur `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="6827c-134">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="6827c-135">Wenn Sie c# verwenden, stellen Sie sicher, dass das- <xref:System.Windows.Forms.TreeView.NodeMouseClick> Ereignis mit seiner Ereignis Behandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="6827c-135">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="6827c-136">Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="6827c-136">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="6827c-137">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="6827c-137">Testing the Application</span></span>

<span data-ttu-id="6827c-138">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="6827c-138">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="6827c-139">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="6827c-139">To test the form</span></span>

- <span data-ttu-id="6827c-140">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6827c-140">Press F5 to run the application.</span></span>

     <span data-ttu-id="6827c-141">Sie sehen ein geteiltes Formular, das ein Steuerelement enthält, <xref:System.Windows.Forms.TreeView> das Ihr Projektverzeichnis auf der linken Seite anzeigt, und ein <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite mit drei Spalten.</span><span class="sxs-lookup"><span data-stu-id="6827c-141">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="6827c-142">Sie können den <xref:System.Windows.Forms.TreeView> durchlaufen, indem Sie Verzeichnis Knoten auswählen, und <xref:System.Windows.Forms.ListView> wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="6827c-142">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6827c-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6827c-143">Next Steps</span></span>

<span data-ttu-id="6827c-144">Diese Anwendung bietet ein Beispiel dafür, wie Sie und-Steuerelemente gleichzeitig verwenden können <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> .</span><span class="sxs-lookup"><span data-stu-id="6827c-144">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="6827c-145">Weitere Informationen zu diesen Steuerelementen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6827c-145">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="6827c-146">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6827c-146">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="6827c-147">Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6827c-147">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="6827c-148">Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten</span><span class="sxs-lookup"><span data-stu-id="6827c-148">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="6827c-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6827c-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="6827c-150">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6827c-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="6827c-151">Vorgehensweise: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6827c-151">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="6827c-152">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6827c-152">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6827c-153">Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6827c-153">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
