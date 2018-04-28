---
title: 'Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc8214815beb0eac6fe3811ba198207a06ee1a9a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="374b5-102">Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="374b5-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="374b5-103">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="374b5-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="374b5-104">MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="374b5-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="374b5-105">Diese exemplarische Vorgehensweise veranschaulicht, wie <xref:System.Windows.Forms.ToolStripPanel> -Steuerelemente mit einem MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="374b5-106">Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.</span><span class="sxs-lookup"><span data-stu-id="374b5-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="374b5-107">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="374b5-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="374b5-108">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="374b5-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="374b5-109">Erstellen im Hauptmenü für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-109">Creating the main menu for your form.</span></span> <span data-ttu-id="374b5-110">Der tatsächliche Name des Menüs variiert.</span><span class="sxs-lookup"><span data-stu-id="374b5-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="374b5-111">Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="374b5-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="374b5-112">Erstellen eines untergeordneten Formulars an.</span><span class="sxs-lookup"><span data-stu-id="374b5-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="374b5-113">Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="374b5-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="374b5-114">Wenn Sie fertig sind, müssen Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="374b5-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="374b5-115">Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="374b5-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="374b5-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="374b5-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="374b5-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="374b5-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="374b5-118">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="374b5-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="374b5-119">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="374b5-119">Prerequisites</span></span>  
 <span data-ttu-id="374b5-120">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="374b5-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="374b5-121">Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="374b5-122">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="374b5-122">Creating the Project</span></span>  
 <span data-ttu-id="374b5-123">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="374b5-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="374b5-124">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="374b5-124">To create the project</span></span>  
  
1.  <span data-ttu-id="374b5-125">Erstellen Sie ein Windows-Anwendungsprojekt namens **MDI-Formulars**.</span><span class="sxs-lookup"><span data-stu-id="374b5-125">Create a Windows Application project called **MdiForm**.</span></span>  
  
     <span data-ttu-id="374b5-126">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="374b5-126">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="374b5-127">Wählen Sie in der Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="374b5-127">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="374b5-128">Legen Sie im Fenster Eigenschaften den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> auf `true`.</span><span class="sxs-lookup"><span data-stu-id="374b5-128">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="374b5-129">Erstellen Sie im Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="374b5-129">Creating the Main Menu</span></span>  
 <span data-ttu-id="374b5-130">Das übergeordnete MDI-Formular enthält das Hauptmenü.</span><span class="sxs-lookup"><span data-stu-id="374b5-130">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="374b5-131">Im Hauptmenü befindet sich ein Element mit dem Namen **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="374b5-131">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="374b5-132">Mit der **Fenster** Menüelement klicken, können Sie untergeordnete Formulare erstellen.</span><span class="sxs-lookup"><span data-stu-id="374b5-132">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="374b5-133">Menüelemente von untergeordneten Formularen werden im Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="374b5-133">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="374b5-134">So erstellen im Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="374b5-134">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="374b5-135">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="374b5-136">Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="374b5-136">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="374b5-137">Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-137">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="374b5-138">Legen Sie im Fenster Eigenschaften den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="374b5-138">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="374b5-139">Fügen Sie ein Unterelement, das **Fenster** Menüelement, und geben Sie den Namen des Unterelements **neu**.</span><span class="sxs-lookup"><span data-stu-id="374b5-139">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="374b5-140">Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="374b5-140">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="374b5-141">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="374b5-141">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="374b5-142">Windows Forms-Designer wird ein Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="374b5-142">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="374b5-143">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="374b5-143">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="374b5-144">ToolStripPanel-Steuerelement hinzufügen zur Toolbox</span><span class="sxs-lookup"><span data-stu-id="374b5-144">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="374b5-145">Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> -Steuerelemente mit einem MDI-Formular Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-145">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="374b5-146">Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** der MDI-Formulars in Windows Forms-Designer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="374b5-146">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="374b5-147">So fügen Sie das ToolStripPanel-Steuerelement zur Toolbox hinzu</span><span class="sxs-lookup"><span data-stu-id="374b5-147">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="374b5-148">Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente zeigen.</span><span class="sxs-lookup"><span data-stu-id="374b5-148">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="374b5-149">Mit der rechten Maustaste das Kontextmenü öffnen, und wählen Sie **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="374b5-149">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="374b5-150">In der **Toolboxelemente** (Dialogfeld), einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="374b5-150">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="374b5-151">Wählen Sie das Kontrollkästchen **ToolStripPanel**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="374b5-151">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="374b5-152">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement wird in der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="374b5-152">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="374b5-153">Erstellen eines untergeordneten Formulars</span><span class="sxs-lookup"><span data-stu-id="374b5-153">Creating a Child Form</span></span>  
 <span data-ttu-id="374b5-154">In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-154">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="374b5-155">Die Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="374b5-155">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="374b5-156">Um eine untergeordnete Formular zu definieren.</span><span class="sxs-lookup"><span data-stu-id="374b5-156">To define a child form</span></span>  
  
