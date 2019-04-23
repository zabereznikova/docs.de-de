---
title: 'Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 526cb509d780abdbf3db6e15504616de19daae83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336550"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="5015e-102">Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5015e-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="5015e-103">Sie können Ihrer Anwendungsverzeichnis erteilen <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen und Verhalten durch eine eigene Klasse abgeleitet schreiben die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.</span><span class="sxs-lookup"><span data-stu-id="5015e-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="5015e-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente, um ein zusammengesetztes Steuerelement zu erstellen, ähnelt die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten.</span><span class="sxs-lookup"><span data-stu-id="5015e-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="5015e-105">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5015e-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="5015e-106">Erstellen eines Windows-Steuerelementbibliothek-Projekts.</span><span class="sxs-lookup"><span data-stu-id="5015e-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="5015e-107">Entwerfen des StackView-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="5015e-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="5015e-108">Implementieren eines benutzerdefinierten Renderers.</span><span class="sxs-lookup"><span data-stu-id="5015e-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="5015e-109">Wenn Sie fertig sind, müssen Sie ein Steuerelement wiederverwendbare benutzerdefinierte Clienteinstellungen, mit der professionelle Darstellung eines Microsoft Office® XP-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="5015e-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="5015e-110">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5015e-111">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="5015e-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5015e-112">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5015e-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5015e-113">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5015e-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5015e-114">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5015e-114">Prerequisites</span></span>  
 <span data-ttu-id="5015e-115">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5015e-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="5015e-116">Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5015e-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="5015e-117">Erstellen eine Windows-Steuerelementbibliothek-Projekt</span><span class="sxs-lookup"><span data-stu-id="5015e-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="5015e-118">Der erste Schritt ist das Steuerelementbibliothek-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5015e-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="5015e-119">Um die Steuerelementbibliothek-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5015e-119">To create the control library project</span></span>  
  
1. <span data-ttu-id="5015e-120">Erstellen Sie ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="5015e-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2. <span data-ttu-id="5015e-121">In **Projektmappen-Explorer**, löschen Sie Standardsteuerelement des Projekts, indem Sie die Quelldatei, die mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von der Sprache Ihrer Wahl löschen.</span><span class="sxs-lookup"><span data-stu-id="5015e-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="5015e-122">Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5015e-122">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="5015e-123">Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die **StackViewLibrary** Projekt.</span><span class="sxs-lookup"><span data-stu-id="5015e-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="5015e-124">Weisen Sie der neuen Quelldatei Basisnamen `StackView`.</span><span class="sxs-lookup"><span data-stu-id="5015e-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="5015e-125">Entwerfen des StackView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5015e-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="5015e-126">Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="5015e-127">Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varieties of Custom Controls](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-127">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="5015e-128">So entwerfen Sie die StackView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5015e-128">To design the StackView control</span></span>  
  
1. <span data-ttu-id="5015e-129">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="5015e-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2. <span data-ttu-id="5015e-130">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5015e-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="5015e-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5015e-131">Property</span></span>|<span data-ttu-id="5015e-132">Wert</span><span class="sxs-lookup"><span data-stu-id="5015e-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="5015e-133">Name</span><span class="sxs-lookup"><span data-stu-id="5015e-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="5015e-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="5015e-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="5015e-135">Andocken</span><span class="sxs-lookup"><span data-stu-id="5015e-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="5015e-136">Schriftart</span><span class="sxs-lookup"><span data-stu-id="5015e-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="5015e-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="5015e-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="5015e-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="5015e-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="5015e-139">Abstand</span><span class="sxs-lookup"><span data-stu-id="5015e-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="5015e-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="5015e-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3. <span data-ttu-id="5015e-141">Im Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche, und fügen eine <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4. <span data-ttu-id="5015e-142">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5015e-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="5015e-143">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5015e-143">Property</span></span>|<span data-ttu-id="5015e-144">Wert</span><span class="sxs-lookup"><span data-stu-id="5015e-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="5015e-145">Name</span><span class="sxs-lookup"><span data-stu-id="5015e-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="5015e-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="5015e-146">CheckOnClick</span></span>|<span data-ttu-id="5015e-147">true</span><span class="sxs-lookup"><span data-stu-id="5015e-147">true</span></span>|  
    |<span data-ttu-id="5015e-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="5015e-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="5015e-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="5015e-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="5015e-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="5015e-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="5015e-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="5015e-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="5015e-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="5015e-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="5015e-153">Rand</span><span class="sxs-lookup"><span data-stu-id="5015e-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="5015e-154">Abstand</span><span class="sxs-lookup"><span data-stu-id="5015e-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="5015e-155">Text</span><span class="sxs-lookup"><span data-stu-id="5015e-155">Text</span></span>|<span data-ttu-id="5015e-156">**E-Mail-Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="5015e-156">**Mail**</span></span>|  
    |<span data-ttu-id="5015e-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="5015e-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5. <span data-ttu-id="5015e-158">Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5015e-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="5015e-159">Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="5015e-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="5015e-160">Legen Sie den Wert, der die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw.</span><span class="sxs-lookup"><span data-stu-id="5015e-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="5015e-161">Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5015e-161">Handling Events</span></span>  
 <span data-ttu-id="5015e-162">Zwei Ereignisse sind wichtig, zu der `StackView` -Steuerelement ordnungsgemäß verhält.</span><span class="sxs-lookup"><span data-stu-id="5015e-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="5015e-163">Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="5015e-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="5015e-164">Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für jeden <xref:System.Windows.Forms.ToolStripButton> gerne die `StackView` steuern das Verhalten ähnlich wie die <xref:System.Windows.Forms.RadioButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="5015e-165">Zum Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5015e-165">To handle events</span></span>  
  
