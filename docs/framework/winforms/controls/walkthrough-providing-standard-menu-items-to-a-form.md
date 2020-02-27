---
title: 'Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628773"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="dce72-102">Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="dce72-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="dce72-103">Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dce72-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="dce72-104">Diese exemplarische Vorgehensweise veranschaulicht, wie ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement verwendet wird, um ein Standardmenü zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dce72-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="dce72-105">Das Formular antwortet auch, wenn ein Benutzer ein Menü Element auswählt.</span><span class="sxs-lookup"><span data-stu-id="dce72-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="dce72-106">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="dce72-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="dce72-107">Erstellen eines Windows Forms Projekts</span><span class="sxs-lookup"><span data-stu-id="dce72-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="dce72-108">Erstellen eines Standardmenüs.</span><span class="sxs-lookup"><span data-stu-id="dce72-108">Creating a standard menu.</span></span>

- <span data-ttu-id="dce72-109">Erstellen eines <xref:System.Windows.Forms.StatusStrip>-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="dce72-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="dce72-110">Menü Elementauswahl wird verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dce72-110">Handling menu item selection.</span></span>

<span data-ttu-id="dce72-111">Wenn Sie fertig sind, verfügen Sie über ein Formular mit einem Standardmenü, in dem eine Menü Elementauswahl in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dce72-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="dce72-112">Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Bereitstellen von Standard Menü Elementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="dce72-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dce72-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dce72-113">Prerequisites</span></span>

<span data-ttu-id="dce72-114">Sie benötigen Visual Studio, um diese exemplarische Vorgehensweise abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="dce72-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="dce72-115">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="dce72-115">Create the project</span></span>

1. <span data-ttu-id="dce72-116">Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt mit dem Namen **StandardMenuForm** (**Datei** > **Neues** > **Projekt** > **Visual C#**  oder **Visual Basic** >  > **Anwendung**für die **klassische Desktop** Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="dce72-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="dce72-117">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="dce72-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="dce72-118">Standardmenü erstellen</span><span class="sxs-lookup"><span data-stu-id="dce72-118">Create a standard menu</span></span>

<span data-ttu-id="dce72-119">Der Windows Forms-Designer kann ein <xref:System.Windows.Forms.MenuStrip> Steuerelement automatisch mit Standardmenü Elementen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="dce72-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="dce72-120">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dce72-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="dce72-121">Klicken Sie auf das Symbol für Designer Aktionen des <xref:System.Windows.Forms.MenuStrip> Steuer Elements (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie **Standard Elemente einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="dce72-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="dce72-122">Das <xref:System.Windows.Forms.MenuStrip> Steuerelement wird mit den Standardmenü Elementen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="dce72-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="dce72-123">Klicken Sie auf das Menü Element **Datei** , um die Standardmenü Elemente und zugehörige Symbole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dce72-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="dce72-124">Erstellen eines Status Strip-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="dce72-124">Create a StatusStrip control</span></span>

<span data-ttu-id="dce72-125">Verwenden Sie das <xref:System.Windows.Forms.StatusStrip>-Steuerelement, um den Status Ihrer Windows Forms-Anwendungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dce72-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="dce72-126">Im aktuellen Beispiel werden Menü Elemente, die vom Benutzer ausgewählt werden, in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dce72-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="dce72-127">Ziehen Sie aus der **Toolbox**ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dce72-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="dce72-128">Das <xref:System.Windows.Forms.StatusStrip>-Steuerelement wird automatisch am Ende des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="dce72-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="dce72-129">Klicken Sie auf die Dropdown Schaltfläche des <xref:System.Windows.Forms.StatusStrip> Steuer Elements, und wählen Sie **Status Label** aus, um dem <xref:System.Windows.Forms.StatusStrip> Steuerelement ein <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dce72-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="dce72-130">Elementauswahl behandeln</span><span class="sxs-lookup"><span data-stu-id="dce72-130">Handle item selection</span></span>

<span data-ttu-id="dce72-131">Behandeln Sie das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis, um zu reagieren, wenn der Benutzer ein Menü Element auswählt.</span><span class="sxs-lookup"><span data-stu-id="dce72-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="dce72-132">Klicken Sie auf das Menü Element **Datei** , das Sie im Abschnitt Erstellen eines Standard Menüs erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dce72-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="dce72-133">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="dce72-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="dce72-134">Doppelklicken Sie auf das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dce72-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="dce72-135">Der Windows Forms-Designer generiert einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dce72-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="dce72-136">Fügen Sie den folgenden Code in den-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="dce72-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="dce72-137">Fügen Sie die Methoden Definition des `UpdateStatus`-Hilfsprogramms in das Formular ein.</span><span class="sxs-lookup"><span data-stu-id="dce72-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="dce72-138">Prüfpunkt: Testen des Formulars</span><span class="sxs-lookup"><span data-stu-id="dce72-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="dce72-139">Drücken Sie **F5** , um das Formular zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dce72-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="dce72-140">Klicken Sie auf das Menü Element **Datei** , um das Menü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dce72-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="dce72-141">Klicken Sie im Menü **Datei** auf eines der Elemente, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dce72-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="dce72-142">Das <xref:System.Windows.Forms.StatusStrip>-Steuerelement zeigt das ausgewählte Element an.</span><span class="sxs-lookup"><span data-stu-id="dce72-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dce72-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dce72-143">Next steps</span></span>

<span data-ttu-id="dce72-144">In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit einem Standardmenü erstellt.</span><span class="sxs-lookup"><span data-stu-id="dce72-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="dce72-145">Die <xref:System.Windows.Forms.ToolStrip>-Steuerelement Familie kann für viele andere Zwecke verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="dce72-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="dce72-146">Erstellen Sie Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dce72-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="dce72-147">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="dce72-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="dce72-148">Erstellen eines MDI-Formulars (Multiple Document Interface) mit Andocken <xref:System.Windows.Forms.ToolStrip> Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="dce72-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="dce72-149">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines MDI-Formulars mit der Zusammenführung von Menüs und ToolStrip-Steuerelementen](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="dce72-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="dce72-150">Legen Sie für Ihre <xref:System.Windows.Forms.ToolStrip> Steuerelemente ein professionelles Erscheinungsbild.</span><span class="sxs-lookup"><span data-stu-id="dce72-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="dce72-151">Weitere Informationen finden Sie unter Gewusst [wie: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="dce72-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dce72-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dce72-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="dce72-153">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dce72-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
