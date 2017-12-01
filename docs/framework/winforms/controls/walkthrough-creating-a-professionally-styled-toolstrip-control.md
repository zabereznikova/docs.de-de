---
title: 'Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
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
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fbc03ad16bcc0d63a75df5478f7da8abbf19193
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="eafe5-102">Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="eafe5-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="eafe5-103">Sie können angeben, kann Ihre Anwendung <xref:System.Windows.Forms.ToolStrip> steuert ein professionelles Aussehen und Verhalten durch Schreiben einer eigenen Klasse abgeleitet wurde. die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.</span><span class="sxs-lookup"><span data-stu-id="eafe5-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="eafe5-104">Diese exemplarische Vorgehensweise veranschaulicht, wie <xref:System.Windows.Forms.ToolStrip> Steuerelemente zum Erstellen eines zusammengesetzten Steuerelements, das ähnelt der **Navigationsbereich** von Microsoft® Outlook® bereitgestellten.</span><span class="sxs-lookup"><span data-stu-id="eafe5-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="eafe5-105">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eafe5-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="eafe5-106">Erstellen eines Windows-Steuerelementbibliothek-Projekts.</span><span class="sxs-lookup"><span data-stu-id="eafe5-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="eafe5-107">Entwerfen des StackView-Steuerelements an.</span><span class="sxs-lookup"><span data-stu-id="eafe5-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="eafe5-108">Implementieren eines benutzerdefinierten Renderers.</span><span class="sxs-lookup"><span data-stu-id="eafe5-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="eafe5-109">Wenn Sie fertig sind, müssen Sie ein wiederverwendbare benutzerdefinierte Clientsteuerelement mit professionelle Darstellung eines Microsoft Office® XP-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="eafe5-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="eafe5-110">Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen einer professionellen ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eafe5-111">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="eafe5-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="eafe5-112">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="eafe5-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="eafe5-113">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="eafe5-113">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eafe5-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="eafe5-114">Prerequisites</span></span>  
 <span data-ttu-id="eafe5-115">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eafe5-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="eafe5-116">Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="eafe5-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="eafe5-117">Erstellen eine Windows-Steuerelementbibliothek-Projekt</span><span class="sxs-lookup"><span data-stu-id="eafe5-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="eafe5-118">Der erste Schritt besteht darin-Steuerelementbibliothek-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eafe5-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="eafe5-119">-Steuerelementbibliothek-Projekt erstellen</span><span class="sxs-lookup"><span data-stu-id="eafe5-119">To create the control library project</span></span>  
  
