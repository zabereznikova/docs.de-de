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
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211769"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="b9e75-102">Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="b9e75-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="b9e75-103">Sie können Ihrer Anwendungsverzeichnis erteilen <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen und Verhalten durch eine eigene Klasse abgeleitet schreiben die <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Typ.</span><span class="sxs-lookup"><span data-stu-id="b9e75-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="b9e75-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit <xref:System.Windows.Forms.ToolStrip> Steuerelemente, um ein zusammengesetztes Steuerelement zu erstellen, ähnelt die **Navigationsbereich** von Microsoft® Outlook® bereitgestellten.</span><span class="sxs-lookup"><span data-stu-id="b9e75-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="b9e75-105">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b9e75-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="b9e75-106">Erstellen eines Windows-Steuerelementbibliothek-Projekts.</span><span class="sxs-lookup"><span data-stu-id="b9e75-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="b9e75-107">Entwerfen des StackView-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="b9e75-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="b9e75-108">Implementieren eines benutzerdefinierten Renderers.</span><span class="sxs-lookup"><span data-stu-id="b9e75-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="b9e75-109">Wenn Sie fertig sind, müssen Sie ein Steuerelement wiederverwendbare benutzerdefinierte Clienteinstellungen, mit der professionelle Darstellung eines Microsoft Office® XP-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="b9e75-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="b9e75-110">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines professionellen ToolStrip-Steuerelements](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9e75-111">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b9e75-111">Prerequisites</span></span>

<span data-ttu-id="b9e75-112">Sie benötigen Visual Studio zum Durchführen dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="b9e75-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="b9e75-113">Erstellen Sie die Steuerelementbibliothek-Projekt</span><span class="sxs-lookup"><span data-stu-id="b9e75-113">Create the control library project</span></span>

1. <span data-ttu-id="b9e75-114">Erstellen Sie in Visual Studio ein neues Windows-Steuerelementbibliothek-Projekt namens `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="b9e75-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="b9e75-115">In **Projektmappen-Explorer**, löschen Sie Standardsteuerelement des Projekts, indem Sie die Quelldatei, die mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von der Sprache Ihrer Wahl löschen.</span><span class="sxs-lookup"><span data-stu-id="b9e75-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="b9e75-116">Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b9e75-116">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="b9e75-117">Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die **StackViewLibrary** Projekt.</span><span class="sxs-lookup"><span data-stu-id="b9e75-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="b9e75-118">Weisen Sie der neuen Quelldatei Basisnamen `StackView`.</span><span class="sxs-lookup"><span data-stu-id="b9e75-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="b9e75-119">Entwerfen des StackView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="b9e75-119">Design the StackView control</span></span>

<span data-ttu-id="b9e75-120">Die `StackView` Steuerelement ist ein zusammengesetztes Steuerelement mit einem untergeordneten <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="b9e75-121">Weitere Informationen über zusammengesetzte Steuerelemente finden Sie unter [Varieties of Custom Controls](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="b9e75-122">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.ToolStrip> Steuerelement auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b9e75-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="b9e75-123">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStrip> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b9e75-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="b9e75-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b9e75-124">Property</span></span>|<span data-ttu-id="b9e75-125">Wert</span><span class="sxs-lookup"><span data-stu-id="b9e75-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b9e75-126">Name</span><span class="sxs-lookup"><span data-stu-id="b9e75-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="b9e75-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="b9e75-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="b9e75-128">Andocken</span><span class="sxs-lookup"><span data-stu-id="b9e75-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="b9e75-129">Schriftart</span><span class="sxs-lookup"><span data-stu-id="b9e75-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="b9e75-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="b9e75-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="b9e75-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="b9e75-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="b9e75-132">Abstand</span><span class="sxs-lookup"><span data-stu-id="b9e75-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="b9e75-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="b9e75-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="b9e75-134">Im Windows Forms-Designer, klicken Sie auf die <xref:System.Windows.Forms.ToolStrip> des Steuerelements **hinzufügen** Schaltfläche, und fügen eine <xref:System.Windows.Forms.ToolStripButton> auf die `stackStrip` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="b9e75-135">In der **Eigenschaften** legen die <xref:System.Windows.Forms.ToolStripButton> Eigenschaften des Steuerelements entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b9e75-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="b9e75-136">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b9e75-136">Property</span></span>|<span data-ttu-id="b9e75-137">Wert</span><span class="sxs-lookup"><span data-stu-id="b9e75-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b9e75-138">Name</span><span class="sxs-lookup"><span data-stu-id="b9e75-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="b9e75-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="b9e75-139">CheckOnClick</span></span>|<span data-ttu-id="b9e75-140">true</span><span class="sxs-lookup"><span data-stu-id="b9e75-140">true</span></span>|
    |<span data-ttu-id="b9e75-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="b9e75-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="b9e75-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="b9e75-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="b9e75-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="b9e75-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="b9e75-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="b9e75-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="b9e75-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="b9e75-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="b9e75-146">Rand</span><span class="sxs-lookup"><span data-stu-id="b9e75-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="b9e75-147">Abstand</span><span class="sxs-lookup"><span data-stu-id="b9e75-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="b9e75-148">Text</span><span class="sxs-lookup"><span data-stu-id="b9e75-148">Text</span></span>|<span data-ttu-id="b9e75-149">**E-Mail-Nachrichten**</span><span class="sxs-lookup"><span data-stu-id="b9e75-149">**Mail**</span></span>|
    |<span data-ttu-id="b9e75-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="b9e75-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="b9e75-151">Wiederholen Sie Schritt 7 für drei weitere <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b9e75-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="b9e75-152">Benennen Sie die Steuerelemente `calendarStackButton`, `contactsStackButton`, und `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="b9e75-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="b9e75-153">Legen Sie den Wert, der die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft **Kalender**, **Kontakte**, und **Aufgaben**bzw.</span><span class="sxs-lookup"><span data-stu-id="b9e75-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="b9e75-154">Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b9e75-154">Handle events</span></span>

