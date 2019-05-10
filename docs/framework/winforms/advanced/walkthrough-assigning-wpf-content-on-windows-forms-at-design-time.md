---
title: 'Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211239"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="b63a0-102">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="b63a0-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="b63a0-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie die WPF-Steuerelementtypen (Windows Presentation Foundation) ausgewählt werden, die im Formular angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b63a0-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="b63a0-104">Sie können alle WPF-Steuerelementtypen auswählen, die im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b63a0-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="b63a0-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b63a0-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="b63a0-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="b63a0-106">Create the project.</span></span>

- <span data-ttu-id="b63a0-107">Erstellen der WPF-Steuerelementtypen.</span><span class="sxs-lookup"><span data-stu-id="b63a0-107">Create the WPF control types.</span></span>

- <span data-ttu-id="b63a0-108">Auswählen der WPF-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b63a0-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b63a0-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b63a0-109">Prerequisites</span></span>

<span data-ttu-id="b63a0-110">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b63a0-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="b63a0-111">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="b63a0-111">Create the project</span></span>

<span data-ttu-id="b63a0-112">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="b63a0-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="b63a0-113">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b63a0-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="b63a0-114">Erstellen der WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="b63a0-114">Create the WPF control types</span></span>

<span data-ttu-id="b63a0-115">Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.</span><span class="sxs-lookup"><span data-stu-id="b63a0-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="b63a0-116">Erstellen von WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="b63a0-116">Create WPF control types</span></span>

1. <span data-ttu-id="b63a0-117">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="b63a0-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="b63a0-118">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="b63a0-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="b63a0-119">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="b63a0-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="b63a0-120">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b63a0-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="b63a0-121">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b63a0-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="b63a0-122">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="b63a0-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="b63a0-123">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="b63a0-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="b63a0-124">Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu.</span><span class="sxs-lookup"><span data-stu-id="b63a0-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="b63a0-125">Verwenden Sie den Standardnamen, `UserControl2.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="b63a0-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="b63a0-126">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="b63a0-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="b63a0-127">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="b63a0-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="b63a0-128">**Beachten Sie** im Allgemeinen sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="b63a0-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="b63a0-129">
  <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet. </span><span class="sxs-lookup"><span data-stu-id="b63a0-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="b63a0-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="b63a0-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="b63a0-131">Auswählen von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b63a0-131">Select WPF controls</span></span>

<span data-ttu-id="b63a0-132">Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b63a0-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="b63a0-133">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="b63a0-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b63a0-134">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="b63a0-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="b63a0-135">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="b63a0-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="b63a0-136">Der Smarttagbereich für `elementHost1`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b63a0-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="b63a0-137">Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="b63a0-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="b63a0-138">Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.</span><span class="sxs-lookup"><span data-stu-id="b63a0-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="b63a0-139">In der **Eigenschaften** Fenster, überprüfen Sie, ob die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="b63a0-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="b63a0-140">Von der **Toolbox**in die **WPF-Interoperabilität** gruppieren, ziehen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="b63a0-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="b63a0-141">Der Standardname für das neue Steuerelement ist `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="b63a0-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="b63a0-142">Der Smarttagbereich für `elementHost2`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b63a0-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="b63a0-143">Wählen Sie **"UserControl1"** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b63a0-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="b63a0-144">Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.</span><span class="sxs-lookup"><span data-stu-id="b63a0-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="b63a0-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b63a0-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b63a0-146">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="b63a0-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="b63a0-147">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b63a0-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="b63a0-148">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b63a0-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