1. <span data-ttu-id="5015e-166">Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2. <span data-ttu-id="5015e-167">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="5015e-167">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="5015e-168">Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5015e-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4. <span data-ttu-id="5015e-169">Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="5015e-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5. <span data-ttu-id="5015e-170">Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6. <span data-ttu-id="5015e-171">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="5015e-171">In the **Properties** window, click **Events**.</span></span>  
  
7. <span data-ttu-id="5015e-172">Doppelklicken Sie auf das Click-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5015e-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="5015e-173">Die Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5015e-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8. <span data-ttu-id="5015e-174">Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="5015e-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="5015e-175">Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="5015e-175">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
9. <span data-ttu-id="5015e-176">Fügen Sie folgenden Code in die `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5015e-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="5015e-177">Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5015e-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="5015e-178">In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="5015e-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="5015e-179">Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5015e-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="5015e-180">Definieren von Symbolen</span><span class="sxs-lookup"><span data-stu-id="5015e-180">Defining Icons</span></span>  
 <span data-ttu-id="5015e-181">Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol.</span><span class="sxs-lookup"><span data-stu-id="5015e-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="5015e-182">Der Einfachheit halber jedes Symbol wird dargestellt, als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5015e-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="5015e-183">In einer produktionsumgebung Bitmapdaten werden als Ressource gespeichert, und die Symbole, die im Windows Forms-Designer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5015e-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="5015e-184">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Hintergrundbildern zu Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5015e-184">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="5015e-185">Um Symbole zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5015e-185">To define icons</span></span>  
  
1. <span data-ttu-id="5015e-186">Im Code-Editor, fügen Sie folgenden Code in die `StackView` Definition der Klasse.</span><span class="sxs-lookup"><span data-stu-id="5015e-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="5015e-187">Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.</span><span class="sxs-lookup"><span data-stu-id="5015e-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2. <span data-ttu-id="5015e-188">Fügen Sie einen Aufruf an die `InitializeImages` -Methode in der die `StackView` Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="5015e-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="5015e-189">Implementieren eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="5015e-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="5015e-190">Sie können anpassen, dass die meisten Elemente der `StackView` steuern Implementieren einer Klasse, die von abgeleitet der <xref:System.Windows.Forms.ToolStripRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="5015e-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="5015e-191">In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und Hintergründe mit Farbverlauf für zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5015e-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="5015e-192">Zum Implementieren eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="5015e-192">To implement a custom renderer</span></span>  
  
1. <span data-ttu-id="5015e-193">Fügen Sie folgenden Code in die `StackView` Definition zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5015e-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="5015e-194">Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="5015e-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2. <span data-ttu-id="5015e-195">In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5015e-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="5015e-196">Testen des Steuerelements StackView</span><span class="sxs-lookup"><span data-stu-id="5015e-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="5015e-197">Die `StackView` Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.UserControl> Klasse.</span><span class="sxs-lookup"><span data-stu-id="5015e-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="5015e-198">Aus diesem Grund können Sie testen, das Steuerelement mit dem **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="5015e-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="5015e-199">Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="5015e-200">So testen Sie die StackView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5015e-200">To test the StackView control</span></span>  
  
1. <span data-ttu-id="5015e-201">Drücken Sie F5, um das Projekt erstellen und starten Sie den **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="5015e-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="5015e-202">Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung im ausgewählten Zustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5015e-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5015e-203">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5015e-203">Next Steps</span></span>  
 <span data-ttu-id="5015e-204">In dieser exemplarischen Vorgehensweise haben Sie eine wiederverwendbare benutzerdefinierte Clientsteuerelement mit der professionelle Darstellung eines Steuerelements Office XP erstellt.</span><span class="sxs-lookup"><span data-stu-id="5015e-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="5015e-205">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="5015e-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="5015e-206">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="5015e-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="5015e-207">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-207">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="5015e-208">Erstellen Sie ein Formular mit einem automatisch angegebenen Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="5015e-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="5015e-209">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="5015e-210">Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5015e-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="5015e-211">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5015e-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5015e-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5015e-212">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="5015e-213">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5015e-213">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="5015e-214">Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="5015e-214">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
