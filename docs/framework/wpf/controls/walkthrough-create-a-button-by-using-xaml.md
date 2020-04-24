---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646470"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="33cbb-102">Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML</span><span class="sxs-lookup"><span data-stu-id="33cbb-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="33cbb-103">Das Ziel dieser exemplarischen Vorgehensweise besteht darin, zu erfahren, wie Sie eine animierte Schaltfläche für die Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="33cbb-104">In dieser exemplarischen Vorgehensweise werden Stile und eine Vorlage verwendet, um eine benutzerdefinierte Schaltflächenressource zu erstellen, die die Wiederverwendung von Code und die Trennung der Schaltflächenlogik von der Schaltflächendeklaration ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="33cbb-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="33cbb-105">Diese exemplarische Vorgehensweise [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist vollständig in geschrieben.</span><span class="sxs-lookup"><span data-stu-id="33cbb-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33cbb-106">In dieser exemplarischen Vorgehensweise führen Sie durch die Schritte zum [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Erstellen der Anwendung durch Eingabe oder Kopieren und Einfügen in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="33cbb-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="33cbb-107">Wenn Sie möchten, wie Sie einen Designer zum Erstellen derselben Anwendung verwenden möchten, finden Sie weitere Informationen unter [Erstellen einer Schaltfläche mithilfe von Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="33cbb-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="33cbb-108">Die folgende Abbildung zeigt die fertigen Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="33cbb-109">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="33cbb-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="33cbb-110">Erstellen von Basisschaltflächen</span><span class="sxs-lookup"><span data-stu-id="33cbb-110">Create Basic Buttons</span></span>

<span data-ttu-id="33cbb-111">Beginnen wir mit dem Erstellen eines neuen Projekts und dem Hinzufügen einiger Schaltflächen zum Fenster.</span><span class="sxs-lookup"><span data-stu-id="33cbb-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="33cbb-112">So erstellen Sie ein neues WPF-Projekt und fügen dem Fenster Schaltflächen hinzu</span><span class="sxs-lookup"><span data-stu-id="33cbb-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="33cbb-113">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="33cbb-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="33cbb-114">**Erstellen Sie ein neues WPF-Projekt:** Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="33cbb-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="33cbb-115">Suchen Sie die **Windows-Anwendungsvorlage (WPF),** und benennen Sie das Projekt "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="33cbb-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="33cbb-116">Dadurch wird das Skelett für die Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="33cbb-117">**Hinzufügen grundlegender Standardschaltflächen:** Alle Dateien, die Sie für diese exemplarische Vorgehensweise benötigen, werden von der Vorlage bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="33cbb-118">Öffnen Sie die Datei Window1.xaml, indem Sie im Projektmappen-Explorer darauf doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="33cbb-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="33cbb-119">Standardmäßig gibt es <xref:System.Windows.Controls.Grid> ein Element in Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="33cbb-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="33cbb-120">Entfernen <xref:System.Windows.Controls.Grid> Sie das Element, und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] fügen Sie der Seite einige Schaltflächen hinzu, indem Sie den folgenden hervorgehobenen Code in Window1.xaml eingeben oder kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="33cbb-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="33cbb-121">Drücken Sie F5, um die Anwendung auszuführen; Sie sollten eine Reihe von Schaltflächen sehen, die wie die folgende Abbildung aussieht.</span><span class="sxs-lookup"><span data-stu-id="33cbb-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="33cbb-122">![Drei grundlegende Schaltflächen](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="33cbb-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="33cbb-123">Nachdem Sie die grundlegenden Schaltflächen erstellt haben, sind Sie mit der Arbeit in der Datei Window1.xaml fertig.</span><span class="sxs-lookup"><span data-stu-id="33cbb-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="33cbb-124">Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei app.xaml, die Stile und eine Vorlage für die Schaltflächen definiert.</span><span class="sxs-lookup"><span data-stu-id="33cbb-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="33cbb-125">Festlegen grundlegender Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="33cbb-125">Set Basic Properties</span></span>

<span data-ttu-id="33cbb-126">Als Nächstes legen wir einige Eigenschaften auf diesen Schaltflächen fest, um die Schaltflächendarstellung und das Layout zu steuern.</span><span class="sxs-lookup"><span data-stu-id="33cbb-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="33cbb-127">Anstatt Eigenschaften für die Schaltflächen einzeln festzulegen, verwenden Sie Ressourcen, um Schaltflächeneigenschaften für die gesamte Anwendung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="33cbb-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="33cbb-128">Anwendungsressourcen ähneln konzeptionell externen Cascading Style Sheets (CSS) für Webseiten. Ressourcen sind jedoch viel leistungsfähiger als Cascading Style Sheets (CSS), wie Sie am Ende dieser exemplarischen Vorgehensweise sehen werden.</span><span class="sxs-lookup"><span data-stu-id="33cbb-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="33cbb-129">Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="33cbb-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="33cbb-130">So verwenden Sie Stile, um grundlegende Eigenschaften für die Schaltflächen festzulegen</span><span class="sxs-lookup"><span data-stu-id="33cbb-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="33cbb-131">**Definieren eines Application.Resources-Blocks:** Öffnen Sie app.xaml und fügen Sie das folgende hervorgehobene Markup hinzu, wenn es noch nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="33cbb-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="33cbb-132">Der Ressourcenbereich wird dadurch bestimmt, wo Sie die Ressource definieren.</span><span class="sxs-lookup"><span data-stu-id="33cbb-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="33cbb-133">Durch das `Application.Resources` Definieren von Ressourcen in der Datei app.xaml kann die Ressource von überall in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33cbb-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="33cbb-134">Weitere Informationen zum Definieren des Ressourcenbereichs finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="33cbb-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="33cbb-135">**Erstellen Sie einen Stil, und definieren Sie damit grundlegende Eigenschaftswerte:** Fügen Sie dem `Application.Resources` Block das folgende Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="33cbb-136">Dieses Markup <xref:System.Windows.Style> erstellt eine, die für alle <xref:System.Windows.FrameworkElement.Width%2A> Schaltflächen in der Anwendung <xref:System.Windows.FrameworkElement.Margin%2A> gilt, und legt die Schaltflächen auf 90 und die auf 10 fest:</span><span class="sxs-lookup"><span data-stu-id="33cbb-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="33cbb-137">Die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der <xref:System.Windows.Controls.Button>Stil für alle Objekte vom Typ gilt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="33cbb-138">Jeder <xref:System.Windows.Setter> legt einen anderen <xref:System.Windows.Style>Eigenschaftswert für die fest.</span><span class="sxs-lookup"><span data-stu-id="33cbb-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="33cbb-139">Daher hat an dieser Stelle jede Taste in der Anwendung eine Breite von 90 und einen Rand von 10.</span><span class="sxs-lookup"><span data-stu-id="33cbb-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="33cbb-140">Wenn Sie F5 drücken, um die Anwendung auszuführen, wird das folgende Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="33cbb-141">![Schaltflächen mit einer Breite von 90 und einem Rand von 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="33cbb-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="33cbb-142">Es gibt viel mehr, was Sie mit Stilen tun können, einschließlich einer Vielzahl von Möglichkeiten, um die Ziele von Objekten zu optimieren, komplexe Eigenschaftswerte anzugeben und sogar Stile als Eingabe für andere Stile zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="33cbb-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="33cbb-143">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33cbb-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="33cbb-144">**Legen Sie einen Stileigenschaftswert für eine Ressource fest:** Ressourcen ermöglichen eine einfache Möglichkeit, häufig definierte Objekte und Werte wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="33cbb-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="33cbb-145">Es ist besonders nützlich, komplexe Werte mithilfe von Ressourcen zu definieren, um den Code modularer zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="33cbb-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="33cbb-146">Fügen Sie das folgende hervorgehobene Markup zu app.xaml hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="33cbb-147">Direkt unter `Application.Resources` dem Block haben Sie eine Ressource mit dem Namen "GrayBlueGradientBrush" erstellt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="33cbb-148">Diese Ressource definiert einen horizontalen Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="33cbb-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="33cbb-149">Diese Ressource kann als Eigenschaftswert von überall in der Anwendung verwendet <xref:System.Windows.Controls.Control.Background%2A> werden, einschließlich innerhalb des Schaltflächenstil-Setters für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="33cbb-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="33cbb-150">Jetzt haben alle Schaltflächen einen <xref:System.Windows.Controls.Control.Background%2A> Eigenschaftswert dieses Farbverlaufs.</span><span class="sxs-lookup"><span data-stu-id="33cbb-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="33cbb-151">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-151">Press F5 to run the application.</span></span> <span data-ttu-id="33cbb-152">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-152">It should look like the following.</span></span>

     <span data-ttu-id="33cbb-153">![Schaltflächen mit einem Farbverlaufshintergrund](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="33cbb-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="33cbb-154">Erstellen einer Vorlage, die das Aussehen der Schaltfläche definiert</span><span class="sxs-lookup"><span data-stu-id="33cbb-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="33cbb-155">In diesem Abschnitt erstellen Sie eine Vorlage, die die Darstellung (Präsentation) der Schaltfläche anpasst.</span><span class="sxs-lookup"><span data-stu-id="33cbb-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="33cbb-156">Die Schaltflächenpräsentation besteht aus mehreren Objekten, einschließlich Rechtecken und anderen Komponenten, um der Schaltfläche ein einzigartiges Aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="33cbb-157">Bisher beschränkte sich die Steuerung, wie Schaltflächen in der Anwendung aussehen, auf die Änderung der Eigenschaften der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="33cbb-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="33cbb-158">Was ist, wenn Sie radikalere Änderungen am Erscheinungsbild der Schaltfläche vornehmen möchten?</span><span class="sxs-lookup"><span data-stu-id="33cbb-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="33cbb-159">Vorlagen ermöglichen eine leistungsstarke Steuerung der Darstellung eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="33cbb-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="33cbb-160">Da Vorlagen innerhalb von Stilen verwendet werden können, können Sie eine Vorlage auf alle Objekte anwenden, auf die der Stil angewendet wird (in dieser exemplarischen Vorgehensweise die Schaltfläche).</span><span class="sxs-lookup"><span data-stu-id="33cbb-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="33cbb-161">So verwenden Sie die Vorlage, um das Aussehen der Schaltfläche zu definieren</span><span class="sxs-lookup"><span data-stu-id="33cbb-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="33cbb-162">**Richten Sie die Vorlage ein:** Da <xref:System.Windows.Controls.Button> Steuerelemente <xref:System.Windows.Controls.Control.Template%2A> wie eine Eigenschaft vorhanden sind, können Sie den Wert der <xref:System.Windows.Style> Vorlageneigenschaft genau wie die anderen Eigenschaftswerte definieren, die wir in a mit einer <xref:System.Windows.Setter>festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="33cbb-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="33cbb-163">Fügen Sie das folgende hervorgehobene Markup zu Ihrem Schaltflächenstil hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="33cbb-164">**Änderungsschaltflächenpräsentation:** An diesem Punkt müssen Sie die Vorlage definieren.</span><span class="sxs-lookup"><span data-stu-id="33cbb-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="33cbb-165">Fügen Sie das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-165">Add the following highlighted markup.</span></span> <span data-ttu-id="33cbb-166">Dieses Markup gibt <xref:System.Windows.Shapes.Rectangle> zwei Elemente mit abgerundeten Kanten an, gefolgt von einer <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="33cbb-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="33cbb-167">Der <xref:System.Windows.Controls.DockPanel> wird verwendet, <xref:System.Windows.Controls.ContentPresenter> um die Schaltfläche zu hosten.</span><span class="sxs-lookup"><span data-stu-id="33cbb-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="33cbb-168">A <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche an.</span><span class="sxs-lookup"><span data-stu-id="33cbb-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="33cbb-169">In dieser exemplarischen Vorgehensweise ist der Inhalt Text ("Button 1", "Button 2", "Button 3").</span><span class="sxs-lookup"><span data-stu-id="33cbb-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="33cbb-170">Alle Vorlagenkomponenten (die Rechtecke <xref:System.Windows.Controls.DockPanel>und die ) sind <xref:System.Windows.Controls.Grid>innerhalb einer angeordnet.</span><span class="sxs-lookup"><span data-stu-id="33cbb-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="33cbb-171">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-171">Press F5 to run the application.</span></span> <span data-ttu-id="33cbb-172">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-172">It should look like the following.</span></span>

     ![Fenster mit 3 Tasten](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="33cbb-174">**Fügen Sie der Vorlage einen Glaseffekt hinzu:** Als nächstes fügen Sie das Glas hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="33cbb-175">Zuerst erstellen Sie einige Ressourcen, die einen Glasgradienteneffekt erzeugen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="33cbb-176">Fügen Sie diese Verlaufsressourcen an einer beliebigen Stelle innerhalb des `Application.Resources` Blocks hinzu:</span><span class="sxs-lookup"><span data-stu-id="33cbb-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="33cbb-177">Diese Ressourcen werden <xref:System.Windows.Shapes.Shape.Fill%2A> als die für ein <xref:System.Windows.Controls.Grid> Rechteck verwendet, das wir in die der Schaltflächenvorlage einfügen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="33cbb-178">Fügen Sie der Vorlage das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="33cbb-179">Beachten Sie, dass <xref:System.Windows.UIElement.Opacity%2A> das `x:Name` Rechteck mit der Eigenschaft "glassCube" 0 ist, sodass beim Ausführen des Beispiels das Glasrechteck nicht überlagert wird.</span><span class="sxs-lookup"><span data-stu-id="33cbb-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="33cbb-180">Dies liegt daran, dass wir später Trigger zur Vorlage hinzufügen, wenn der Benutzer mit der Schaltfläche interagiert.</span><span class="sxs-lookup"><span data-stu-id="33cbb-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="33cbb-181">Sie können jedoch sehen, wie die Schaltfläche <xref:System.Windows.UIElement.Opacity%2A> jetzt aussieht, indem Sie den Wert auf 1 ändern und die Anwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="33cbb-182">Dies wird in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="33cbb-182">See the following figure.</span></span> <span data-ttu-id="33cbb-183">Bevor Sie mit dem nächsten <xref:System.Windows.UIElement.Opacity%2A> Schritt fortfahren, ändern Sie die Rückseite auf 0.</span><span class="sxs-lookup"><span data-stu-id="33cbb-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="33cbb-184">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="33cbb-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="33cbb-185">Erstellen von Button Interaktivität</span><span class="sxs-lookup"><span data-stu-id="33cbb-185">Create Button Interactivity</span></span>

<span data-ttu-id="33cbb-186">In diesem Abschnitt erstellen Sie Eigenschaftstrigger und Ereignistrigger, um Eigenschaftswerte zu ändern und Animationen als Reaktion auf Benutzeraktionen auszuführen, z. B. das Verschieben des Mauszeigers über die Schaltfläche und klicken.</span><span class="sxs-lookup"><span data-stu-id="33cbb-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="33cbb-187">Eine einfache Möglichkeit zum Hinzufügen von Interaktivität (Mausüber- und Maus-Leave, Klicken usw.) besteht darin, Trigger in Ihrer Vorlage oder Ihrem Stil zu definieren.</span><span class="sxs-lookup"><span data-stu-id="33cbb-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="33cbb-188">Um eine <xref:System.Windows.Trigger>zu erstellen, definieren Sie eine Eigenschaft <xref:System.Windows.UIElement.IsMouseOver%2A> "Bedingung" `true`wie: Der Wert der Schaltflächeneigenschaft ist gleich .</span><span class="sxs-lookup"><span data-stu-id="33cbb-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="33cbb-189">Anschließend definieren Sie Setter (Aktionen), die stattfinden, wenn die Triggerbedingung wahr ist.</span><span class="sxs-lookup"><span data-stu-id="33cbb-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="33cbb-190">So erstellen Sie Schaltflächeninteraktivität</span><span class="sxs-lookup"><span data-stu-id="33cbb-190">To create button interactivity</span></span>

1. <span data-ttu-id="33cbb-191">**Vorlagentrigger hinzufügen:** Fügen Sie der Vorlage das hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="33cbb-192">**Eigenschaftentrigger hinzufügen:** Fügen Sie dem `ControlTemplate.Triggers` Block das hervorgehobene Markup hinzu:</span><span class="sxs-lookup"><span data-stu-id="33cbb-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="33cbb-193">Drücken Sie F5, um die Anwendung auszuführen, und sehen Sie den Effekt, während Sie den Mauszeiger über die Schaltflächen ausführen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="33cbb-194">**Hinzufügen eines Fokustriggers:** Als Nächstes fügen wir einige ähnliche Setter hinzu, um den Fall zu behandeln, wenn die Schaltfläche den Fokus hat (z. B. nachdem der Benutzer darauf geklickt hat).</span><span class="sxs-lookup"><span data-stu-id="33cbb-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="33cbb-195">Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="33cbb-196">Beachten Sie, dass die Schaltfläche hervorgehoben bleibt, nachdem Sie darauf geklickt haben, da sie immer noch den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="33cbb-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="33cbb-197">Wenn Sie auf eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während die letzte Sie verlieren.</span><span class="sxs-lookup"><span data-stu-id="33cbb-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="33cbb-198">**Fügen Sie Animationen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** Als nächstes fügen wir einige Animationen zu den Triggern hinzu.  </span><span class="sxs-lookup"><span data-stu-id="33cbb-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="33cbb-199">Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des `ControlTemplate.Triggers` Blocks hinzu.</span><span class="sxs-lookup"><span data-stu-id="33cbb-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="33cbb-200">Das Glasrechteck wird verkleinert, wenn sich der Mauszeiger über die Schaltfläche bewegt, und kehrt zum normalen Zeiger zurück, wenn der Zeiger verlässt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="33cbb-201">Es gibt zwei Animationen, die ausgelöst werden,<xref:System.Windows.UIElement.MouseEnter> wenn der Zeiger über die Schaltfläche geht (Ereignis wird ausgelöst).</span><span class="sxs-lookup"><span data-stu-id="33cbb-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="33cbb-202">Diese Animationen verkleinern das Glasrechteck entlang der X- und Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="33cbb-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="33cbb-203">Beachten Sie die <xref:System.Windows.Media.Animation.DoubleAnimation> Eigenschaften <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>der Elemente — und .</span><span class="sxs-lookup"><span data-stu-id="33cbb-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="33cbb-204">Der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> mehr als eine halbe Sekunde dauert, und gibt an, dass das Glas um 10 % schrumpft.</span><span class="sxs-lookup"><span data-stu-id="33cbb-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="33cbb-205">Der zweite Ereignisauslöser (<xref:System.Windows.UIElement.MouseLeave>) stoppt einfach den ersten.</span><span class="sxs-lookup"><span data-stu-id="33cbb-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="33cbb-206">Wenn Sie <xref:System.Windows.Media.Animation.Storyboard>eine beenden, kehren alle animierten Eigenschaften zu ihren Standardwerten zurück.</span><span class="sxs-lookup"><span data-stu-id="33cbb-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="33cbb-207">Wenn der Benutzer den Mauszeiger von der Schaltfläche entfernt, kehrt die Schaltfläche daher zu der Art zurück, wie sie war, bevor der Mauszeiger über die Schaltfläche bewegt wurde.</span><span class="sxs-lookup"><span data-stu-id="33cbb-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="33cbb-208">Weitere Informationen zu Animationen finden Sie unter [Animationsübersicht](../graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33cbb-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="33cbb-209">**Fügen Sie eine Animation hinzu, wenn auf die Schaltfläche geklickt wird:** Der letzte Schritt besteht darin, einen Trigger hinzuzufügen, wenn der Benutzer auf die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="33cbb-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="33cbb-210">Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des `ControlTemplate.Triggers` Blocks hinzu:</span><span class="sxs-lookup"><span data-stu-id="33cbb-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="33cbb-211">Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="33cbb-212">Wenn Sie auf eine Schaltfläche klicken, dreht sich das Glasrechteck um.</span><span class="sxs-lookup"><span data-stu-id="33cbb-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="33cbb-213">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="33cbb-213">Summary</span></span>
 <span data-ttu-id="33cbb-214">In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="33cbb-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="33cbb-215">Gezielt <xref:System.Windows.Style> a auf einen<xref:System.Windows.Controls.Button>Objekttyp ( ).</span><span class="sxs-lookup"><span data-stu-id="33cbb-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="33cbb-216">Kontrollierte grundlegende Eigenschaften der Schaltflächen in <xref:System.Windows.Style>der gesamten Anwendung mit der .</span><span class="sxs-lookup"><span data-stu-id="33cbb-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="33cbb-217">Ressourcen wie Farbverläufe erstellt, die <xref:System.Windows.Style> für Eigenschaftswerte der Setter verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="33cbb-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="33cbb-218">Angepasst eisern das Aussehen von Schaltflächen in der gesamten Anwendung, indem Sie eine Vorlage auf die Schaltflächen anwenden.</span><span class="sxs-lookup"><span data-stu-id="33cbb-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="33cbb-219">Angepasstes Verhalten für die Schaltflächen als <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>Reaktion <xref:System.Windows.Controls.Primitives.ButtonBase.Click>auf Benutzeraktionen (z. B. , und ), die Animationseffekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="33cbb-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="33cbb-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33cbb-220">See also</span></span>

- [<span data-ttu-id="33cbb-221">Erstellen einer Schaltfläche mit Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="33cbb-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="33cbb-222">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="33cbb-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="33cbb-223">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="33cbb-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="33cbb-224">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="33cbb-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="33cbb-225">Übersicht über Bitmapeffekte</span><span class="sxs-lookup"><span data-stu-id="33cbb-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
