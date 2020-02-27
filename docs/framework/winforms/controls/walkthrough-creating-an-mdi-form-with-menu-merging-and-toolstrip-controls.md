---
title: 'Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628786"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="bd41f-102">Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="bd41f-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="bd41f-103">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="bd41f-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="bd41f-104">MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd41f-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="bd41f-105">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd41f-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="bd41f-106">Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.</span><span class="sxs-lookup"><span data-stu-id="bd41f-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="bd41f-107">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bd41f-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="bd41f-108">Erstellen eines Windows Forms Projekts</span><span class="sxs-lookup"><span data-stu-id="bd41f-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="bd41f-109">Erstellen des Hauptmenüs für das Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-109">Creating the main menu for your form.</span></span> <span data-ttu-id="bd41f-110">Der tatsächliche Name des Menüs ist unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="bd41f-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="bd41f-111">Das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement wird der **Toolbox**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="bd41f-112">Erstellen eines untergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="bd41f-112">Creating a child form.</span></span>

- <span data-ttu-id="bd41f-113">Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelementen durch z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bd41f-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="bd41f-114">Wenn Sie fertig sind, verfügen Sie über ein MDI-Formular, das Zusammenführen von Menüs und verschiebbaren <xref:System.Windows.Forms.ToolStrip> Steuerelementen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="bd41f-115">Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Erstellen eines MDI-Formulars mit der Zusammenführung von Menüs und ToolStrip-Steuerelementen](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="bd41f-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd41f-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bd41f-116">Prerequisites</span></span>

<span data-ttu-id="bd41f-117">Sie benötigen Visual Studio, um diese exemplarische Vorgehensweise abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="bd41f-118">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="bd41f-118">Create the project</span></span>

1. <span data-ttu-id="bd41f-119">Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt mit dem Namen " **MDIForm** " (**Datei** > **neue** > **Projekt** >  **C# Visual** oder **Visual Basic** > **klassischen Desktop** > Windows Forms **Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="bd41f-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="bd41f-120">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="bd41f-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="bd41f-121">Legen Sie in der Eigenschaftenfenster den Wert des <xref:System.Windows.Forms.Form.IsMdiContainer%2A> auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="bd41f-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="bd41f-122">Erstellen des Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="bd41f-122">Create the main menu</span></span>

<span data-ttu-id="bd41f-123">Das übergeordnete MDI-Formular enthält das Hauptmenü.</span><span class="sxs-lookup"><span data-stu-id="bd41f-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="bd41f-124">Das Hauptmenü hat ein Menü Element mit dem Namen **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="bd41f-125">Mit dem Menü Element **Fenster** können Sie untergeordnete Formulare erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="bd41f-126">Menü Elemente aus untergeordneten Formularen werden im Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="bd41f-127">Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der **Toolbox**auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="bd41f-128">Fügen Sie dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement eine <xref:System.Windows.Forms.ToolStripMenuItem> hinzu, und nennen Sie es **Window**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="bd41f-129">Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bd41f-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="bd41f-130">Legen Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> auf `ToolStripMenuItem1`fest.</span><span class="sxs-lookup"><span data-stu-id="bd41f-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="bd41f-131">Fügen Sie dem **Fenster** Menü Element ein Unterelement hinzu, und benennen Sie das Unterelement **neu**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="bd41f-132">Klicken Sie im Eigenschaftenfenster auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="bd41f-133">Doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bd41f-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="bd41f-134">Der Windows Forms-Designer generiert einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bd41f-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="bd41f-135">Fügen Sie den folgenden Code in den-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="bd41f-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="bd41f-136">Fügen Sie das ToolStripPanel-Steuerelement der Toolbox hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd41f-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="bd41f-137">Wenn Sie <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular verwenden, müssen Sie über das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="bd41f-138">Sie müssen das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement der **Toolbox** hinzufügen, um das MDI-Formular im Windows Forms-Designer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="bd41f-139">Öffnen Sie die **Toolbox**, und klicken Sie dann auf die Registerkarte **alle Windows Forms** , um die verfügbaren Windows Forms Steuerelemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="bd41f-140">Klicken Sie mit der rechten Maustaste, um das Kontextmenü zu öffnen, und wählen Sie **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="bd41f-141">Führen Sie im Dialogfeld **Toolbox Elemente auswählen** einen **Bildlauf** nach unten in der Spalte Name aus, bis Sie **ToolStripPanel**gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="bd41f-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="bd41f-142">Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="bd41f-143">Das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement wird in der **Toolbox**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="bd41f-144">Erstellen eines untergeordneten Formulars</span><span class="sxs-lookup"><span data-stu-id="bd41f-144">Create a child form</span></span>

<span data-ttu-id="bd41f-145">In diesem Verfahren definieren Sie eine separate untergeordnete Formular Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip>-Steuerelement verfügt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="bd41f-146">Die Menü Elemente für dieses Formular werden mit denen des übergeordneten Formulars zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="bd41f-147">Fügen Sie dem Projekt ein neues Formular mit dem Namen `ChildForm` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd41f-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="bd41f-148">Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Windows Forms zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bd41f-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="bd41f-149">Ziehen Sie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement aus der **Toolbox**auf das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="bd41f-150">Klicken Sie auf das Designer Aktions Symbol des <xref:System.Windows.Forms.MenuStrip> Steuer Elements (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie dann **Elemente bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd41f-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="bd41f-151">Fügen Sie im Dialogfeld Elementauflistungs- **Editor** dem untergeordneten Menü eine neue <xref:System.Windows.Forms.ToolStripMenuItem> namens **ChildMenuItem** hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd41f-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="bd41f-152">Weitere Informationen finden Sie unter [ToolStrip Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))-Auflistungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="bd41f-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="bd41f-153">Testen des Formulars</span><span class="sxs-lookup"><span data-stu-id="bd41f-153">Test the form</span></span>

1. <span data-ttu-id="bd41f-154">Drücken Sie **F5** , um das Formular zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="bd41f-155">Klicken Sie auf das Menü Element **Fenster** , um das Menü zu öffnen, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="bd41f-156">Im MDI-Client Bereich des Formulars wird ein neues untergeordnetes Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="bd41f-157">Das Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="bd41f-158">Schließen Sie das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-158">Close the child form.</span></span>

     <span data-ttu-id="bd41f-159">Das Menü des untergeordneten Formulars wird aus dem Hauptmenü entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="bd41f-160">Klicken Sie mehrmals auf **neu** .</span><span class="sxs-lookup"><span data-stu-id="bd41f-160">Click **New** several times.</span></span>

     <span data-ttu-id="bd41f-161">Die untergeordneten Formulare werden automatisch unter dem Menü Element **Fenster** aufgeführt, da die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip>-Steuer Elements zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bd41f-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="bd41f-162">ToolStrip-Unterstützung hinzufügen</span><span class="sxs-lookup"><span data-stu-id="bd41f-162">Add ToolStrip support</span></span>

<span data-ttu-id="bd41f-163">In diesem Verfahren fügen Sie dem übergeordneten MDI-Formular vier <xref:System.Windows.Forms.ToolStrip>-Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd41f-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="bd41f-164">Jedes <xref:System.Windows.Forms.ToolStrip> Steuerelement wird in einem <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement hinzugefügt, das an den Rand des Formulars angedockt wird.</span><span class="sxs-lookup"><span data-stu-id="bd41f-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="bd41f-165">Ziehen Sie ein <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement aus der **Toolbox**auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="bd41f-166">Wenn das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement ausgewählt ist, doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStrip>-Steuerelement in der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="bd41f-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="bd41f-167">Ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement wird im <xref:System.Windows.Forms.ToolStripPanel> Steuerelement erstellt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="bd41f-168">Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bd41f-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="bd41f-169">Ändern Sie in der Eigenschaftenfenster den Wert der Eigenschaft <xref:System.Windows.Forms.Control.Dock%2A> des Steuer Elements in <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="bd41f-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="bd41f-170">Das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird auf der linken Seite des Formulars unterhalb des Hauptmenü andocken.</span><span class="sxs-lookup"><span data-stu-id="bd41f-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="bd41f-171">Die Größe des MDI-Client Bereichs wird an das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angepasst.</span><span class="sxs-lookup"><span data-stu-id="bd41f-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="bd41f-172">Wiederholen Sie die Schritte 1 bis 4.</span><span class="sxs-lookup"><span data-stu-id="bd41f-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="bd41f-173">Docken Sie das neue <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement am oberen Rand des Formulars an.</span><span class="sxs-lookup"><span data-stu-id="bd41f-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="bd41f-174">Das <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird unter dem Hauptmenü angedockt, aber auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="bd41f-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="bd41f-175">Dieser Schritt veranschaulicht, wie wichtig die z-Reihenfolge bei der ordnungsgemäßen Positionierung <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente ist.</span><span class="sxs-lookup"><span data-stu-id="bd41f-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="bd41f-176">Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel>-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="bd41f-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="bd41f-177">Andocken der neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente rechts und unten im Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="bd41f-178">ToolStripPanel-Steuerelemente nach Z-Reihenfolge anordnen</span><span class="sxs-lookup"><span data-stu-id="bd41f-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="bd41f-179">Die Position eines angedockten <xref:System.Windows.Forms.ToolStripPanel>-Steuer Elements auf dem MDI-Formular hängt von der Position des Steuer Elements in der z-Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="bd41f-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="bd41f-180">Sie können die z-Reihenfolge der Steuerelemente im Fenster "Dokument Gliederung" problemlos anordnen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="bd41f-181">Klicken Sie im Menü **Ansicht** auf **Weitere Fenster**, und klicken Sie dann auf **Dokument**Gliederung.</span><span class="sxs-lookup"><span data-stu-id="bd41f-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="bd41f-182">Die Anordnung Ihrer <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus der vorherigen Prozedur entspricht nicht dem Standard.</span><span class="sxs-lookup"><span data-stu-id="bd41f-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="bd41f-183">Dies liegt daran, dass die z-Reihenfolge nicht korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="bd41f-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="bd41f-184">Verwenden Sie das Fenster Dokument Gliederung, um die z-Reihenfolge der Steuerelemente zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bd41f-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="bd41f-185">Wählen Sie im Fenster Dokument Gliederung die Option **ToolStripPanel4**aus.</span><span class="sxs-lookup"><span data-stu-id="bd41f-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="bd41f-186">Klicken Sie wiederholt auf die Schaltfläche mit dem Pfeil nach unten, bis sich **ToolStripPanel4** am Ende der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="bd41f-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="bd41f-187">Das **ToolStripPanel4** -Steuerelement wird am unteren Rand des Formulars unterhalb der anderen Steuerelemente angedockt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="bd41f-188">Wählen Sie **ToolStripPanel2**aus.</span><span class="sxs-lookup"><span data-stu-id="bd41f-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="bd41f-189">Klicken Sie einmal auf die Schaltfläche mit dem Pfeil nach unten, um das dritte Steuerelement in der Liste zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="bd41f-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="bd41f-190">Das **ToolStripPanel2** -Steuerelement wird am oberen Rand des Formulars unterhalb des Hauptmenü und über den anderen Steuerelementen angedockt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="bd41f-191">Wählen Sie im **Dokument** Gliederungs Fenster verschiedene Steuerelemente aus, und verschieben Sie Sie an verschiedene Positionen in der z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bd41f-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="bd41f-192">Beachten Sie die Auswirkung der z-Reihenfolge auf die Platzierung von angedockten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="bd41f-193">Verwenden Sie STRG + Z oder **Rückgängig** im Menü **Bearbeiten** , um die Änderungen rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="bd41f-194">Prüfpunkt: Testen des Formulars</span><span class="sxs-lookup"><span data-stu-id="bd41f-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="bd41f-195">Drücken Sie **F5** , um das Formular zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="bd41f-196">Klicken Sie auf den Ziehpunkt eines <xref:System.Windows.Forms.ToolStrip> Steuer Elements, und ziehen Sie das Steuerelement an verschiedene Positionen im Formular.</span><span class="sxs-lookup"><span data-stu-id="bd41f-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="bd41f-197">Sie können ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement zu einem anderen ziehen.</span><span class="sxs-lookup"><span data-stu-id="bd41f-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd41f-198">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bd41f-198">Next steps</span></span>

<span data-ttu-id="bd41f-199">In dieser exemplarischen Vorgehensweise haben Sie ein übergeordnetes MDI-Formular mit <xref:System.Windows.Forms.ToolStrip>-Steuerelementen und der Zusammenführung des Menüs erstellt.</span><span class="sxs-lookup"><span data-stu-id="bd41f-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="bd41f-200">Die <xref:System.Windows.Forms.ToolStrip>-Steuerelement Familie kann für viele andere Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bd41f-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="bd41f-201">Erstellen Sie Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="bd41f-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="bd41f-202">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bd41f-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="bd41f-203">Erstellt ein Formular mit einem automatisch ausgefüllten Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="bd41f-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="bd41f-204">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Bereitstellen von Standard Menü Elementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="bd41f-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="bd41f-205">Legen Sie für Ihre <xref:System.Windows.Forms.ToolStrip> Steuerelemente ein professionelles Erscheinungsbild.</span><span class="sxs-lookup"><span data-stu-id="bd41f-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="bd41f-206">Weitere Informationen finden Sie unter Gewusst [wie: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="bd41f-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd41f-207">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd41f-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="bd41f-208">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="bd41f-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="bd41f-209">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="bd41f-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="bd41f-210">Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü</span><span class="sxs-lookup"><span data-stu-id="bd41f-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="bd41f-211">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bd41f-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