1.  <span data-ttu-id="374b5-157">Fügen Sie ein neues Formular mit dem Namen `ChildForm` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="374b5-157">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="374b5-158">Weitere Informationen finden Sie unter [wie: Hinzufügen von Windows Forms zu einem Projekt](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="374b5-158">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="374b5-159">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-159">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="374b5-160">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="374b5-160">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="374b5-161">In der **-Elementauflistungs-Editor** Dialogfeld Feld, fügen Sie einen neuen <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf dem untergeordneten-Menü.</span><span class="sxs-lookup"><span data-stu-id="374b5-161">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="374b5-162">Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="374b5-162">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="374b5-163">Testen das Formular</span><span class="sxs-lookup"><span data-stu-id="374b5-163">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="374b5-164">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="374b5-164">To test your form</span></span>  
  
1.  <span data-ttu-id="374b5-165">Drücken Sie F5, um zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="374b5-165">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="374b5-166">Klicken Sie auf die **Fenster** Menüelement, öffnen Sie das Menü, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="374b5-166">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="374b5-167">Ein neues untergeordnetes Formular wird im MDI-Clientbereich des Formulars erstellt.</span><span class="sxs-lookup"><span data-stu-id="374b5-167">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="374b5-168">Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="374b5-168">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="374b5-169">Schließen Sie das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-169">Close the child form.</span></span>  
  
     <span data-ttu-id="374b5-170">Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.</span><span class="sxs-lookup"><span data-stu-id="374b5-170">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="374b5-171">Klicken Sie auf **neu** mehrmals.</span><span class="sxs-lookup"><span data-stu-id="374b5-171">Click **New** several times.</span></span>  
  
     <span data-ttu-id="374b5-172">Die untergeordneten Formulare sind automatisch aufgeführt, unter der W**Window** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-172">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="374b5-173">Hinzufügen von ToolStrip-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="374b5-173">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="374b5-174">In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente zum übergeordneten MDI-Formulars.</span><span class="sxs-lookup"><span data-stu-id="374b5-174">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="374b5-175">Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement hinzugefügt wird, innerhalb einer <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das an den Rand des Formulars angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-175">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="374b5-176">Hinzufügen von ToolStrip-Steuerelementen zu übergeordneten MDI-Formulars</span><span class="sxs-lookup"><span data-stu-id="374b5-176">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="374b5-177">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="374b5-177">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="374b5-178">Mit der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement aktiviert ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="374b5-178">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="374b5-179">Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-179">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="374b5-180">Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-180">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="374b5-181">Ändern Sie im Fenster Eigenschaften den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="374b5-181">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="374b5-182">Die <xref:System.Windows.Forms.ToolStripPanel> wird an der linken Seite des Formulars, unterhalb des Hauptmenüs angedockt steuern.</span><span class="sxs-lookup"><span data-stu-id="374b5-182">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="374b5-183">MDI-Clientbereichs wird an die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-183">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="374b5-184">Wiederholen Sie die Schritte 1 bis 4.</span><span class="sxs-lookup"><span data-stu-id="374b5-184">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="374b5-185">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="374b5-185">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="374b5-186">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist unterhalb des Hauptmenüs, jedoch auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-186">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="374b5-187">Dieser Schritt veranschaulicht die Bedeutung der Z-Reihenfolge ordnungsgemäß Positionierung <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="374b5-187">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="374b5-188">Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="374b5-188">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="374b5-189">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente zum rechten und unteren Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="374b5-189">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="374b5-190">ToolStripPanel-Steuerelementen nach Z-Reihenfolge anordnen</span><span class="sxs-lookup"><span data-stu-id="374b5-190">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="374b5-191">Die Position eines angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement im MDI-Formulars wird durch die Position des Steuerelements in der Z-Reihenfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="374b5-191">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="374b5-192">Sie können einfach die Z-Reihenfolge von den Steuerelementen im Fenster "Dokumentgliederung" anordnen.</span><span class="sxs-lookup"><span data-stu-id="374b5-192">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="374b5-193">ToolStripPanel-Steuerelementen nach Z-Reihenfolge anordnen.</span><span class="sxs-lookup"><span data-stu-id="374b5-193">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="374b5-194">In der **Ansicht** Menü klicken Sie auf **Weitere Fenster**, und klicken Sie dann auf **Dokumentgliederung**.</span><span class="sxs-lookup"><span data-stu-id="374b5-194">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="374b5-195">Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus der vorherigen Prozedur ist nicht dem Standard entsprechende.</span><span class="sxs-lookup"><span data-stu-id="374b5-195">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="374b5-196">Dies ist, da die Z-Reihenfolge nicht richtig ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-196">This is because the z-order is not correct.</span></span> <span data-ttu-id="374b5-197">Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="374b5-197">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="374b5-198">Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="374b5-198">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="374b5-199">Klicken Sie auf die nach-unten-Taste wiederholt, bis **ToolStripPanel4** befindet sich unten in der Liste.</span><span class="sxs-lookup"><span data-stu-id="374b5-199">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="374b5-200">Die **ToolStripPanel4** Steuerelement an das Ende des Formulars unter den anderen Steuerelementen angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-200">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="374b5-201">Wählen Sie **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="374b5-201">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="374b5-202">Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, im dritten Positionieren des Steuerelements in der Liste.</span><span class="sxs-lookup"><span data-stu-id="374b5-202">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="374b5-203">Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="374b5-203">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="374b5-204">Wählen Sie die verschiedenen Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="374b5-204">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="374b5-205">Beachten Sie die Auswirkung der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="374b5-205">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="374b5-206">Drücken Sie STRG-z oder **Rückgängig** auf die **bearbeiten** -Menü, um Ihre Änderungen rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="374b5-206">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="374b5-207">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="374b5-207">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="374b5-208">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="374b5-208">To test your form</span></span>  
  
1.  <span data-ttu-id="374b5-209">Drücken Sie F5, um zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="374b5-209">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="374b5-210">Klicken Sie auf den Ziehpunkt des eine <xref:System.Windows.Forms.ToolStrip> steuern und auf dem Formular an andere Positionen ziehen.</span><span class="sxs-lookup"><span data-stu-id="374b5-210">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="374b5-211">Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement aus einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="374b5-211">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="374b5-212">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="374b5-212">Next Steps</span></span>  
 <span data-ttu-id="374b5-213">In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="374b5-213">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="374b5-214">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="374b5-214">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="374b5-215">Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="374b5-215">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="374b5-216">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="374b5-216">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="374b5-217">Ein Formular erstellt mit einem automatisch gefüllten Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="374b5-217">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="374b5-218">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="374b5-218">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="374b5-219">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="374b5-219">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="374b5-220">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="374b5-220">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="374b5-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="374b5-221">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="374b5-222">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="374b5-222">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="374b5-223">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="374b5-223">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="374b5-224">Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü</span><span class="sxs-lookup"><span data-stu-id="374b5-224">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="374b5-225">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="374b5-225">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
