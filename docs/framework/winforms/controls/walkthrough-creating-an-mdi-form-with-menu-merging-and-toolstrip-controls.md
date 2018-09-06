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
ms.openlocfilehash: a84b51679969f38955dd6a72ffe94ec8ca70b3df
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861784"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="349cc-102">Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="349cc-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="349cc-103">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace unterstützt MDI-Anwendungen (Multiple Document Interface, Schnittstelle für mehrere Dokumente), und das <xref:System.Windows.Forms.MenuStrip>-Steuerelement unterstützt das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="349cc-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="349cc-104">MDI-Formulare können auch <xref:System.Windows.Forms.ToolStrip>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="349cc-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="349cc-105">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente mit einem MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="349cc-106">Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.</span><span class="sxs-lookup"><span data-stu-id="349cc-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="349cc-107">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="349cc-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="349cc-108">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="349cc-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="349cc-109">Erstellen im Hauptmenü für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-109">Creating the main menu for your form.</span></span> <span data-ttu-id="349cc-110">Der tatsächliche Name des Menüs variieren.</span><span class="sxs-lookup"><span data-stu-id="349cc-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="349cc-111">Hinzufügen der <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="349cc-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="349cc-112">Erstellen ein untergeordnetes Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="349cc-113">Anordnen von <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente nach Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="349cc-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="349cc-114">Wenn Sie fertig sind, haben Sie ein MDI-Formular, das Zusammenführen von Menüs und verschiebbare unterstützt <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="349cc-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="349cc-115">Um den Code in diesem Thema als einzelne Auflistung kopieren möchten, finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="349cc-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="349cc-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="349cc-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="349cc-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="349cc-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="349cc-118">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="349cc-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="349cc-119">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="349cc-119">Prerequisites</span></span>  
 <span data-ttu-id="349cc-120">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="349cc-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="349cc-121">Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="349cc-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="349cc-122">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="349cc-122">Creating the Project</span></span>  
 <span data-ttu-id="349cc-123">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="349cc-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="349cc-124">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="349cc-124">To create the project</span></span>  
  
