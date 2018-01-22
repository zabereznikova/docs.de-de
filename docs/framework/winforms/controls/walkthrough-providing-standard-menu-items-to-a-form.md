---
title: "Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89089617a62ab079dd4cccf3ddf6e1e774bac8ba
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="dec97-102">Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="dec97-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="dec97-103">Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dec97-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="dec97-104">Diese exemplarische Vorgehensweise veranschaulicht, wie ein <xref:System.Windows.Forms.MenuStrip> Steuerelement ein Standardmenü erstellt.</span><span class="sxs-lookup"><span data-stu-id="dec97-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="dec97-105">Das Formular reagiert auch auf, wenn ein Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="dec97-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="dec97-106">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="dec97-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="dec97-107">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="dec97-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="dec97-108">Erstellen ein Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="dec97-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="dec97-109">Erstellen einer <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="dec97-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="dec97-110">Behandlung von Menüauswahl-Element.</span><span class="sxs-lookup"><span data-stu-id="dec97-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="dec97-111">Wenn Sie fertig sind, haben Sie ein Formular mit Standardmenü, die Menüelementauswahlen in zeigt ein <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="dec97-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="dec97-112">Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="dec97-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dec97-113">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="dec97-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dec97-114">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="dec97-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dec97-115">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="dec97-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dec97-116">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="dec97-116">Prerequisites</span></span>  
 <span data-ttu-id="dec97-117">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dec97-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="dec97-118">Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="dec97-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="dec97-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="dec97-119">Creating the Project</span></span>  
 <span data-ttu-id="dec97-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dec97-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="dec97-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="dec97-121">To create the project</span></span>  
  
1.  <span data-ttu-id="dec97-122">Erstellen Sie ein Windows-Anwendungsprojekt namens **StandardMenuForm**.</span><span class="sxs-lookup"><span data-stu-id="dec97-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="dec97-123">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="dec97-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="dec97-124">Wählen Sie in der Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="dec97-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="dec97-125">Erstellen ein Standardmenü</span><span class="sxs-lookup"><span data-stu-id="dec97-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="dec97-126">Windows Forms-Designer automatisch Auffüllen einer <xref:System.Windows.Forms.MenuStrip> -Steuerelement mit Standardmenüelementen.</span><span class="sxs-lookup"><span data-stu-id="dec97-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="dec97-127">So erstellen Sie ein Standardmenü</span><span class="sxs-lookup"><span data-stu-id="dec97-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="dec97-128">Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dec97-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="dec97-129">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Standardelemente einfügen**.</span><span class="sxs-lookup"><span data-stu-id="dec97-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="dec97-130">Die <xref:System.Windows.Forms.MenuStrip> Steuerelement mit der Standardmenüelementen gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="dec97-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="dec97-131">Klicken Sie auf die **Datei** Menüelement, um die Standard-Menüelemente und entsprechende Symbole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dec97-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="dec97-132">Erstellen ein StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dec97-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="dec97-133">Verwenden der <xref:System.Windows.Forms.StatusStrip> -Steuerelement zum Anzeigen des Status für Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="dec97-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="dec97-134">Im aktuellen Beispiel Menüelemente, die vom Benutzer ausgewählten angezeigt werden, einem <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="dec97-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="dec97-135">So erstellen ein StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dec97-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="dec97-136">Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.StatusStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="dec97-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="dec97-137">Die <xref:System.Windows.Forms.StatusStrip> Steuerelement wird automatisch an das Ende des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="dec97-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="dec97-138">Klicken Sie auf die <xref:System.Windows.Forms.StatusStrip> des Steuerelements Dropdown-Schaltfläche und wählen Sie **StatusLabel** Hinzufügen einer <xref:System.Windows.Forms.ToolStripStatusLabel> die Steuerung an die <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="dec97-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="dec97-139">Behandlung Elementauswahl</span><span class="sxs-lookup"><span data-stu-id="dec97-139">Handling Item Selection</span></span>  
 <span data-ttu-id="dec97-140">Behandeln der <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis reagiert, wenn der Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="dec97-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="dec97-141">Elementauswahl behandeln</span><span class="sxs-lookup"><span data-stu-id="dec97-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="dec97-142">Klicken Sie auf die **Datei** Menüelement, das Sie in der erstellen erstellt ein Standardmenü-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="dec97-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="dec97-143">In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="dec97-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="dec97-144">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dec97-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="dec97-145">Windows Forms-Designer wird ein Ereignishandler für das <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dec97-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="dec97-146">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="dec97-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="dec97-147">Fügen Sie der `UpdateStatus` Hilfsprogramm Methodendefinition in das Formular.</span><span class="sxs-lookup"><span data-stu-id="dec97-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="dec97-148">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="dec97-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="dec97-149">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="dec97-149">To test your form</span></span>  
  
1.  <span data-ttu-id="dec97-150">Drücken Sie F5, um zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="dec97-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="dec97-151">Klicken Sie auf die **Datei** Menüelement, um das Menü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dec97-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="dec97-152">Auf der **Datei** Menü klicken Sie auf eines der Elemente, um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="dec97-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="dec97-153">Die <xref:System.Windows.Forms.StatusStrip> -Steuerelement zeigt das ausgewählte Element.</span><span class="sxs-lookup"><span data-stu-id="dec97-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dec97-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dec97-154">Next Steps</span></span>  
 <span data-ttu-id="dec97-155">In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit Standardmenü erstellt.</span><span class="sxs-lookup"><span data-stu-id="dec97-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="dec97-156">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="dec97-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="dec97-157">Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dec97-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="dec97-158">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="dec97-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="dec97-159">Erstellen Sie ein Formular der multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="dec97-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="dec97-160">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="dec97-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="dec97-161">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="dec97-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="dec97-162">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="dec97-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec97-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dec97-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="dec97-164">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dec97-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
