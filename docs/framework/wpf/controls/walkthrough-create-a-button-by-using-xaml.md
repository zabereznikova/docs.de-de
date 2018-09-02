---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 96d54efbabbd95a24f1fb7118305ddbff4dfd110
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415823"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="266c7-102">Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML</span><span class="sxs-lookup"><span data-stu-id="266c7-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="266c7-103">Das Ziel dieser exemplarischen Vorgehensweise werden erfahren, wie Sie eine animierte Schaltfläche für die Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="266c7-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="266c7-104">In dieser exemplarischen Vorgehensweise verwendet und eine Vorlage zum Erstellen einer benutzerdefinierten Schaltflächenressource, die Wiederverwendung von Code und die Trennung von aus der Schaltflächendeklaration ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="266c7-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="266c7-105">In dieser exemplarischen Vorgehensweise wird ausschließlich in geschrieben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="266c7-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="266c7-106">Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Erstellen der Anwendung durch eingeben oder kopieren und Einfügen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="266c7-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="266c7-107">Wenn Sie erfahren lieber, wie Sie ein Design-Tool (Microsoft Expression Blend) mit die gleiche Anwendung zu erstellen, finden Sie unter [erstellen Sie eine Schaltfläche mithilfe von Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="266c7-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="266c7-108">Die folgende Abbildung zeigt die Schaltflächen fertig.</span><span class="sxs-lookup"><span data-stu-id="266c7-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="266c7-109">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="266c7-109">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="266c7-110">Erstellen von grundlegenden Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="266c7-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="266c7-111">Beginnen Sie durch Erstellen eines neuen Projekts und einige Schaltflächen hinzufügen, um das Fenster.</span><span class="sxs-lookup"><span data-stu-id="266c7-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="266c7-112">Erstellen eines neuen WPF-Projekts und Hinzufügen von Schaltflächen für das Fenster</span><span class="sxs-lookup"><span data-stu-id="266c7-112">To create a new WPF project and add buttons to the window</span></span>  
  
1.  <span data-ttu-id="266c7-113">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="266c7-113">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="266c7-114">**Erstellen eines neuen WPF-Projekts:** auf die **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="266c7-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="266c7-115">Suchen der **Windows-Anwendung (WPF)** Vorlage und geben Sie dem Projekt "den Namen AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="266c7-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="266c7-116">Dadurch wird das Gerüst für die Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="266c7-116">This will create the skeleton for the application.</span></span>  
  
3.  <span data-ttu-id="266c7-117">**Hinzufügen von Standardschaltflächen für basic,:** werden alle Dateien, die in dieser exemplarischen Vorgehensweise Sie müssen von der Vorlage bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="266c7-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="266c7-118">Öffnen Sie die Datei "Window1.xaml", indem Sie auf die sie im Projektmappen-Explorer doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="266c7-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="266c7-119">Es wird standardmäßig ein <xref:System.Windows.Controls.Grid> Element in der Datei Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="266c7-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="266c7-120">Entfernen der <xref:System.Windows.Controls.Grid> Element, und fügen einige Schaltflächen auf der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite eingeben oder kopieren und Einfügen von den folgenden hervorgehobenen Code in die Datei Window1.xaml:</span><span class="sxs-lookup"><span data-stu-id="266c7-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
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
  
     <span data-ttu-id="266c7-121">Drücken Sie F5 zum Ausführen der Anwendung verwendet. Daraufhin sollte eine Reihe von Schaltflächen, die in der folgenden Abbildung aussieht.</span><span class="sxs-lookup"><span data-stu-id="266c7-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="266c7-122">![Drei grundlegende Schaltflächen](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="266c7-122">![Three basic buttons](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="266c7-123">Nun, dass Sie die grundlegende Schaltflächen erstellt haben, können Sie alle erforderlichen Schritte ausgeführt werden, in der Datei "Window1.xaml".</span><span class="sxs-lookup"><span data-stu-id="266c7-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="266c7-124">Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei "App.xaml" Definieren von Stilen und eine Vorlage für die Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="266c7-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="266c7-125">Legen Sie grundlegende Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="266c7-125">Set Basic Properties</span></span>  
 <span data-ttu-id="266c7-126">Als Nächstes legen wir einige Eigenschaften für diese Schaltflächen, um die Darstellung und Layout steuern.</span><span class="sxs-lookup"><span data-stu-id="266c7-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="266c7-127">Anstatt Eigenschaften einzeln auf den Schaltflächen festlegen, werden Sie Ressourcen verwenden, um Schaltflächeneigenschaften für die gesamte Anwendung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="266c7-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="266c7-128">Anwendungsressourcen sind konzeptionell identisch mit externen [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] für Webseiten jedoch Ressourcen sind wesentlich leistungsfähiger als [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], wie Sie am Ende dieser exemplarischen Vorgehensweise sehen.</span><span class="sxs-lookup"><span data-stu-id="266c7-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="266c7-129">Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="266c7-129">To learn more about resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="266c7-130">Um Stile zu verwenden, um grundlegende Eigenschaften für die Schaltflächen festlegen</span><span class="sxs-lookup"><span data-stu-id="266c7-130">To use styles to set basic properties on the buttons</span></span>  
  
1.  <span data-ttu-id="266c7-131">**Definieren Sie einen Block Application.Resources:** "App.xaml" zu öffnen und die folgende hervorgehobene Markup hinzufügen, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="266c7-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
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
  
     <span data-ttu-id="266c7-132">Ressourcenbereich wird durch Sie die Ressource definieren bestimmt.</span><span class="sxs-lookup"><span data-stu-id="266c7-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="266c7-133">Definieren von Ressourcen in `Application.Resources` in app.xaml-Datei kann die Ressource aus an einer beliebigen Stelle in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="266c7-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="266c7-134">Weitere Informationen zum Definieren des Bereichs Ihrer Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="266c7-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
2.  <span data-ttu-id="266c7-135">**Eine Formatvorlage erstellen und grundlegende Eigenschaftswerte mit definieren:** fügen Sie das folgende Markup, das `Application.Resources` Block.</span><span class="sxs-lookup"><span data-stu-id="266c7-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="266c7-136">Dieses Markup erstellt eine <xref:System.Windows.Style> , die für alle Schaltflächen in der Anwendung, die Einstellung gilt die <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und die <xref:System.Windows.FrameworkElement.Margin%2A> auf 10:</span><span class="sxs-lookup"><span data-stu-id="266c7-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="266c7-137">Die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der Stil für alle Objekte des Typs gilt <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="266c7-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="266c7-138">Jede <xref:System.Windows.Setter> legt einen anderen Eigenschaftswert für die <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="266c7-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="266c7-139">Daher muss jede Schaltfläche in der Anwendung an diesem Punkt eine Breite von 90 und einem Rand von 10.</span><span class="sxs-lookup"><span data-stu-id="266c7-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="266c7-140">Wenn Sie zum Ausführen der Anwendung F5 drücken, wird das folgende Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="266c7-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="266c7-141">![Schaltflächen mit einer Breite von 90 und einem Rand von 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="266c7-141">![Buttons with a width of 90 and a margin of 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="266c7-142">Es gibt viele weitere Möglichkeiten mit Stilen, einschließlich eine Vielzahl von Möglichkeiten zum Optimieren, welche Objekte gelten, komplexe Eigenschaftswerte angeben und auch mithilfe von Stilen als Eingabe für andere Stile.</span><span class="sxs-lookup"><span data-stu-id="266c7-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="266c7-143">Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="266c7-143">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
3.  <span data-ttu-id="266c7-144">**Legen Sie einen Stil-Eigenschaftswert auf eine Ressource:** Ressourcen ermöglichen eine einfache Möglichkeit, Wiederverwenden von häufig definierten Objekten und Werte.</span><span class="sxs-lookup"><span data-stu-id="266c7-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="266c7-145">Er ist besonders nützlich, um mit Ressourcen, um den Code etwas modularer gestalten komplexe Werte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="266c7-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="266c7-146">Fügen Sie die folgende hervorgehobene Markup, um "App.xaml".</span><span class="sxs-lookup"><span data-stu-id="266c7-146">Add the following highlighted markup to app.xaml.</span></span>  
  
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
  
     <span data-ttu-id="266c7-147">Direkt unterhalb der `Application.Resources` Block, haben Sie eine Ressource namens "GrayBlueGradientBrush erstellt".</span><span class="sxs-lookup"><span data-stu-id="266c7-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="266c7-148">Dieser Ressource wird einen horizontalen Farbverlauf definiert.</span><span class="sxs-lookup"><span data-stu-id="266c7-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="266c7-149">Diese Ressource verwendet werden kann, als Eigenschaftswert von überall aus in der Anwendung, die auch im Setter für den Stil für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="266c7-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="266c7-150">Jetzt alle Schaltflächen sind eine <xref:System.Windows.Controls.Control.Background%2A> Eigenschaftswert, der diesem Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="266c7-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="266c7-151">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="266c7-151">Press F5 to run the application.</span></span> <span data-ttu-id="266c7-152">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="266c7-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="266c7-153">![Schaltflächen mit einem Farbverlaufshintergrund](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="266c7-153">![Buttons with a gradient background](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="266c7-154">Erstellen Sie eine Vorlage, die das Aussehen der Schaltfläche definiert.</span><span class="sxs-lookup"><span data-stu-id="266c7-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="266c7-155">In diesem Abschnitt erstellen Sie eine Vorlage, die die Darstellung der Schaltfläche (Presentation) passt.</span><span class="sxs-lookup"><span data-stu-id="266c7-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="266c7-156">Die Darstellung der Schaltfläche mehrere Objekte, darunter Rechtecke und anderen Komponenten besteht, geben Sie der Schaltfläche ein charakteristisches Aussehen verleihen.</span><span class="sxs-lookup"><span data-stu-id="266c7-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="266c7-157">Bisher wurde die Kontrolle über die Darstellung von Schaltflächen in der Anwendung beschränkt wurde, zum Ändern der Eigenschaften der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="266c7-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="266c7-158">Was geschieht, wenn Sie möchten die Darstellung der Schaltfläche radikalere Änderungen vornehmen?</span><span class="sxs-lookup"><span data-stu-id="266c7-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="266c7-159">Vorlagen können leistungsstarke Kontrolle über die Darstellung eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="266c7-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="266c7-160">Da Vorlagen innerhalb von Stilen verwendet werden können, können Sie eine Vorlage für alle Objekte anwenden, denen das Format auf (in dieser exemplarischen Vorgehensweise, die Schaltfläche ") angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="266c7-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="266c7-161">Die Vorlage zu verwenden, um das Aussehen der Schaltfläche zu definieren.</span><span class="sxs-lookup"><span data-stu-id="266c7-161">To use the template to define the look of the button</span></span>  
  
1.  <span data-ttu-id="266c7-162">**Richten Sie die Vorlage:** da Steuerelemente wie <xref:System.Windows.Controls.Button> haben eine <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft, können Sie den Wert der Vorlage genau wie die anderen haben wir auf Eigenschaftswerte definieren eine <xref:System.Windows.Style> mithilfe einer <xref:System.Windows.Setter>.</span><span class="sxs-lookup"><span data-stu-id="266c7-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="266c7-163">Fügen Sie die folgende hervorgehobene Markup, um die Schaltflächen-Formatvorlage.</span><span class="sxs-lookup"><span data-stu-id="266c7-163">Add the following highlighted markup to your button style.</span></span>  
  
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
  
2.  <span data-ttu-id="266c7-164">**Ändern der Darstellung der Schaltfläche:** an diesem Punkt müssen Sie die Vorlage zu definieren.</span><span class="sxs-lookup"><span data-stu-id="266c7-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="266c7-165">Fügen Sie das folgende hervorgehobene Markup hinzu.</span><span class="sxs-lookup"><span data-stu-id="266c7-165">Add the following highlighted markup.</span></span> <span data-ttu-id="266c7-166">Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle> Elemente mit abgerundeten Ecken an, gefolgt von einem <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="266c7-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="266c7-167">Die <xref:System.Windows.Controls.DockPanel> wird verwendet, auf dem Host die <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="266c7-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="266c7-168">Ein <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="266c7-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="266c7-169">In dieser exemplarischen Vorgehensweise wird der Inhalt Text ("Schaltfläche" 1","Button 2","Button 3").</span><span class="sxs-lookup"><span data-stu-id="266c7-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="266c7-170">Alle von den Komponenten der Dienstvorlage (Rechtecke und die <xref:System.Windows.Controls.DockPanel>) angeordnet sind, in der ein <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="266c7-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
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
  
     <span data-ttu-id="266c7-171">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="266c7-171">Press F5 to run the application.</span></span> <span data-ttu-id="266c7-172">Es sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="266c7-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="266c7-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="266c7-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3.  <span data-ttu-id="266c7-174">**Fügen Sie einen Glaseffekt auf die Vorlage:** als Nächstes fügen Sie das Glas.</span><span class="sxs-lookup"><span data-stu-id="266c7-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="266c7-175">Erstellen Sie zunächst einige Ressourcen, die einen Glaseffekt für den Farbverlauf zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="266c7-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="266c7-176">Fügen Sie diesen Farbverlauf Ressourcen an einer beliebigen Stelle innerhalb der `Application.Resources` blockieren:</span><span class="sxs-lookup"><span data-stu-id="266c7-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
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
  
     <span data-ttu-id="266c7-177">Diese Ressourcen dienen dazu, wie die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck, das wir in einfügen die <xref:System.Windows.Controls.Grid> der Schaltflächenvorlage.</span><span class="sxs-lookup"><span data-stu-id="266c7-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="266c7-178">Fügen Sie das folgende hervorgehobene Markup der Vorlage hinzu.</span><span class="sxs-lookup"><span data-stu-id="266c7-178">Add the following highlighted markup to the template.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="266c7-179">Beachten Sie, dass die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der `x:Name` "GlassCube"-Eigenschaft ist 0, damit beim Ausführen des Beispiels nicht das Glasrechteck als Überlagerung auf oben angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="266c7-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="266c7-180">Dies ist, da wir später Trigger auf die Vorlage für hinzufügen, wenn der Benutzer mit der Schaltfläche interagiert.</span><span class="sxs-lookup"><span data-stu-id="266c7-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="266c7-181">Sie können jedoch sehen, wie die Schaltfläche mit der jetzt ändern dargestellt die <xref:System.Windows.UIElement.Opacity%2A> Wert 1 und Ausführen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="266c7-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="266c7-182">Das Ergebnis wird in der folgende Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="266c7-182">See the following figure.</span></span> <span data-ttu-id="266c7-183">Vor dem Fortfahren mit dem nächsten Schritt ändern Sie die <xref:System.Windows.UIElement.Opacity%2A> auf 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="266c7-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="266c7-184">![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="266c7-184">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="266c7-185">Gestalten, Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="266c7-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="266c7-186">In diesem Abschnitt erstellen Sie Eigenschaftstrigger und Ereignistrigger Eigenschaftswerte ändern und Ausführen von Animationen als Reaktion auf Benutzeraktionen wie klicken und den Mauszeiger über der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="266c7-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="266c7-187">Eine einfache Möglichkeit zum Hinzufügen von Interaktivität (Mouseover-MouseLeave-, klicken Sie auf und So weiter) werden in der Vorlage oder Stil festlegen.</span><span class="sxs-lookup"><span data-stu-id="266c7-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="266c7-188">Zum Erstellen einer <xref:System.Windows.Trigger>, definieren Sie z. B. eine Eigenschaft "Condition": die Schaltfläche mit den <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaftswert ist gleich `true`.</span><span class="sxs-lookup"><span data-stu-id="266c7-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="266c7-189">Anschließend definieren Sie die Setter (Aktionen), die stattfinden, wenn die auslöserbedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="266c7-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="266c7-190">Schaltfläche Interaktivität</span><span class="sxs-lookup"><span data-stu-id="266c7-190">To create button interactivity</span></span>  
  
1.  <span data-ttu-id="266c7-191">**Hinzufügen von Vorlagentriggern:** fügen Sie das hervorgehobene Markup der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="266c7-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
    ```  
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
  
2.  <span data-ttu-id="266c7-192">**Eigenschaftsauslöser hinzufügen:** fügen Sie das hervorgehobene Markup, das `ControlTemplate.Triggers` blockieren:</span><span class="sxs-lookup"><span data-stu-id="266c7-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="266c7-193">Drücken Sie F5, um die Anwendung auszuführen und die Auswirkung dieser feststellen, wie Sie den Mauszeiger über die Schaltflächen ausführen.</span><span class="sxs-lookup"><span data-stu-id="266c7-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3.  <span data-ttu-id="266c7-194">**Hinzufügen eines Triggers Fokus:** als Nächstes fügen wir einige ähnliche Setter, um Fälle zu behandeln, wenn die Schaltfläche den Fokus (z. B. hat, wenn der Benutzer darauf klickt).</span><span class="sxs-lookup"><span data-stu-id="266c7-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
    ```  
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
  
     <span data-ttu-id="266c7-195">Drücken Sie F5, um die Anwendung auszuführen, und klicken auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="266c7-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="266c7-196">Beachten Sie, dass die Schaltfläche mit der hervorgehobenen bleibt, wenn Sie darauf klicken, da es immer noch den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="266c7-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="266c7-197">Wenn Sie eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während die verliert.</span><span class="sxs-lookup"><span data-stu-id="266c7-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4.  <span data-ttu-id="266c7-198">**Hinzufügen von Animationen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** als Nächstes fügen wir einige Animationen für die Trigger hinzu.</span><span class="sxs-lookup"><span data-stu-id="266c7-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="266c7-199">Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` Block.</span><span class="sxs-lookup"><span data-stu-id="266c7-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="266c7-200">Das Glasrechteck wird reduziert, wenn der Mauszeiger über die Schaltfläche bewegt, und gibt an die normale Größe zurück, wenn der Mauszeiger verlässt.</span><span class="sxs-lookup"><span data-stu-id="266c7-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="266c7-201">Es werden zwei Animationen, die ausgelöst werden, wenn der Zeiger auf die Schaltfläche befindet (<xref:System.Windows.UIElement.MouseEnter> Ereignis wird ausgelöst).</span><span class="sxs-lookup"><span data-stu-id="266c7-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="266c7-202">Diese Animationen verkleinert das Glasrechteck entlang der X- und Y-Achse.</span><span class="sxs-lookup"><span data-stu-id="266c7-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="266c7-203">Beachten Sie die Eigenschaften auf der <xref:System.Windows.Media.Animation.DoubleAnimation> Elemente – <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span><span class="sxs-lookup"><span data-stu-id="266c7-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="266c7-204">Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation über mehr als eine halbe Sekunde auftritt und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10 % verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="266c7-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="266c7-205">Der zweite Ereignistrigger (<xref:System.Windows.UIElement.MouseLeave>) einfach beendet das erste Abonnement.</span><span class="sxs-lookup"><span data-stu-id="266c7-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="266c7-206">Wenn Sie beenden eine <xref:System.Windows.Media.Animation.Storyboard>, alle animierten Eigenschaften auf ihre Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="266c7-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="266c7-207">Aus diesem Grund, wenn der Benutzer den Zeiger der Schaltfläche weg bewegt, wird die Schaltfläche zurück auf die Art und Weise, die vor der Mauszeiger über die Schaltfläche bewegt.</span><span class="sxs-lookup"><span data-stu-id="266c7-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="266c7-208">Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="266c7-208">For more information about animations, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
5.  <span data-ttu-id="266c7-209">**Fügen Sie eine Animation für, wenn die Schaltfläche geklickt wird:** der letzte Schritt ist zum Hinzufügen eines Triggers für, wenn der Benutzer die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="266c7-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="266c7-210">Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` blockieren:</span><span class="sxs-lookup"><span data-stu-id="266c7-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
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
  
     <span data-ttu-id="266c7-211">Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="266c7-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="266c7-212">Wenn Sie eine Schaltfläche klicken, dreht sich um das Glasrechteck.</span><span class="sxs-lookup"><span data-stu-id="266c7-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="266c7-213">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="266c7-213">Summary</span></span>  
 <span data-ttu-id="266c7-214">In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen:</span><span class="sxs-lookup"><span data-stu-id="266c7-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="266c7-215">Ziel einer <xref:System.Windows.Style> in einen Objekttyp (<xref:System.Windows.Controls.Button>).</span><span class="sxs-lookup"><span data-stu-id="266c7-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="266c7-216">Gesteuert von grundlegenden Eigenschaften von Schaltflächen in der gesamten Anwendung mit der <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="266c7-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="266c7-217">Ressourcen wie Farbverläufe, für Eigenschaftswerte erstellt die <xref:System.Windows.Style> Setter.</span><span class="sxs-lookup"><span data-stu-id="266c7-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="266c7-218">Die Darstellung der Schaltflächen in der gesamten Anwendung wird durch Anwenden einer Vorlage auf die Schaltflächen angepasst.</span><span class="sxs-lookup"><span data-stu-id="266c7-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="266c7-219">Anpassen des Verhaltens für die Schaltflächen als Reaktion auf Benutzeraktionen (z. B. <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, und <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), die Animationseffekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="266c7-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266c7-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="266c7-220">See Also</span></span>  
 [<span data-ttu-id="266c7-221">Erstellen einer Schaltfläche mit Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="266c7-221">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [<span data-ttu-id="266c7-222">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="266c7-222">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="266c7-223">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="266c7-223">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="266c7-224">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="266c7-224">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="266c7-225">Übersicht über Bitmapeffekte</span><span class="sxs-lookup"><span data-stu-id="266c7-225">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