1.  <span data-ttu-id="349cc-125">Erstellen Sie ein Windows-Anwendungsprojekt namens **MDI-Formulars** (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="349cc-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="349cc-126">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="349cc-126">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="349cc-127">Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.Form.IsMdiContainer%2A> zu `true`.</span><span class="sxs-lookup"><span data-stu-id="349cc-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="349cc-128">Erstellen im Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="349cc-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="349cc-129">Das übergeordnete MDI-Formular enthält das Hauptmenü.</span><span class="sxs-lookup"><span data-stu-id="349cc-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="349cc-130">Das Hauptmenü befindet sich ein Element mit dem Namen **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="349cc-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="349cc-131">Mit der **Fenster** Menüelement, können Sie untergeordnete Formulare erstellen.</span><span class="sxs-lookup"><span data-stu-id="349cc-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="349cc-132">Menüelemente, die aus untergeordneten Formulare werden in das Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="349cc-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="349cc-133">Erstellen Sie im Hauptmenü</span><span class="sxs-lookup"><span data-stu-id="349cc-133">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="349cc-134">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="349cc-135">Hinzufügen einer <xref:System.Windows.Forms.ToolStripMenuItem> auf die <xref:System.Windows.Forms.MenuStrip> steuern, und nennen Sie sie **Fenster**.</span><span class="sxs-lookup"><span data-stu-id="349cc-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="349cc-136">Wählen Sie das <xref:System.Windows.Forms.MenuStrip>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="349cc-137">Legen Sie im Eigenschaftenfenster den Wert von der <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="349cc-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="349cc-138">Fügen Sie ein Unterelement, das **Fenster** Menüelement, und nennen Sie das Unterelement **neu**.</span><span class="sxs-lookup"><span data-stu-id="349cc-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="349cc-139">Klicken Sie im Fenster Eigenschaften auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="349cc-139">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="349cc-140">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="349cc-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="349cc-141">Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="349cc-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="349cc-142">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="349cc-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="349cc-143">Das ToolStripPanel-Steuerelement hinzufügen zur Toolbox</span><span class="sxs-lookup"><span data-stu-id="349cc-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="349cc-144">Bei Verwendung von <xref:System.Windows.Forms.MenuStrip> Steuerelemente mit einem MDI-Formular, das Sie benötigen die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="349cc-145">Müssen Sie hinzufügen, die <xref:System.Windows.Forms.ToolStripPanel> die Steuerung an die **Toolbox** das MDI-Formular im Windows Forms-Designer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="349cc-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="349cc-146">Das ToolStripPanel-Steuerelement zur Toolbox hinzufügen</span><span class="sxs-lookup"><span data-stu-id="349cc-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="349cc-147">Öffnen der **Toolbox**, und klicken Sie dann auf die **alle Windows Forms** Tab, um die verfügbaren Windows Forms-Steuerelemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="349cc-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="349cc-148">Mit der rechten Maustaste das Kontextmenü öffnen, und wählen **Elemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="349cc-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="349cc-149">In der **Toolboxelemente auswählen** (Dialogfeld), führen Sie einen Bildlauf nach unten der **Namen** Spalte, bis Sie gefunden **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="349cc-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="349cc-150">Aktivieren Sie das Kontrollkästchen von **ToolStripPanel**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="349cc-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="349cc-151">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angezeigt wird, der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="349cc-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="349cc-152">Erstellen ein untergeordnetes Formular</span><span class="sxs-lookup"><span data-stu-id="349cc-152">Creating a Child Form</span></span>  
 <span data-ttu-id="349cc-153">In diesem Verfahren definieren Sie eine separate untergeordnete Formular-Klasse, die über ein eigenes <xref:System.Windows.Forms.MenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="349cc-154">Menüelemente für dieses Formular sind mit denen des übergeordneten Formulars zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="349cc-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="349cc-155">Um ein untergeordnetes Formular zu definieren.</span><span class="sxs-lookup"><span data-stu-id="349cc-155">To define a child form</span></span>  
  
1.  <span data-ttu-id="349cc-156">Hinzufügen eines neuen Formulars mit dem Namen `ChildForm` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="349cc-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="349cc-157">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Windows Forms zu einem Projekt](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="349cc-157">For more information, see [How to: Add Windows Forms to a Project](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="349cc-158">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="349cc-159">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Elemente bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="349cc-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="349cc-160">In der **-Elementauflistungs-Editor** Dialogfeld hinzu, und ein neues <xref:System.Windows.Forms.ToolStripMenuItem> mit dem Namen **ChildMenuItem** auf das Menü des untergeordneten.</span><span class="sxs-lookup"><span data-stu-id="349cc-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="349cc-161">Weitere Informationen finden Sie unter [ToolStrip-Elementauflistungs-Editor](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="349cc-161">For more information, see [ToolStrip Items Collection Editor](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="349cc-162">Testen das Formular</span><span class="sxs-lookup"><span data-stu-id="349cc-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="349cc-163">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="349cc-163">To test your form</span></span>  
  
1.  <span data-ttu-id="349cc-164">Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="349cc-164">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="349cc-165">Klicken Sie auf die **Fenster** Menüelement öffnen Sie das Menü, und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="349cc-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="349cc-166">Ein neues untergeordnetes Formular wird in den MDI-Clientbereichs des Formulars erstellt.</span><span class="sxs-lookup"><span data-stu-id="349cc-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="349cc-167">Menü des untergeordneten Formulars wird mit dem Hauptmenü zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="349cc-167">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="349cc-168">Schließen Sie das untergeordnete Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-168">Close the child form.</span></span>  
  
     <span data-ttu-id="349cc-169">Menü des untergeordneten Formulars wird über das Hauptmenü entfernt.</span><span class="sxs-lookup"><span data-stu-id="349cc-169">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="349cc-170">Klicken Sie auf **neu** mehrmals.</span><span class="sxs-lookup"><span data-stu-id="349cc-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="349cc-171">Die untergeordneten Formulare werden automatisch aufgelistet, unter der W**inzufügen** Menüelement, da die <xref:System.Windows.Forms.MenuStrip> des Steuerelements <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> -Eigenschaft zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="349cc-171">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="349cc-172">Hinzufügen von ToolStrip-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="349cc-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="349cc-173">In diesem Verfahren fügen Sie vier <xref:System.Windows.Forms.ToolStrip> Steuerelemente an das übergeordnete MDI-Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="349cc-174">Jede <xref:System.Windows.Forms.ToolStrip> Steuerelement wird hinzugefügt, in einem <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement, das den Rand des Formulars angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="349cc-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="349cc-175">Hinzufügen von ToolStrip-Steuerelementen zur übergeordneten MDI-Formulars</span><span class="sxs-lookup"><span data-stu-id="349cc-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="349cc-176">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="349cc-177">Mit der <xref:System.Windows.Forms.ToolStripPanel> -Steuerelement ausgewählt ist, doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStrip> steuern, der **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="349cc-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="349cc-178">Ein <xref:System.Windows.Forms.ToolStrip> Steuerelement wird erstellt, der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="349cc-179">Wählen Sie das <xref:System.Windows.Forms.ToolStripPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="349cc-180">Ändern Sie im Eigenschaftenfenster den Wert des Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="349cc-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="349cc-181">Die <xref:System.Windows.Forms.ToolStripPanel> steuern, wird an der linken Seite des Formulars wird unterhalb des Hauptmenüs angedockt.</span><span class="sxs-lookup"><span data-stu-id="349cc-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="349cc-182">Wird die Größe des MDI-Client-Bereichs angepasst der <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="349cc-183">Wiederholen Sie die Schritte 1 bis 4.</span><span class="sxs-lookup"><span data-stu-id="349cc-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="349cc-184">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelement am oberen Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="349cc-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="349cc-185">Die <xref:System.Windows.Forms.ToolStripPanel> Steuerelement angedockt ist, unterhalb des Hauptmenüs, sondern auf der rechten Seite des ersten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="349cc-186">Dieser Schritt veranschaulicht, die Bedeutung der Z-Reihenfolge bei der Positionierung ordnungsgemäß <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="349cc-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="349cc-187">Wiederholen Sie die Schritte 1 bis 4 für zwei weitere <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="349cc-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="349cc-188">Docken Sie die neuen <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente am rechten und unteren Rand des Formulars.</span><span class="sxs-lookup"><span data-stu-id="349cc-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="349cc-189">ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen</span><span class="sxs-lookup"><span data-stu-id="349cc-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="349cc-190">Die Position des angedockten <xref:System.Windows.Forms.ToolStripPanel> Steuerelement auf dem MDI-Formular richtet sich nach der die Position des Steuerelements in der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="349cc-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="349cc-191">Sie können problemlos die Z-Reihenfolge der Steuerelemente in das Fenster "Dokumentgliederung" anordnen.</span><span class="sxs-lookup"><span data-stu-id="349cc-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="349cc-192">ToolStripPanel-Steuerelementen Z-Reihenfolge anordnen</span><span class="sxs-lookup"><span data-stu-id="349cc-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="349cc-193">In der **Ansicht** Menü klicken Sie auf **Other Windows**, und klicken Sie dann auf **Dokumentgliederung**.</span><span class="sxs-lookup"><span data-stu-id="349cc-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="349cc-194">Die Anordnung von Ihrem <xref:System.Windows.Forms.ToolStripPanel> Steuerelemente aus dem vorherigen Verfahren entspricht nicht dem Standard.</span><span class="sxs-lookup"><span data-stu-id="349cc-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="349cc-195">Dies ist, da die Z-Reihenfolge nicht korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="349cc-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="349cc-196">Verwenden Sie das Fenster "Dokumentgliederung", um die Z-Reihenfolge der Steuerelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="349cc-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="349cc-197">Wählen Sie in das Fenster "Dokumentgliederung" **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="349cc-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="349cc-198">Klicken Sie auf den Pfeil nach unten-Schaltfläche wiederholt, bis **ToolStripPanel4** wird am unteren Rand der Liste.</span><span class="sxs-lookup"><span data-stu-id="349cc-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="349cc-199">Die **ToolStripPanel4** Steuerelement am unteren Rand unter den anderen Steuerelementen im Formular angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="349cc-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="349cc-200">Wählen Sie **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="349cc-200">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="349cc-201">Klicken Sie einmal auf die Schaltfläche nach unten weisenden Pfeil, dritte Positionieren des Steuerelements in der Liste.</span><span class="sxs-lookup"><span data-stu-id="349cc-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="349cc-202">Die **ToolStripPanel2** Steuerelement am oberen Rand des Formulars, unterhalb des Hauptmenüs und über die anderen Steuerelemente angedockt ist.</span><span class="sxs-lookup"><span data-stu-id="349cc-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="349cc-203">Wählen Sie verschiedene Steuerelemente in der **Dokumentgliederung** Fenster und verschieben Sie sie an andere Positionen in der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="349cc-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="349cc-204">Beachten Sie die Auswirkungen der Z-Reihenfolge auf die Platzierung der angedockten Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="349cc-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="349cc-205">Verwenden Sie STRG + Z oder **Rückgängig** auf die **bearbeiten** Menü, um Ihre Änderungen rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="349cc-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="349cc-206">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="349cc-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="349cc-207">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="349cc-207">To test your form</span></span>  
  
1.  <span data-ttu-id="349cc-208">Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="349cc-208">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="349cc-209">Klicken Sie auf den Ziehpunkt einer <xref:System.Windows.Forms.ToolStrip> steuern, und ziehen Sie das Steuerelement an anderen Positionen auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="349cc-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="349cc-210">Ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement von einem <xref:System.Windows.Forms.ToolStripPanel> zu einem anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="349cc-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="349cc-211">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="349cc-211">Next Steps</span></span>  
 <span data-ttu-id="349cc-212">In dieser exemplarischen Vorgehensweise haben Sie einen übergeordneten MDI-Formulars mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente und das Zusammenführen von Menüs.</span><span class="sxs-lookup"><span data-stu-id="349cc-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="349cc-213">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="349cc-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="349cc-214">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="349cc-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="349cc-215">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="349cc-215">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="349cc-216">Ein Formular erstellt mit einem automatisch angegebenen Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="349cc-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="349cc-217">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="349cc-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="349cc-218">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="349cc-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="349cc-219">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="349cc-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349cc-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="349cc-220">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="349cc-221">Gewusst wie: Erstellen von übergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="349cc-221">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="349cc-222">Gewusst wie: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="349cc-222">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="349cc-223">Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü</span><span class="sxs-lookup"><span data-stu-id="349cc-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="349cc-224">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="349cc-224">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
