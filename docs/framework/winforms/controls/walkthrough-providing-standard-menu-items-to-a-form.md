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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211503"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="ec8cd-102">Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="ec8cd-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="ec8cd-103">Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="ec8cd-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit einem <xref:System.Windows.Forms.MenuStrip> Steuerelement an ein Standardmenü zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="ec8cd-105">Das Formular reagiert auch auf, wenn ein Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="ec8cd-106">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ec8cd-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="ec8cd-107">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="ec8cd-108">Erstellen ein Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-108">Creating a standard menu.</span></span>

- <span data-ttu-id="ec8cd-109">Erstellen einer <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="ec8cd-110">Behandeln von Menüauswahl-Element.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-110">Handling menu item selection.</span></span>

<span data-ttu-id="ec8cd-111">Wenn Sie fertig sind, haben Sie ein Formular mit Standardmenü, die die Auswahl von Menüelementen in zeigt eine <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="ec8cd-112">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="ec8cd-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec8cd-113">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ec8cd-113">Prerequisites</span></span>

<span data-ttu-id="ec8cd-114">Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ec8cd-115">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="ec8cd-115">Create the project</span></span>

1. <span data-ttu-id="ec8cd-116">Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt namens **StandardMenuForm** (**Datei** > **neu** > **Projekt**   >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop**  >  **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="ec8cd-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="ec8cd-117">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="ec8cd-118">Erstellen Sie ein Standardmenü</span><span class="sxs-lookup"><span data-stu-id="ec8cd-118">Create a standard menu</span></span>

<span data-ttu-id="ec8cd-119">Der Windows Forms-Designer können automatisch Auffüllen einer <xref:System.Windows.Forms.MenuStrip> -Steuerelement mit Standardmenüelementen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="ec8cd-120">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="ec8cd-121">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Standardelemente einfügen**.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="ec8cd-122">Die <xref:System.Windows.Forms.MenuStrip> Steuerelement mit Standardmenüelemente gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="ec8cd-123">Klicken Sie auf die **Datei** Menüelement, um die Standard-Menüelemente und entsprechende Symbole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="ec8cd-124">Erstellen Sie ein StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ec8cd-124">Create a StatusStrip control</span></span>

<span data-ttu-id="ec8cd-125">Verwenden der <xref:System.Windows.Forms.StatusStrip> -Steuerelement zum Anzeigen des Status Ihrer Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="ec8cd-126">Im aktuellen Beispiel-Menüelemente, die vom Benutzer ausgewählten werden angezeigt, einem <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="ec8cd-127">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.StatusStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="ec8cd-128">Die <xref:System.Windows.Forms.StatusStrip> Steuerelement wird automatisch am unteren Rand des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="ec8cd-129">Klicken Sie auf die <xref:System.Windows.Forms.StatusStrip> Dropdown-Schaltfläche des Steuerelements, und wählen **StatusLabel** Hinzufügen einer <xref:System.Windows.Forms.ToolStripStatusLabel> die Steuerung an die <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="ec8cd-130">Behandeln Sie die Auswahl von Listenelementen</span><span class="sxs-lookup"><span data-stu-id="ec8cd-130">Handle item selection</span></span>

<span data-ttu-id="ec8cd-131">Behandeln der <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis reagieren, wenn der Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="ec8cd-132">Klicken Sie auf die **Datei** Menüelement, das Sie in der erstellen erstellt ein Standardmenü-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="ec8cd-133">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="ec8cd-134">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="ec8cd-135">Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="ec8cd-136">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="ec8cd-137">Fügen Sie der `UpdateStatus` Definition des Hilfsprogramm-Methode in das Formular.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="ec8cd-138">Prüfpunkt-testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="ec8cd-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="ec8cd-139">Drücken Sie **F5** zum Kompilieren und führen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="ec8cd-140">Klicken Sie auf die **Datei** Menüelement, um das Menü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="ec8cd-141">Auf der **Datei** Menü klicken Sie auf eines der Elemente, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="ec8cd-142">Die <xref:System.Windows.Forms.StatusStrip> Steuerelement zeigt das ausgewählte Element.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec8cd-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ec8cd-143">Next steps</span></span>

<span data-ttu-id="ec8cd-144">In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit Standardmenü erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="ec8cd-145">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="ec8cd-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="ec8cd-146">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="ec8cd-147">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ec8cd-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="ec8cd-148">Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="ec8cd-149">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ec8cd-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="ec8cd-150">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="ec8cd-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="ec8cd-151">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="ec8cd-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec8cd-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec8cd-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="ec8cd-153">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ec8cd-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
