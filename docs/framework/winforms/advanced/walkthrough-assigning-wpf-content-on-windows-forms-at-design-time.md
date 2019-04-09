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
ms.openlocfilehash: 781eaaabb7306018366450c013c227fe5a1fef78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108679"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="5d694-102">Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="5d694-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="5d694-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie die WPF-Steuerelementtypen (Windows Presentation Foundation) ausgewählt werden, die im Formular angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5d694-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="5d694-104">Sie können alle WPF-Steuerelementtypen auswählen, die im Projekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5d694-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="5d694-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5d694-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="5d694-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="5d694-106">Create the project.</span></span>

-   <span data-ttu-id="5d694-107">Erstellen der WPF-Steuerelementtypen.</span><span class="sxs-lookup"><span data-stu-id="5d694-107">Create the WPF control types.</span></span>

-   <span data-ttu-id="5d694-108">Auswählen der WPF-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5d694-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="5d694-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="5d694-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5d694-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5d694-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5d694-111">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5d694-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d694-112">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5d694-112">Prerequisites</span></span>  
 <span data-ttu-id="5d694-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="5d694-113">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="5d694-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="5d694-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5d694-115">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="5d694-115">Creating the Project</span></span>  
 <span data-ttu-id="5d694-116">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5d694-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d694-117">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d694-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="5d694-118">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="5d694-118">To create the project</span></span>  
  
-   <span data-ttu-id="5d694-119">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="5d694-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="5d694-120">Erstellen der WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="5d694-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="5d694-121">Nachdem Sie dem Projekt WPF-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelementen hosten.</span><span class="sxs-lookup"><span data-stu-id="5d694-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="5d694-122">So erstellen Sie WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="5d694-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="5d694-123">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d694-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="5d694-124">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="5d694-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="5d694-125">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="5d694-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="5d694-126">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5d694-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="5d694-127">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5d694-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="5d694-128">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="5d694-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="5d694-129">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="5d694-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="5d694-130">Fügen Sie dem Projekt ein zweites WPF-<xref:System.Windows.Controls.UserControl> hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d694-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="5d694-131">Verwenden Sie den Standardnamen, `UserControl2.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="5d694-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="5d694-132">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="5d694-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="5d694-133">Hinzufügen einer <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="5d694-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="5d694-134">**Beachten Sie** im Allgemeinen sollten Sie anspruchsvolleren WPF-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="5d694-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="5d694-135">
  <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet. </span><span class="sxs-lookup"><span data-stu-id="5d694-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="5d694-136">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5d694-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="5d694-137">Auswählen von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5d694-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="5d694-138">Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement, das bereits Inhalte hostet, verschiedene WPF-Inhalte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5d694-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="5d694-139">So wählen Sie WPF-Steuerelemente aus</span><span class="sxs-lookup"><span data-stu-id="5d694-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="5d694-140">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="5d694-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="5d694-141">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="5d694-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="5d694-142">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="5d694-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="5d694-143">Der Smarttagbereich für `elementHost1`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="5d694-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="5d694-144">Wählen Sie **UserControl2** aus dem Dropdown-Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="5d694-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="5d694-145">Das `elementHost1`-Steuerelement hostet jetzt eine Instanz des `UserControl2`-Typs.</span><span class="sxs-lookup"><span data-stu-id="5d694-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="5d694-146">In der **Eigenschaften** Fenster, überprüfen Sie, ob die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="5d694-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="5d694-147">Von der **Toolbox**in die **WPF-Interoperabilität** gruppieren, ziehen Sie ein <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="5d694-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="5d694-148">Der Standardname für das neue Steuerelement ist `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="5d694-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="5d694-149">Der Smarttagbereich für `elementHost2`öffnen die **gehosteten Inhalt auswählen** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="5d694-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="5d694-150">Wählen Sie **"UserControl1"** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="5d694-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="5d694-151">Das `elementHost2`-Steuerelement hostet jetzt eine Instanz des `UserControl1`-Typs.</span><span class="sxs-lookup"><span data-stu-id="5d694-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d694-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d694-152">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5d694-153">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="5d694-153">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="5d694-154">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5d694-154">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="5d694-155">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d694-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
