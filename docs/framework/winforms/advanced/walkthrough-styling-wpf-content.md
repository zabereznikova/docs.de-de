---
title: 'Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 887a157494c2992c1ae5868229c442f31fafb276
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312149"
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="868dd-102">Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt</span><span class="sxs-lookup"><span data-stu-id="868dd-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="868dd-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Formatvorlage auf ein WPF-Steuerelement (Windows Presentation Foundation) angewendet wird, das in einem Windows Form-Objekt gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="868dd-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="868dd-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="868dd-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="868dd-105">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="868dd-105">Create the project.</span></span>

-   <span data-ttu-id="868dd-106">Erstellen des WPF-Steuerelementtyps</span><span class="sxs-lookup"><span data-stu-id="868dd-106">Create the WPF control type.</span></span>

-   <span data-ttu-id="868dd-107">Zuweisen einer Formatvorlage zum WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="868dd-107">Apply a style to the WPF control.</span></span>

> [!NOTE]
>  <span data-ttu-id="868dd-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="868dd-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="868dd-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="868dd-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="868dd-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="868dd-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="868dd-111">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="868dd-111">Prerequisites</span></span>  
 <span data-ttu-id="868dd-112">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="868dd-112">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="868dd-113">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="868dd-113">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="868dd-114">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="868dd-114">Creating the Project</span></span>  
 <span data-ttu-id="868dd-115">Zunächst muss das Windows Forms-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="868dd-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="868dd-116">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="868dd-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="868dd-117">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="868dd-117">To create the project</span></span>  
  
-   <span data-ttu-id="868dd-118">Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `StylingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="868dd-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="868dd-119">Erstellen der WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="868dd-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="868dd-120">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.</span><span class="sxs-lookup"><span data-stu-id="868dd-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="868dd-121">So erstellen Sie WPF-Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="868dd-121">To create WPF control types</span></span>  
  
1. <span data-ttu-id="868dd-122">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="868dd-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="868dd-123">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="868dd-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="868dd-124">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="868dd-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="868dd-125">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="868dd-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="868dd-126">Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="868dd-126">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="868dd-127">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.</span><span class="sxs-lookup"><span data-stu-id="868dd-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4. <span data-ttu-id="868dd-128">Hinzufügen einer <xref:System.Windows.Controls.Button?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="868dd-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5. <span data-ttu-id="868dd-129">Fügen Sie eine zweite <xref:System.Windows.Controls.Button?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft **OK**.</span><span class="sxs-lookup"><span data-stu-id="868dd-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6. <span data-ttu-id="868dd-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="868dd-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="868dd-131">Anwenden einer Formatvorlage auf ein WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="868dd-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="868dd-132">Sie können verschiedene Formatvorlagen auf ein WPF-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="868dd-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="868dd-133">So wenden Sie eine Formatvorlage auf ein WPF-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="868dd-133">To apply a style to a WPF control</span></span>  
  
1. <span data-ttu-id="868dd-134">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="868dd-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="868dd-135">In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="868dd-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="868dd-136">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="868dd-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3. <span data-ttu-id="868dd-137">Der Smarttagbereich für `elementHost1`, klicken Sie auf **gehosteten Inhalt bearbeiten** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="868dd-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="868dd-138">`UserControl1` wird im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] geöffnet.</span><span class="sxs-lookup"><span data-stu-id="868dd-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="868dd-139">Fügen Sie den folgenden XAML-Code in der XAML-Ansicht hinter dem `<UserControl>`-Starttag ein.</span><span class="sxs-lookup"><span data-stu-id="868dd-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="868dd-140">Dieser XAML-Code erstellt einen Farbverlauf mit kontrastreichem Farbverlaufsrand.</span><span class="sxs-lookup"><span data-stu-id="868dd-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="868dd-141">Wenn das Steuerelement angeklickt wird, werden die Farbverläufe geändert, um den Eindruck einer gedrückten Schaltfläche zu generieren.</span><span class="sxs-lookup"><span data-stu-id="868dd-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="868dd-142">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="868dd-142">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1. <span data-ttu-id="868dd-143">Wenden Sie die im vorherigen Schritt definierte `SimpleButton`-Formatvorlage auf die „Cancel“-Schaltfläche an, indem Sie den folgenden XAML-Code im `<Button>`-Tag der „Cancel“-Schaltfläche einfügen.</span><span class="sxs-lookup"><span data-stu-id="868dd-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="868dd-144">Ihre Schaltflächendeklaration wird dem folgenden XAML-Code ähneln.</span><span class="sxs-lookup"><span data-stu-id="868dd-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1. <span data-ttu-id="868dd-145">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="868dd-145">Build the project.</span></span>  
  
2. <span data-ttu-id="868dd-146">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="868dd-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3. <span data-ttu-id="868dd-147">Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.</span><span class="sxs-lookup"><span data-stu-id="868dd-147">The new style is applied to the button control.</span></span>  
  
4. <span data-ttu-id="868dd-148">Von der **Debuggen** , wählen Sie im Menü **Debuggen starten** zum Ausführen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="868dd-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5. <span data-ttu-id="868dd-149">Klicken Sie auf die Schaltflächen "OK" und "Cancel", und beobachten Sie die Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="868dd-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868dd-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="868dd-150">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="868dd-151">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="868dd-151">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="868dd-152">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="868dd-152">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="868dd-153">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="868dd-153">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="868dd-154">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="868dd-154">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="868dd-155">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="868dd-155">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
