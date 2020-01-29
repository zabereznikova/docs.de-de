---
title: 'Exemplarische Vorgehensweise: Formatieren von WPF-Inhalten'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e52297f51c74fc3dba93c987fd5b9bd5b6801777
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732547"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="a1d19-102">Exemplarische Vorgehensweise: Formatieren von WPF-Inhalten</span><span class="sxs-lookup"><span data-stu-id="a1d19-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="a1d19-103">In diesem Artikel erfahren Sie, wie Sie Formatierungen auf ein WPF-Steuerelement (Windows Presentation Foundation) anwenden, das in einem Windows Form gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="a1d19-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1d19-104">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a1d19-104">Prerequisites</span></span>

<span data-ttu-id="a1d19-105">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a1d19-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a1d19-106">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="a1d19-106">Create the project</span></span>

<span data-ttu-id="a1d19-107">Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in Visual Basic oder Visual mit dem Namen `StylingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="a1d19-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="a1d19-108">Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1d19-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="a1d19-109">Erstellen der WPF-Steuerelement Typen</span><span class="sxs-lookup"><span data-stu-id="a1d19-109">Create the WPF control types</span></span>

<span data-ttu-id="a1d19-110">Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.</span><span class="sxs-lookup"><span data-stu-id="a1d19-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="a1d19-111">Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a1d19-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="a1d19-112">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="a1d19-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="a1d19-113">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="a1d19-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="a1d19-114">Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1d19-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="a1d19-115">Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf **200**fest.</span><span class="sxs-lookup"><span data-stu-id="a1d19-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="a1d19-116">Fügen Sie der <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.Button?displayProperty=nameWithType>-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A> auf **Abbrechen**fest.</span><span class="sxs-lookup"><span data-stu-id="a1d19-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="a1d19-117">Fügen Sie der <xref:System.Windows.Controls.UserControl> ein zweites <xref:System.Windows.Controls.Button?displayProperty=nameWithType> Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A> auf **OK**fest.</span><span class="sxs-lookup"><span data-stu-id="a1d19-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="a1d19-118">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1d19-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="a1d19-119">Anwenden eines Stils auf ein WPF-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a1d19-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="a1d19-120">Sie können verschiedene Formatvorlagen auf ein WPF-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a1d19-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="a1d19-121">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="a1d19-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="a1d19-122">Doppelklicken Sie in der **Toolbox**auf `UserControl1`, um eine Instanz von `UserControl1` im Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1d19-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="a1d19-123">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="a1d19-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="a1d19-124">Klicken Sie im smarttagpanel für `elementHost1`in der Dropdown Liste auf **gehosteten Inhalt bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="a1d19-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="a1d19-125">`UserControl1` wird im WPF-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a1d19-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="a1d19-126">Fügen Sie den folgenden XAML-Code in der XAML-Ansicht hinter dem `<UserControl>`-Starttag ein.</span><span class="sxs-lookup"><span data-stu-id="a1d19-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="a1d19-127">Dieser XAML-Code erstellt einen Farbverlauf mit kontrastreichem Farbverlaufsrand.</span><span class="sxs-lookup"><span data-stu-id="a1d19-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="a1d19-128">Wenn das Steuerelement angeklickt wird, werden die Farbverläufe geändert, um den Eindruck einer gedrückten Schaltfläche zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a1d19-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="a1d19-129">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a1d19-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

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

1. <span data-ttu-id="a1d19-130">Wenden Sie den im vorherigen Schritt definierten `SimpleButton` Stil auf die Schaltfläche Abbrechen an, indem Sie den folgenden XAML-Code in das `<Button>`-Tag der Schaltfläche **Abbrechen** einfügen.</span><span class="sxs-lookup"><span data-stu-id="a1d19-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="a1d19-131">Die Schaltflächen Deklaration ähnelt der folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="a1d19-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="a1d19-132">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1d19-132">Build the project.</span></span>

1. <span data-ttu-id="a1d19-133">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="a1d19-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="a1d19-134">Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.</span><span class="sxs-lookup"><span data-stu-id="a1d19-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="a1d19-135">Wählen Sie im Menü **Debuggen** die Option **Debuggen starten** , um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a1d19-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="a1d19-136">Klicken Sie auf die Schaltflächen **OK** und **Abbrechen** , um die Unterschiede anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1d19-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1d19-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d19-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a1d19-138">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="a1d19-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="a1d19-139">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a1d19-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="a1d19-140">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a1d19-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a1d19-141">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a1d19-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="a1d19-142">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a1d19-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