1.  <span data-ttu-id="eafe5-120">Erstellen Sie ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="eafe5-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2.  <span data-ttu-id="eafe5-121">In **Projektmappen-Explorer**, Standardsteuerelement für das Projekt löschen, indem Sie die Quelldatei mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von einer Sprache Ihrer Wahl zu löschen.</span><span class="sxs-lookup"><span data-stu-id="eafe5-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="eafe5-122">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: entfernen, löschen und Ausschließen von Elementen](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="eafe5-122">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="eafe5-123">Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element an der **StackViewLibrary** Projekt.</span><span class="sxs-lookup"><span data-stu-id="eafe5-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="eafe5-124">Benennen Sie die neue Quelldatei Basis von `StackView`.</span><span class="sxs-lookup"><span data-stu-id="eafe5-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="eafe5-125">Entwerfen des StackView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="eafe5-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="eafe5-126">Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="eafe5-127">Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varianten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-127">For more information about composite controls, see [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="eafe5-128">So entwerfen Sie das StackView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eafe5-128">To design the StackView control</span></span>  
  
1.  <span data-ttu-id="eafe5-129">Aus der **Toolbox**, ziehen Sie ein <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="eafe5-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2.  <span data-ttu-id="eafe5-130">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="eafe5-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="eafe5-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eafe5-131">Property</span></span>|<span data-ttu-id="eafe5-132">Wert</span><span class="sxs-lookup"><span data-stu-id="eafe5-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="eafe5-133">Name</span><span class="sxs-lookup"><span data-stu-id="eafe5-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="eafe5-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="eafe5-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="eafe5-135">Andocken</span><span class="sxs-lookup"><span data-stu-id="eafe5-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="eafe5-136">Schriftart</span><span class="sxs-lookup"><span data-stu-id="eafe5-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="eafe5-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="eafe5-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="eafe5-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="eafe5-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="eafe5-139">Textabstand</span><span class="sxs-lookup"><span data-stu-id="eafe5-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="eafe5-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="eafe5-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  <span data-ttu-id="eafe5-141">In Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche und Hinzufügen einer <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4.  <span data-ttu-id="eafe5-142">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="eafe5-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="eafe5-143">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eafe5-143">Property</span></span>|<span data-ttu-id="eafe5-144">Wert</span><span class="sxs-lookup"><span data-stu-id="eafe5-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="eafe5-145">Name</span><span class="sxs-lookup"><span data-stu-id="eafe5-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="eafe5-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="eafe5-146">CheckOnClick</span></span>|<span data-ttu-id="eafe5-147">true</span><span class="sxs-lookup"><span data-stu-id="eafe5-147">true</span></span>|  
    |<span data-ttu-id="eafe5-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="eafe5-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="eafe5-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="eafe5-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="eafe5-150">Verwendung</span><span class="sxs-lookup"><span data-stu-id="eafe5-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="eafe5-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="eafe5-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="eafe5-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="eafe5-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="eafe5-153">Margin</span><span class="sxs-lookup"><span data-stu-id="eafe5-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="eafe5-154">Textabstand</span><span class="sxs-lookup"><span data-stu-id="eafe5-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="eafe5-155">Text</span><span class="sxs-lookup"><span data-stu-id="eafe5-155">Text</span></span>|<span data-ttu-id="eafe5-156">**E-Mail-Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="eafe5-156">**Mail**</span></span>|  
    |<span data-ttu-id="eafe5-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="eafe5-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  <span data-ttu-id="eafe5-158">Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="eafe5-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="eafe5-159">Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="eafe5-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="eafe5-160">Legen Sie den Wert von der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw..</span><span class="sxs-lookup"><span data-stu-id="eafe5-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="eafe5-161">Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="eafe5-161">Handling Events</span></span>  
 <span data-ttu-id="eafe5-162">Zwei Ereignisse sind wichtig, damit die `StackView` -Steuerelement ordnungsgemäß verhält.</span><span class="sxs-lookup"><span data-stu-id="eafe5-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="eafe5-163">Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="eafe5-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="eafe5-164">Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis für jedes <xref:System.Windows.Forms.ToolStripButton> so erteilen Sie die `StackView` Zustand Verhalten ähnelt steuern die <xref:System.Windows.Forms.RadioButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="eafe5-165">Um Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="eafe5-165">To handle events</span></span>  
  
1.  <span data-ttu-id="eafe5-166">Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2.  <span data-ttu-id="eafe5-167">In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="eafe5-167">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="eafe5-168">Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eafe5-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4.  <span data-ttu-id="eafe5-169">Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="eafe5-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  <span data-ttu-id="eafe5-170">Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6.  <span data-ttu-id="eafe5-171">In der **Eigenschaften** Fenster, klicken Sie auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="eafe5-171">In the **Properties** window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="eafe5-172">Doppelklicken Sie auf das Click-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="eafe5-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="eafe5-173">Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eafe5-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8.  <span data-ttu-id="eafe5-174">Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="eafe5-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="eafe5-175">Weitere Informationen finden Sie unter [Vorgehensweise: Umbenennen von Bezeichnern (Visual Basic)](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span><span class="sxs-lookup"><span data-stu-id="eafe5-175">For more information, see [How to: Rename an Identifier (Visual Basic)](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span></span>  
  
9. <span data-ttu-id="eafe5-176">Fügen Sie den folgenden Code in der `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eafe5-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="eafe5-177">Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="eafe5-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="eafe5-178">In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="eafe5-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="eafe5-179">Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="eafe5-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="eafe5-180">Definieren von Symbolen</span><span class="sxs-lookup"><span data-stu-id="eafe5-180">Defining Icons</span></span>  
 <span data-ttu-id="eafe5-181">Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol.</span><span class="sxs-lookup"><span data-stu-id="eafe5-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="eafe5-182">Der Einfachheit halber jedes Symbol wird dargestellt als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="eafe5-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="eafe5-183">In einer produktionsumgebung Bitmapdaten als Ressourcen gespeichert, und die Symbole in Windows Forms-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eafe5-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="eafe5-184">Weitere Informationen finden Sie unter [wie: Hinzufügen von Hintergrundbildern zu Windows Forms](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span><span class="sxs-lookup"><span data-stu-id="eafe5-184">For more information, see [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="eafe5-185">So definieren Sie Symbole</span><span class="sxs-lookup"><span data-stu-id="eafe5-185">To define icons</span></span>  
  
1.  <span data-ttu-id="eafe5-186">Fügen Sie im Code-Editor den folgenden Code in die `StackView` Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="eafe5-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="eafe5-187">Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.</span><span class="sxs-lookup"><span data-stu-id="eafe5-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  <span data-ttu-id="eafe5-188">Fügen Sie einen Aufruf an die `InitializeImages` Methode in der `StackView` Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="eafe5-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="eafe5-189">Implementieren eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="eafe5-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="eafe5-190">Sie können die meisten Elemente der Anpassen der `StackView` steuern, implementieren eine Klasse, abgeleitet wird, die <xref:System.Windows.Forms.ToolStripRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="eafe5-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="eafe5-191">In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und für Farbverlauf Hintergründe zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="eafe5-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="eafe5-192">Implementieren ein benutzerdefiniertes Renderers</span><span class="sxs-lookup"><span data-stu-id="eafe5-192">To implement a custom renderer</span></span>  
  
1.  <span data-ttu-id="eafe5-193">Fügen Sie den folgenden Code in die `StackView` Definition zu steuern.</span><span class="sxs-lookup"><span data-stu-id="eafe5-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="eafe5-194">Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="eafe5-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  <span data-ttu-id="eafe5-195">In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eafe5-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="eafe5-196">Testen des StackView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="eafe5-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="eafe5-197">Die `StackView` Steuerelement leitet sich von der <xref:System.Windows.Forms.UserControl> Klasse.</span><span class="sxs-lookup"><span data-stu-id="eafe5-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="eafe5-198">Aus diesem Grund können Sie das Steuerelement mit dem Testen der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="eafe5-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="eafe5-199">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="eafe5-200">So testen Sie das StackView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eafe5-200">To test the StackView control</span></span>  
  
1.  <span data-ttu-id="eafe5-201">Drücken Sie F5, um das Projekt erstellen und starten Sie die **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="eafe5-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="eafe5-202">Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung des ausgewählten Zustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eafe5-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eafe5-203">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="eafe5-203">Next Steps</span></span>  
 <span data-ttu-id="eafe5-204">In dieser exemplarischen Vorgehensweise haben Sie ein wiederverwendbare benutzerdefinierte Clientsteuerelement mit professionelle Darstellung eines Steuerelements Office XP erstellt.</span><span class="sxs-lookup"><span data-stu-id="eafe5-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="eafe5-205">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="eafe5-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="eafe5-206">Erstellen von Kontextmenüs für die Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="eafe5-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="eafe5-207">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-207">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="eafe5-208">Erstellen Sie ein Formular mit einem automatisch gefüllten Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="eafe5-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="eafe5-209">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="eafe5-210">Erstellen Sie ein Formular der multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="eafe5-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="eafe5-211">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="eafe5-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafe5-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eafe5-212">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="eafe5-213">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eafe5-213">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="eafe5-214">Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="eafe5-214">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