<span data-ttu-id="b9e75-155">Zwei Ereignisse sind wichtig, zu der `StackView` -Steuerelement ordnungsgemäß verhält.</span><span class="sxs-lookup"><span data-stu-id="b9e75-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="b9e75-156">Behandeln der <xref:System.Windows.Forms.UserControl.Load> Ereignis, um das Steuerelement ordnungsgemäß zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="b9e75-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="b9e75-157">Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für jeden <xref:System.Windows.Forms.ToolStripButton> gerne die `StackView` steuern das Verhalten ähnlich wie die <xref:System.Windows.Forms.RadioButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="b9e75-158">Wählen Sie in der Windows Forms-Designer die `StackView` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="b9e75-159">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="b9e75-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="b9e75-160">Doppelklicken Sie auf das Load-Ereignis zum Generieren der `StackView_Load` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b9e75-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="b9e75-161">Kopieren Sie den folgenden Code und fügen Sie ihn in den `StackView_Load`-Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="b9e75-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="b9e75-162">Wählen Sie in der Windows Forms-Designer die `mailStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="b9e75-163">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="b9e75-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="b9e75-164">Doppelklicken Sie auf das Click-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b9e75-164">Double-click the Click event.</span></span>

     <span data-ttu-id="b9e75-165">Die Windows Forms-Designer generiert die `mailStackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b9e75-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="b9e75-166">Benennen Sie die `mailStackButton_Click` Ereignishandler `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="b9e75-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="b9e75-167">Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="b9e75-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="b9e75-168">Fügen Sie folgenden Code in die `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b9e75-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="b9e75-169">Wählen Sie in der Windows Forms-Designer die `calendarStackButton` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9e75-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="b9e75-170">In der **Eigenschaften** legen das Click-Ereignis das `stackButton_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b9e75-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="b9e75-171">Wiederholen Sie die Schritte 10 und 11 für den `contactsStackButton` und `tasksStackButton` Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b9e75-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="b9e75-172">Definieren der Symbole</span><span class="sxs-lookup"><span data-stu-id="b9e75-172">Define icons</span></span>

<span data-ttu-id="b9e75-173">Jede `StackView` Schaltfläche verfügt über ein zugeordnetes Symbol.</span><span class="sxs-lookup"><span data-stu-id="b9e75-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="b9e75-174">Der Einfachheit halber jedes Symbol wird dargestellt, als Base64-codierte Zeichenfolge, die deserialisiert wird, bevor Sie eine <xref:System.Drawing.Bitmap> daraus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b9e75-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="b9e75-175">In einer produktionsumgebung Bitmapdaten werden als Ressource gespeichert, und die Symbole, die im Windows Forms-Designer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9e75-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="b9e75-176">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Hintergrundbildern zu Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b9e75-176">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="b9e75-177">Im Code-Editor, fügen Sie folgenden Code in die `StackView` Definition der Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9e75-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="b9e75-178">Dieser Code initialisiert die Bitmaps für die <xref:System.Windows.Forms.ToolStripButton> Symbole.</span><span class="sxs-lookup"><span data-stu-id="b9e75-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="b9e75-179">Fügen Sie einen Aufruf an die `InitializeImages` -Methode in der die `StackView` Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="b9e75-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="b9e75-180">Implementieren eines benutzerdefinierten Renderers</span><span class="sxs-lookup"><span data-stu-id="b9e75-180">Implement a custom renderer</span></span>

<span data-ttu-id="b9e75-181">Sie können anpassen, dass die meisten Elemente der `StackView` steuern Implementieren einer Klasse, die von abgeleitet der <xref:System.Windows.Forms.ToolStripRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9e75-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="b9e75-182">In diesem Verfahren implementieren Sie eine <xref:System.Windows.Forms.ToolStripProfessionalRenderer> -Klasse, die den Ziehpunkt anpasst und Hintergründe mit Farbverlauf für zeichnet die <xref:System.Windows.Forms.ToolStripButton> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b9e75-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="b9e75-183">Fügen Sie folgenden Code in die `StackView` Definition zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b9e75-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="b9e75-184">Dies ist die Definition für die `StackRenderer` Klasse, welche Außerkraftsetzungen der <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, und <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> Methoden, um eine benutzerdefinierte Darstellung zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="b9e75-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="b9e75-185">In der `StackView` Konstruktor des Steuerelements, erstellen Sie eine neue Instanz der dem `StackRenderer` Klasse, und weisen Sie diese Instanz mit der `stackStrip` des Steuerelements <xref:System.Windows.Forms.ToolStrip.Renderer%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b9e75-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="b9e75-186">Testen Sie das Steuerelement StackView</span><span class="sxs-lookup"><span data-stu-id="b9e75-186">Test the StackView control</span></span>

<span data-ttu-id="b9e75-187">Die `StackView` Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.UserControl> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b9e75-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="b9e75-188">Aus diesem Grund können Sie testen, das Steuerelement mit dem **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="b9e75-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="b9e75-189">Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="b9e75-190">Drücken Sie **F5** erstellen Sie das Projekt, und Starten der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="b9e75-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="b9e75-191">Bewegen Sie den Zeiger über die Schaltflächen des der `StackView` steuern, und klicken Sie dann auf eine Schaltfläche, um die Darstellung im ausgewählten Zustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9e75-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9e75-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b9e75-192">Next steps</span></span>

<span data-ttu-id="b9e75-193">In dieser exemplarischen Vorgehensweise haben Sie eine wiederverwendbare benutzerdefinierte Clientsteuerelement mit der professionelle Darstellung eines Steuerelements Office XP erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9e75-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="b9e75-194">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="b9e75-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="b9e75-195">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b9e75-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="b9e75-196">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="b9e75-197">Erstellen Sie ein Formular mit einem automatisch angegebenen Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="b9e75-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="b9e75-198">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="b9e75-199">Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b9e75-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="b9e75-200">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b9e75-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9e75-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9e75-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="b9e75-202">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b9e75-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="b9e75-203">Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="b9e75-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
