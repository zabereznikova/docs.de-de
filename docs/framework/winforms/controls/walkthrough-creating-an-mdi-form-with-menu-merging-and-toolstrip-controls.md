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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211560"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="e7619-102">Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e7619-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="e7619-103">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="e7619-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="e7619-104">MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7619-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="e7619-105">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="e7619-106">Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.</span><span class="sxs-lookup"><span data-stu-id="e7619-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="e7619-107">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e7619-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="e7619-108">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="e7619-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="e7619-109">Erstellen im Hauptmenü für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-109">Creating the main menu for your form.</span></span> <span data-ttu-id="e7619-110">Der tatsächliche Name des Menüs variieren.</span><span class="sxs-lookup"><span data-stu-id="e7619-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="e7619-111">Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="e7619-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="e7619-112">Erstellen ein untergeordnetes Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-112">Creating a child form.</span></span>

- <span data-ttu-id="e7619-113">Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7619-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="e7619-114">Wenn Sie fertig sind, haben Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e7619-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="e7619-115">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e7619-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7619-116">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e7619-116">Prerequisites</span></span>

<span data-ttu-id="e7619-117">Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="e7619-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e7619-118">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="e7619-118">Create the project</span></span>

1. <span data-ttu-id="e7619-119">Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt namens **MDI-Formulars** (**Datei** > **neu** > **Projekt**  >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop**  >   **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="e7619-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="e7619-120">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="e7619-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="e7619-121">Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> zu `true`.</span><span class="sxs-lookup"><span data-stu-id="e7619-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="e7619-122">Erstellen Sie im Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="e7619-122">Create the main menu</span></span>

<span data-ttu-id="e7619-123">Das übergeordnete MDI-Formular enthält das Hauptmenü.</span><span class="sxs-lookup"><span data-stu-id="e7619-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="e7619-124">Das Hauptmenü befindet sich ein Element mit dem Namen **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="e7619-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="e7619-125">Mit der **Fenster** Menüelement, können Sie untergeordnete Formulare erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7619-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="e7619-126">Menüelemente, die aus untergeordneten Formulare werden in das Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e7619-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="e7619-127">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="e7619-128">Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="e7619-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="e7619-129">Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="e7619-130">Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="e7619-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="e7619-131">Fügen Sie ein Unterelement, das **Fenster** Menüelement, und nennen Sie das Unterelement **neu**.</span><span class="sxs-lookup"><span data-stu-id="e7619-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="e7619-132">Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="e7619-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="e7619-133">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e7619-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="e7619-134">Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e7619-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="e7619-135">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="e7619-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="e7619-136">Fügen Sie das ToolStripPanel-Steuerelement zur Toolbox</span><span class="sxs-lookup"><span data-stu-id="e7619-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="e7619-137">Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular, das Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="e7619-138">Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** das MDI-Formular im Windows Forms-Designer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7619-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="e7619-139">Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e7619-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="e7619-140">Mit der rechten Maustaste das Kontextmenü öffnen, und wählen **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="e7619-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="e7619-141">In der **Toolboxelemente auswählen** (Dialogfeld), führen Sie einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="e7619-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="e7619-142">Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7619-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="e7619-143">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angezeigt wird, der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="e7619-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="e7619-144">Erstellen Sie ein untergeordnetes Formular</span><span class="sxs-lookup"><span data-stu-id="e7619-144">Create a child form</span></span>

<span data-ttu-id="e7619-145">In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="e7619-146">Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e7619-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="e7619-147">Hinzufügen eines neuen Formulars mit dem Namen `ChildForm` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="e7619-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="e7619-148">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Windows Forms zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7619-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="e7619-149">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="e7619-150">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e7619-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="e7619-151">In der **-Elementauflistungs-Editor** Dialogfeld hinzu, und ein neues <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf das Menü des untergeordneten.</span><span class="sxs-lookup"><span data-stu-id="e7619-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="e7619-152">Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7619-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="e7619-153">Testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="e7619-153">Test the form</span></span>

1. <span data-ttu-id="e7619-154">Drücken Sie **F5** zum Kompilieren und führen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="e7619-155">Klicken Sie auf die **Fenster** Menüelement öffnen Sie das Menü, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="e7619-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="e7619-156">Ein neues untergeordnetes Formular wird in den MDI-Clientbereichs des Formulars erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7619-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="e7619-157">Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="e7619-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="e7619-158">Schließen Sie das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-158">Close the child form.</span></span>

     <span data-ttu-id="e7619-159">Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.</span><span class="sxs-lookup"><span data-stu-id="e7619-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="e7619-160">Klicken Sie auf **neu** mehrmals.</span><span class="sxs-lookup"><span data-stu-id="e7619-160">Click **New** several times.</span></span>

     <span data-ttu-id="e7619-161">Die untergeordneten Formulare werden automatisch aufgelistet, unter der **Fenster** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> -Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e7619-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="e7619-162">Hinzufügen von ToolStrip-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="e7619-162">Add ToolStrip support</span></span>

<span data-ttu-id="e7619-163">In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente an das übergeordnete MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="e7619-164">Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement wird hinzugefügt, in einem <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das den Rand des Formulars angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="e7619-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="e7619-165">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="e7619-166">Mit der <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement ausgewählt ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="e7619-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="e7619-167">Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="e7619-168">Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="e7619-169">Ändern Sie im Eigenschaftenfenster den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="e7619-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="e7619-170">Die <xref:System.Windows.Forms.ToolStripPanel> steuern, wird an der linken Seite des Formulars wird unterhalb des Hauptmenüs angedockt.</span><span class="sxs-lookup"><span data-stu-id="e7619-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="e7619-171">Wird die Größe des MDI-Client-Bereichs angepasst der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="e7619-172">Wiederholen Sie die Schritte 1 bis 4.</span><span class="sxs-lookup"><span data-stu-id="e7619-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="e7619-173">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="e7619-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="e7619-174">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist, unterhalb des Hauptmenüs, sondern auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="e7619-175">Dieser Schritt veranschaulicht, die Bedeutung der Z-Reihenfolge bei der Positionierung ordnungsgemäß <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e7619-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="e7619-176">Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e7619-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="e7619-177">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente am rechten und unteren Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="e7619-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="e7619-178">ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen</span><span class="sxs-lookup"><span data-stu-id="e7619-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="e7619-179">Die Position des angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement auf dem MDI-Formular richtet sich nach der die Position des Steuerelements in der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7619-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="e7619-180">Sie können problemlos die Z-Reihenfolge der Steuerelemente in das Fenster "Dokumentgliederung" anordnen.</span><span class="sxs-lookup"><span data-stu-id="e7619-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="e7619-181">In der **Ansicht** Menü klicken Sie auf **Other Windows**, und klicken Sie dann auf **Dokumentgliederung**.</span><span class="sxs-lookup"><span data-stu-id="e7619-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="e7619-182">Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus dem vorherigen Verfahren entspricht nicht dem Standard.</span><span class="sxs-lookup"><span data-stu-id="e7619-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="e7619-183">Dies ist, da die Z-Reihenfolge nicht korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="e7619-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="e7619-184">Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="e7619-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="e7619-185">Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="e7619-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="e7619-186">Klicken Sie auf den Pfeil nach unten-Schaltfläche wiederholt, bis **ToolStripPanel4** wird am unteren Rand der Liste.</span><span class="sxs-lookup"><span data-stu-id="e7619-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="e7619-187">Die **ToolStripPanel4** Steuerelement am unteren Rand unter den anderen Steuerelementen im Formular angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="e7619-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="e7619-188">Wählen Sie **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="e7619-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="e7619-189">Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, dritte Positionieren des Steuerelements in der Liste.</span><span class="sxs-lookup"><span data-stu-id="e7619-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="e7619-190">Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="e7619-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="e7619-191">Wählen Sie verschiedene Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7619-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="e7619-192">Beachten Sie die Auswirkungen der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e7619-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="e7619-193">Verwenden Sie STRG + Z oder **Rückgängig** auf die **bearbeiten** Menü, um Ihre Änderungen rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="e7619-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="e7619-194">Prüfpunkt - testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="e7619-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="e7619-195">Drücken Sie **F5** zum Kompilieren und führen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="e7619-196">Klicken Sie auf den Ziehpunkt einer <xref:System.Windows.Forms.ToolStrip> steuern, und ziehen Sie das Steuerelement an anderen Positionen auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="e7619-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="e7619-197">Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e7619-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7619-198">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e7619-198">Next steps</span></span>

<span data-ttu-id="e7619-199">In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="e7619-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="e7619-200">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="e7619-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="e7619-201">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="e7619-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="e7619-202">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e7619-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="e7619-203">Ein Formular erstellt mit einem automatisch angegebenen Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="e7619-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="e7619-204">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="e7619-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="e7619-205">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="e7619-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="e7619-206">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="e7619-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7619-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7619-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e7619-208">Vorgehensweise: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="e7619-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="e7619-209">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="e7619-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="e7619-210">Vorgehensweise: Einfügen eines MenuStrip in ein MDI-Dropdownmenü</span><span class="sxs-lookup"><span data-stu-id="e7619-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="e7619-211">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e7619-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
