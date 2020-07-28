---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
description: In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine animierte Schaltfläche zur Verwendung in einer Windows Presentation Foundation Anwendung mithilfe von XAML erstellen.
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 136d1ad5d6fefd70f0d977e5287ae75f06c52d36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164850"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="8bae5-103">Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML</span><span class="sxs-lookup"><span data-stu-id="8bae5-103">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="8bae5-104">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine animierte Schaltfläche zur Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-104">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="8bae5-105">Diese exemplarische Vorgehensweise verwendet Stile und eine Vorlage, um eine angepasste Schaltflächen Ressource zu erstellen, die die Wiederverwendung von Code und die Trennung der Schaltflächen Logik von der Schaltflächen Deklaration</span><span class="sxs-lookup"><span data-stu-id="8bae5-105">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="8bae5-106">Diese exemplarische Vorgehensweise ist vollständig in geschrieben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bae5-106">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bae5-107">Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Erstellen der Anwendung, indem Sie in Visual Studio eingeben oder kopieren und einfügen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bae5-107">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="8bae5-108">Wenn Sie lieber erfahren möchten, wie Sie einen Designer verwenden, um dieselbe Anwendung zu erstellen, finden Sie unter [Erstellen einer Schaltfläche mit Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-108">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="8bae5-109">In der folgenden Abbildung sind die Schaltflächen fertig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-109">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="8bae5-110">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="8bae5-110">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="8bae5-111">Grundlegende Schaltflächen erstellen</span><span class="sxs-lookup"><span data-stu-id="8bae5-111">Create Basic Buttons</span></span>

<span data-ttu-id="8bae5-112">Erstellen Sie zunächst ein neues Projekt, und fügen Sie dem Fenster einige Schaltflächen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-112">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="8bae5-113">So erstellen Sie ein neues WPF-Projekt und fügen dem Fenster Schaltflächen hinzu</span><span class="sxs-lookup"><span data-stu-id="8bae5-113">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="8bae5-114">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8bae5-114">Start Visual Studio.</span></span>

2. <span data-ttu-id="8bae5-115">**Erstellen Sie ein neues WPF-Projekt:** Zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="8bae5-115">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="8bae5-116">Suchen Sie die Vorlage **Windows-Anwendung (WPF)** , und benennen Sie das Projekt mit dem Namen "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="8bae5-116">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="8bae5-117">Dadurch wird das Gerüst für die Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-117">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="8bae5-118">**Einfache Standard Schaltflächen hinzufügen:** Alle Dateien, die Sie für diese exemplarische Vorgehensweise benötigen, werden von der Vorlage bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-118">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="8bae5-119">Öffnen Sie die Datei Window1. XAML, indem Sie in Projektmappen-Explorer auf die Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="8bae5-119">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="8bae5-120">Standardmäßig ist ein- <xref:System.Windows.Controls.Grid> Element in Window1. XAML vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-120">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="8bae5-121">Entfernen <xref:System.Windows.Controls.Grid> Sie das-Element, und fügen Sie der Seite einige Schaltflächen hinzu, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] indem Sie den folgenden hervorgehobenen Code in Window1. xaml eingeben oder kopieren und einfügen:</span><span class="sxs-lookup"><span data-stu-id="8bae5-121">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

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

     <span data-ttu-id="8bae5-122">Drücken Sie F5, um die Anwendung auszuführen. Es sollte eine Reihe von Schaltflächen angezeigt werden, die wie in der folgenden Abbildung aussehen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-122">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="8bae5-123">![Drei grundlegende Schaltflächen](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="8bae5-123">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="8bae5-124">Nachdem Sie nun die grundlegenden Schaltflächen erstellt haben, sind Sie mit der Arbeit in der Datei Window1. XAML fertig.</span><span class="sxs-lookup"><span data-stu-id="8bae5-124">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="8bae5-125">Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei app. XAML, in der Stile und eine Vorlage für die Schaltflächen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-125">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="8bae5-126">Festlegen von grundlegenden Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8bae5-126">Set Basic Properties</span></span>

<span data-ttu-id="8bae5-127">Als nächstes legen wir einige Eigenschaften für diese Schaltflächen fest, um die Darstellung und das Layout der Schaltfläche zu steuern.</span><span class="sxs-lookup"><span data-stu-id="8bae5-127">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="8bae5-128">Anstatt die Eigenschaften für die Schaltflächen einzeln festzulegen, verwenden Sie Ressourcen, um Schaltflächen Eigenschaften für die gesamte Anwendung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8bae5-128">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="8bae5-129">Anwendungs Ressourcen sind konzeptionell vergleichbar mit externen Cascading Stylesheets (CSS) für Webseiten. Ressourcen sind jedoch viel leistungsfähiger als Cascading Stylesheets (CSS), wie Sie am Ende dieser exemplarischen Vorgehensweise sehen werden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-129">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="8bae5-130">Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="8bae5-130">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="8bae5-131">So verwenden Sie Stile zum Festlegen grundlegender Eigenschaften auf den Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="8bae5-131">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="8bae5-132">**Definieren eines "Application. Resources"-Blocks:** Öffnen Sie App. XAML, und fügen Sie das folgende hervorgehobene Markup hinzu, wenn es nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="8bae5-132">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

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

     <span data-ttu-id="8bae5-133">Der Ressourcenbereich wird bestimmt, wo Sie die Ressource definieren.</span><span class="sxs-lookup"><span data-stu-id="8bae5-133">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="8bae5-134">Durch Definieren von Ressourcen in `Application.Resources` in der Datei "App. XAML" kann die Ressource von überall in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-134">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="8bae5-135">Weitere Informationen zum Definieren des Umfangs ihrer Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="8bae5-135">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="8bae5-136">**Erstellen Sie einen Stil, und definieren Sie grundlegende Eigenschaftswerte damit:** Fügen Sie dem-Block das folgende Markup hinzu `Application.Resources` .</span><span class="sxs-lookup"><span data-stu-id="8bae5-136">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="8bae5-137">Dieses Markup erstellt eine <xref:System.Windows.Style> , die für alle Schaltflächen in der Anwendung gilt, wobei der <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und auf 10 festgelegt wird <xref:System.Windows.FrameworkElement.Margin%2A> :</span><span class="sxs-lookup"><span data-stu-id="8bae5-137">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="8bae5-138">Die- <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der Stil für alle Objekte vom Typ gilt <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-138">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="8bae5-139">Jeder <xref:System.Windows.Setter> legt einen anderen Eigenschafts Wert für fest <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-139">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="8bae5-140">Daher hat an diesem Punkt jede Schaltfläche in der Anwendung eine Breite von 90 und einen Rand von 10.</span><span class="sxs-lookup"><span data-stu-id="8bae5-140">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="8bae5-141">Wenn Sie F5 drücken, um die Anwendung auszuführen, wird das folgende Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-141">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="8bae5-142">![Schaltflächen mit einer Breite von 90 und einem Rand von 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="8bae5-142">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="8bae5-143">Es gibt noch viel mehr Möglichkeiten mit Stilen, einschließlich einer Vielzahl von Möglichkeiten, um zu optimieren, welche Objekte als Ziel verwendet werden, wie komplexe Eigenschaftswerte angegeben werden, und sogar Stile als Eingabe für andere Stile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-143">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="8bae5-144">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8bae5-144">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="8bae5-145">**Legen Sie einen Stil Eigenschafts Wert auf eine Ressource fest:** Ressourcen ermöglichen eine einfache Möglichkeit, häufig definierte Objekte und Werte wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-145">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="8bae5-146">Es ist besonders hilfreich, komplexe Werte mithilfe von Ressourcen zu definieren, um den Code modularer zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="8bae5-146">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="8bae5-147">Fügen Sie der Datei "App. XAML" das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-147">Add the following highlighted markup to app.xaml.</span></span>

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

     <span data-ttu-id="8bae5-148">Direkt unter dem- `Application.Resources` Block haben Sie eine Ressource mit dem Namen "GrayBlueGradientBrush" erstellt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-148">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="8bae5-149">Diese Ressource definiert einen horizontalen Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="8bae5-149">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="8bae5-150">Diese Ressource kann als Eigenschafts Wert von jeder beliebigen Stelle in der Anwendung verwendet werden, einschließlich der Schaltfläche für den Schaltflächen Stil für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8bae5-150">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="8bae5-151">Jetzt haben alle Schaltflächen einen <xref:System.Windows.Controls.Control.Background%2A> Eigenschafts Wert dieses Farbverlaufs.</span><span class="sxs-lookup"><span data-stu-id="8bae5-151">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="8bae5-152">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-152">Press F5 to run the application.</span></span> <span data-ttu-id="8bae5-153">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-153">It should look like the following.</span></span>

     <span data-ttu-id="8bae5-154">![Schaltflächen mit einem Farbverlaufshintergrund](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="8bae5-154">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="8bae5-155">Erstellen einer Vorlage, die das Aussehen der Schaltfläche definiert</span><span class="sxs-lookup"><span data-stu-id="8bae5-155">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="8bae5-156">In diesem Abschnitt erstellen Sie eine Vorlage, mit der die Darstellung (Darstellung) der Schaltfläche angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="8bae5-156">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="8bae5-157">Die Darstellung der Schaltfläche besteht aus mehreren Objekten, einschließlich Rechtecke und anderen Komponenten, um der Schaltfläche ein eindeutiges aussehen zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-157">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="8bae5-158">Bisher wurde die Steuerung, wie Schaltflächen in der Anwendung aussehen, auf das Ändern der Eigenschaften der Schaltfläche beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-158">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="8bae5-159">Was geschieht, wenn Sie radikale Änderungen an der Darstellung der Schaltfläche vornehmen möchten?</span><span class="sxs-lookup"><span data-stu-id="8bae5-159">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="8bae5-160">Vorlagen ermöglichen eine leistungsstarke Kontrolle über die Darstellung eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="8bae5-160">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="8bae5-161">Da Vorlagen in Stilen verwendet werden können, können Sie eine Vorlage auf alle Objekte anwenden, auf die sich der Stil bezieht (in dieser exemplarischen Vorgehensweise die Schaltfläche).</span><span class="sxs-lookup"><span data-stu-id="8bae5-161">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="8bae5-162">So definieren Sie mit der Vorlage das Aussehen der Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="8bae5-162">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="8bae5-163">**Einrichten der Vorlage:** Da Steuerelemente wie <xref:System.Windows.Controls.Button> über eine- <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft verfügen, können Sie den Eigenschafts Wert der Vorlage genau wie die anderen Eigenschaftswerte definieren, die wir in einem mithilfe von festgelegt haben <xref:System.Windows.Style> <xref:System.Windows.Setter> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-163">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="8bae5-164">Fügen Sie dem Schaltflächen Stil das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-164">Add the following highlighted markup to your button style.</span></span>

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

2. <span data-ttu-id="8bae5-165">**Alter Button-Präsentation:** An diesem Punkt müssen Sie die Vorlage definieren.</span><span class="sxs-lookup"><span data-stu-id="8bae5-165">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="8bae5-166">Fügen Sie das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-166">Add the following highlighted markup.</span></span> <span data-ttu-id="8bae5-167">Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle> Elemente mit abgerundeten Kanten an, gefolgt von einer <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-167">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="8bae5-168">Der <xref:System.Windows.Controls.DockPanel> wird zum Hosten des <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bae5-168">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="8bae5-169">Ein <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche an.</span><span class="sxs-lookup"><span data-stu-id="8bae5-169">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="8bae5-170">In dieser exemplarischen Vorgehensweise ist der Inhalt Text ("Button 1", "Button 2", "Schaltfläche 3").</span><span class="sxs-lookup"><span data-stu-id="8bae5-170">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="8bae5-171">Alle Vorlagen Komponenten (Rechtecke und <xref:System.Windows.Controls.DockPanel> ) werden in einer angeordnet <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-171">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

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

     <span data-ttu-id="8bae5-172">Drücken Sie die Taste F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-172">Press F5 to run the application.</span></span> <span data-ttu-id="8bae5-173">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-173">It should look like the following.</span></span>

     ![Fenster mit drei Schaltflächen](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="8bae5-175">**Fügen Sie der Vorlage einen glasseffect hinzu:** Als Nächstes fügen Sie das Glas hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-175">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="8bae5-176">Zuerst erstellen Sie einige Ressourcen, die einen Glas Farbverlaufs Effekt erzeugen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-176">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="8bae5-177">Fügen Sie diese Farbverlaufs Ressourcen an einer beliebigen Stelle innerhalb des `Application.Resources` Blocks</span><span class="sxs-lookup"><span data-stu-id="8bae5-177">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

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

     <span data-ttu-id="8bae5-178">Diese Ressourcen werden als <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck verwendet, das in die <xref:System.Windows.Controls.Grid> der Schaltflächen Vorlage eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8bae5-178">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="8bae5-179">Fügen Sie der Vorlage das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-179">Add the following highlighted markup to the template.</span></span>

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

     <span data-ttu-id="8bae5-180">Beachten Sie, dass der <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der- `x:Name` Eigenschaft von "glassCube" den Wert 0 hat. Wenn Sie das Beispiel ausführen, wird das Glas Rechteck nicht oberhalb der oberen Position angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-180">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="8bae5-181">Dies liegt daran, dass später der Vorlage Trigger hinzugefügt werden, wenn der Benutzer mit der Schaltfläche interagiert.</span><span class="sxs-lookup"><span data-stu-id="8bae5-181">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="8bae5-182">Sie können jedoch sehen, wie die Schaltfläche jetzt aussieht, indem Sie den <xref:System.Windows.UIElement.Opacity%2A> Wert in 1 ändern und die Anwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-182">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="8bae5-183">Dies wird in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8bae5-183">See the following figure.</span></span> <span data-ttu-id="8bae5-184">Bevor Sie mit dem nächsten Schritt fortfahren, ändern <xref:System.Windows.UIElement.Opacity%2A> Sie zurück in 0.</span><span class="sxs-lookup"><span data-stu-id="8bae5-184">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="8bae5-185">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="8bae5-185">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="8bae5-186">Interaktivität zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="8bae5-186">Create Button Interactivity</span></span>

<span data-ttu-id="8bae5-187">In diesem Abschnitt erstellen Sie Eigenschafts Trigger und Ereignis Trigger, um Eigenschaftswerte zu ändern und Animationen als Reaktion auf Benutzeraktionen auszuführen, z. b. das Bewegen des Mauszeigers über die Schaltfläche und das Klicken auf.</span><span class="sxs-lookup"><span data-stu-id="8bae5-187">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="8bae5-188">Eine einfache Möglichkeit, Interaktivität hinzuzufügen (Mouseover, Mouseover, Click usw.), besteht darin, Trigger innerhalb Ihrer Vorlage oder Ihres Stils zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8bae5-188">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="8bae5-189">Um einen zu erstellen <xref:System.Windows.Trigger> , definieren Sie eine Eigenschaft "Bedingung", z. b <xref:System.Windows.UIElement.IsMouseOver%2A> .: der Eigenschafts Wert der Schaltfläche ist gleich `true` .</span><span class="sxs-lookup"><span data-stu-id="8bae5-189">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="8bae5-190">Dann definieren Sie Setter (Aktionen), die stattfinden, wenn die Auslöserbedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="8bae5-190">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="8bae5-191">So erstellen Sie Schaltflächen-Interaktivität</span><span class="sxs-lookup"><span data-stu-id="8bae5-191">To create button interactivity</span></span>

1. <span data-ttu-id="8bae5-192">**Vorlagen Trigger hinzufügen:** Fügen Sie der Vorlage das hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-192">**Add template triggers:** Add the highlighted markup to your template.</span></span>

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

2. <span data-ttu-id="8bae5-193">**Eigenschafts Trigger hinzufügen:** Fügen Sie dem Block das hervorgehobene Markup hinzu `ControlTemplate.Triggers` :</span><span class="sxs-lookup"><span data-stu-id="8bae5-193">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="8bae5-194">Drücken Sie F5, um die Anwendung auszuführen, und sehen Sie sich den Effekt an, während Sie den Mauszeiger über den Schaltflächen ausführen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-194">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="8bae5-195">**Hinzufügen eines Fokus Auslösers:** Als Nächstes fügen wir einige ähnliche Setter hinzu, um den Fall zu behandeln, dass die Schaltfläche den Fokus besitzt (z. b. Nachdem der Benutzer darauf geklickt hat).</span><span class="sxs-lookup"><span data-stu-id="8bae5-195">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

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

     <span data-ttu-id="8bae5-196">Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-196">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="8bae5-197">Beachten Sie, dass die Schaltfläche hervorgehoben bleibt, nachdem Sie darauf geklickt haben, da Sie noch den Fokus besitzt</span><span class="sxs-lookup"><span data-stu-id="8bae5-197">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="8bae5-198">Wenn Sie auf eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während der letzte die Schaltfläche verliert.</span><span class="sxs-lookup"><span data-stu-id="8bae5-198">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="8bae5-199">**Animationen hinzufügen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** Als Nächstes fügen wir den Triggern einige Animationen hinzu.  </span><span class="sxs-lookup"><span data-stu-id="8bae5-199">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="8bae5-200">Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des- `ControlTemplate.Triggers` Blocks hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bae5-200">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

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

     <span data-ttu-id="8bae5-201">Das Glas Rechteck verkleinert sich, wenn der Mauszeiger über die Schaltfläche bewegt wird, und kehrt zur normalen Größe zurück, wenn der Zeiger verlässt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-201">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="8bae5-202">Zwei Animationen werden ausgelöst, wenn der Mauszeiger über die Schaltfläche bewegt wird (das- <xref:System.Windows.UIElement.MouseEnter> Ereignis wird ausgelöst).</span><span class="sxs-lookup"><span data-stu-id="8bae5-202">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="8bae5-203">Diese Animationen verkleinern das Glas Rechteck entlang der X-und Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="8bae5-203">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="8bae5-204">Beachten Sie die Eigenschaften der <xref:System.Windows.Media.Animation.DoubleAnimation> Elemente – <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-204">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="8bae5-205">Der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation über eine halbe Sekunde ausgeführt wird, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10% verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="8bae5-205">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="8bae5-206">Der zweite Ereignis auslöst ( <xref:System.Windows.UIElement.MouseLeave> ) beendet einfach den ersten.</span><span class="sxs-lookup"><span data-stu-id="8bae5-206">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="8bae5-207">Wenn Sie ein Beenden <xref:System.Windows.Media.Animation.Storyboard> , werden alle animierten Eigenschaften auf die Standardwerte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8bae5-207">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="8bae5-208">Wenn der Benutzer den Mauszeiger auf die Schaltfläche verschiebt, wird die Schaltfläche auf die Art und Weise zurückgesetzt, in der sich der Mauszeiger über die Schaltfläche bewegt hat.</span><span class="sxs-lookup"><span data-stu-id="8bae5-208">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="8bae5-209">Weitere Informationen zu Animationen finden Sie unter [Übersicht](../graphics-multimedia/animation-overview.md)über Animationen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-209">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="8bae5-210">**Fügen Sie eine Animation für hinzu, wenn auf die Schaltfläche geklickt wird:** Der letzte Schritt ist das Hinzufügen eines-Auslösers, wenn der Benutzer auf die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="8bae5-210">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="8bae5-211">Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des- `ControlTemplate.Triggers` Blocks hinzu:</span><span class="sxs-lookup"><span data-stu-id="8bae5-211">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

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

     <span data-ttu-id="8bae5-212">Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="8bae5-212">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="8bae5-213">Wenn Sie auf eine Schaltfläche klicken, dreht sich das Glas Rechteck herum.</span><span class="sxs-lookup"><span data-stu-id="8bae5-213">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="8bae5-214">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8bae5-214">Summary</span></span>
 <span data-ttu-id="8bae5-215">In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8bae5-215">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="8bae5-216">Als Ziel <xref:System.Windows.Style> für einen Objekttyp ( <xref:System.Windows.Controls.Button> ).</span><span class="sxs-lookup"><span data-stu-id="8bae5-216">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="8bae5-217">Die grundlegenden Eigenschaften der Schaltflächen in der gesamten Anwendung werden mithilfe von gesteuert <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-217">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="8bae5-218">Es wurden Ressourcen wie Farbverläufe erstellt, die für Eigenschaftswerte der Setter verwendet werden <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="8bae5-218">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="8bae5-219">Sie haben das Aussehen von Schaltflächen in der gesamten Anwendung angepasst, indem Sie eine Vorlage auf die Schaltflächen anwenden.</span><span class="sxs-lookup"><span data-stu-id="8bae5-219">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="8bae5-220">Benutzerdefiniertes Verhalten für die Schaltflächen als Reaktion auf Benutzeraktionen (z. b. <xref:System.Windows.UIElement.MouseEnter> , <xref:System.Windows.UIElement.MouseLeave> und <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ), die Animationseffekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="8bae5-220">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bae5-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bae5-221">See also</span></span>

- [<span data-ttu-id="8bae5-222">Erstellen einer Schaltfläche mit Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="8bae5-222">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="8bae5-223">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8bae5-223">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8bae5-224">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="8bae5-224">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="8bae5-225">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="8bae5-225">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="8bae5-226">Übersicht über Bitmapeffekte</span><span class="sxs-lookup"><span data-stu-id="8bae5-226">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
