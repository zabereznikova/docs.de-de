---
title: Inhaltsmodell
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738284"
---
# <a name="wpf-content-model"></a><span data-ttu-id="4b549-102">WPF-Inhaltsmodell</span><span class="sxs-lookup"><span data-stu-id="4b549-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="4b549-103">ist eine Präsentationsplattform, die viele Steuerelemente und steuerelementähnliche Typen bereitstellt, deren Hauptaufgabe in der Anzeige unterschiedlicher Inhaltstypen besteht.</span><span class="sxs-lookup"><span data-stu-id="4b549-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="4b549-104">Um zu bestimmen, welches Steuerelement verwendet oder von welchem Steuerelement abgeleitet werden soll, sollten Sie mit den Objektarten vertraut sein, die ein bestimmtes Steuerelement am besten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="4b549-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="4b549-105">In diesem Thema wird das Inhaltsmodell für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente und steuerelementähnliche Typen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4b549-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="4b549-106">Das Inhaltsmodell beschreibt, welche Inhalte in einem Steuerelement verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4b549-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="4b549-107">In diesem Thema werden ebenfalls die Inhaltseigenschaften für jedes Inhaltsmodell aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="4b549-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="4b549-108">Eine Inhaltseigenschaft ist eine Eigenschaft, die zum Speichern des Inhalts des Objekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b549-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="4b549-109">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="4b549-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="4b549-110">Einige Steuerelemente können ein Objekt beliebiger Typen enthalten, z. b. eine Zeichenfolge, ein <xref:System.DateTime> Objekt oder einen <xref:System.Windows.UIElement>, bei dem es sich um einen Container für zusätzliche Elemente handelt.</span><span class="sxs-lookup"><span data-stu-id="4b549-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="4b549-111">Beispielsweise kann ein <xref:System.Windows.Controls.Button> ein Bild und Text enthalten. oder ein <xref:System.Windows.Controls.CheckBox> kann den Wert <xref:System.DateTime.Now%2A?displayProperty=nameWithType>enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b549-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4b549-112">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Klassen, die beliebigen Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b549-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="4b549-113">In der folgenden Tabelle werden die-Klassen aufgelistet, die von <xref:System.Windows.Controls.Control>erben.</span><span class="sxs-lookup"><span data-stu-id="4b549-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="4b549-114">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="4b549-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="4b549-115">Inhalt</span><span class="sxs-lookup"><span data-stu-id="4b549-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="4b549-116">Ein einzelnes beliebiges Objekt</span><span class="sxs-lookup"><span data-stu-id="4b549-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="4b549-117">Ein Header und ein einzelnes Element, die beide beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="4b549-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="4b549-118">Eine Auflistung beliebiger Objekte</span><span class="sxs-lookup"><span data-stu-id="4b549-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="4b549-119">Ein Header und eine Auflistung von Elementen, die alle beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="4b549-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="4b549-120">Steuerelemente, die von diesen Klassen erben, können dieselbe Art von Inhalt enthalten und den Inhalt auf die gleiche Weise behandeln.</span><span class="sxs-lookup"><span data-stu-id="4b549-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="4b549-121">Die folgende Abbildung zeigt ein Steuerelement aus jedem Inhalts Modell, das ein Bild und Text enthält:</span><span class="sxs-lookup"><span data-stu-id="4b549-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![Screenshot, der vier verschiedene Steuerelemente anzeigt, eine aus den einzelnen Inhalts Modellen.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="4b549-123">Steuerelemente mit einem einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="4b549-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="4b549-124">Die <xref:System.Windows.Controls.ContentControl>-Klasse enthält einen einzelnen Teil des beliebigen Inhalts.</span><span class="sxs-lookup"><span data-stu-id="4b549-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="4b549-125">Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="4b549-126">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ContentControl> und verwenden dessen Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="4b549-127">Die folgende Abbildung zeigt vier Schaltflächen, deren <xref:System.Windows.Controls.ContentControl.Content%2A> auf eine Zeichenfolge, ein <xref:System.DateTime> Objekt, eine <xref:System.Windows.Shapes.Rectangle>und eine <xref:System.Windows.Controls.Panel>, die eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält:</span><span class="sxs-lookup"><span data-stu-id="4b549-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Screenshot, der vier Schaltflächen mit unterschiedlichen Inhaltstypen anzeigt](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="4b549-129">Ein Beispiel zum Festlegen der <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaft finden Sie unter <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="4b549-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="4b549-130">Steuerelemente mit einem Header und einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="4b549-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="4b549-131">Die <xref:System.Windows.Controls.HeaderedContentControl>-Klasse erbt von <xref:System.Windows.Controls.ContentControl> und zeigt Inhalt mit einem Header an.</span><span class="sxs-lookup"><span data-stu-id="4b549-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="4b549-132">Er erbt die Content-Eigenschaft (<xref:System.Windows.Controls.ContentControl.Content%2A>) von <xref:System.Windows.Controls.ContentControl> und definiert die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>-Eigenschaft, die vom Typ <xref:System.Object>ist. Daher können beide ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="4b549-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="4b549-133">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedContentControl> und verwenden dessen Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="4b549-134">Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.TabItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="4b549-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="4b549-135">Der erste <xref:System.Windows.Controls.TabItem> verfügt über <xref:System.Windows.UIElement> Objekte als <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="4b549-136">Der <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> wird auf einen <xref:System.Windows.Controls.StackPanel> festgelegt, der eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält.</span><span class="sxs-lookup"><span data-stu-id="4b549-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="4b549-137">Der <xref:System.Windows.Controls.ContentControl.Content%2A> wird auf einen <xref:System.Windows.Controls.StackPanel> festgelegt, der einen <xref:System.Windows.Controls.TextBlock> und einen <xref:System.Windows.Controls.Label>enthält.</span><span class="sxs-lookup"><span data-stu-id="4b549-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="4b549-138">Der zweite <xref:System.Windows.Controls.TabItem> enthält eine Zeichenfolge in der <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und eine <xref:System.Windows.Controls.TextBlock> in der <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![TabControl, das unterschiedliche Typen in der Header-Eigenschaft verwendet.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="4b549-140">Ein Beispiel zum Erstellen von <xref:System.Windows.Controls.TabItem> Objekten finden Sie unter <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="4b549-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="4b549-141">Steuerelemente mit einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="4b549-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="4b549-142">Die <xref:System.Windows.Controls.ItemsControl>-Klasse erbt von <xref:System.Windows.Controls.Control> und kann mehrere Elemente enthalten, wie z. b. Zeichen folgen, Objekte oder andere Elemente.</span><span class="sxs-lookup"><span data-stu-id="4b549-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="4b549-143">Die Inhalts Eigenschaften sind <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="4b549-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> wird in der Regel verwendet, um die <xref:System.Windows.Controls.ItemsControl> mit einer Datensammlung aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="4b549-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="4b549-145">Wenn Sie keine Auflistung zum Auffüllen des <xref:System.Windows.Controls.ItemsControl>verwenden möchten, können Sie mithilfe der Eigenschaft <xref:System.Windows.Controls.ItemsControl.Items%2A> Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4b549-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="4b549-146">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ItemsControl> und verwenden dessen Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="4b549-147">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ListBox>, die diese Elementtypen enthält:</span><span class="sxs-lookup"><span data-stu-id="4b549-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="4b549-148">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4b549-148">A string.</span></span>  
  
- <span data-ttu-id="4b549-149">Ein <xref:System.DateTime>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b549-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="4b549-150">Ein <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="4b549-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="4b549-151">Eine <xref:System.Windows.Controls.Panel>, die eine <xref:System.Windows.Shapes.Ellipse> und eine <xref:System.Windows.Controls.TextBlock>enthält.</span><span class="sxs-lookup"><span data-stu-id="4b549-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Screenshot, der ein ListBox mit vier Inhaltstypen anzeigt](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="4b549-153">Steuerelemente mit einem Header und einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="4b549-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="4b549-154">Die <xref:System.Windows.Controls.HeaderedItemsControl>-Klasse erbt von <xref:System.Windows.Controls.ItemsControl> und kann mehrere Elemente, wie z. b. Zeichen folgen, Objekte oder andere Elemente, und einen Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b549-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="4b549-155">Er erbt die <xref:System.Windows.Controls.ItemsControl> Inhalts Eigenschaften, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>und <xref:System.Windows.Controls.ItemsControl.Items%2A>und definiert die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft, die ein beliebiges Objekt sein kann.</span><span class="sxs-lookup"><span data-stu-id="4b549-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="4b549-156">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedItemsControl> und verwenden dessen Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="4b549-157">Klassen mit einer Auflistung von UIElement-Objekten</span><span class="sxs-lookup"><span data-stu-id="4b549-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="4b549-158">Die <xref:System.Windows.Controls.Panel>-Klasse positioniert und ordnet untergeordnete <xref:System.Windows.UIElement>-Objekte an.</span><span class="sxs-lookup"><span data-stu-id="4b549-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="4b549-159">Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="4b549-160">Die folgenden Klassen erben von der <xref:System.Windows.Controls.Panel>-Klasse und verwenden Ihr Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="4b549-161">Weitere Informationen finden Sie unter [Übersicht über Panel-Elemente](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b549-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="4b549-162">Klassen, die sich auf die Anzeige eines UIElement-Objekts auswirken</span><span class="sxs-lookup"><span data-stu-id="4b549-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="4b549-163">Die <xref:System.Windows.Controls.Decorator>-Klasse wendet visuelle Effekte auf oder um ein einzelnes untergeordnetes <xref:System.Windows.UIElement>an.</span><span class="sxs-lookup"><span data-stu-id="4b549-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="4b549-164">Die Inhalts Eigenschaft ist <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="4b549-165">Die folgenden Klassen erben von <xref:System.Windows.Controls.Decorator> und verwenden dessen Inhalts Modell:</span><span class="sxs-lookup"><span data-stu-id="4b549-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="4b549-166">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.TextBox>, die ein <xref:System.Windows.Controls.Border> um Sie herum enthält (ist).</span><span class="sxs-lookup"><span data-stu-id="4b549-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="4b549-167">![TextBox mit schwarzem Rahmen](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="4b549-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="4b549-168">Textfeld mit einem Rahmen</span><span class="sxs-lookup"><span data-stu-id="4b549-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="4b549-169">Klassen, die visuelles Feedback zu einem UIElement bereitstellen</span><span class="sxs-lookup"><span data-stu-id="4b549-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="4b549-170">Die <xref:System.Windows.Documents.Adorner>-Klasse stellt einem Benutzer visuelle Hinweise bereit.</span><span class="sxs-lookup"><span data-stu-id="4b549-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="4b549-171">Verwenden Sie z. b. eine <xref:System.Windows.Documents.Adorner>, um Elementen funktionale Handles hinzuzufügen oder Zustandsinformationen über ein Steuerelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b549-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="4b549-172">Die <xref:System.Windows.Documents.Adorner>-Klasse stellt ein Framework bereit, sodass Sie Ihre eigenen Adorner erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b549-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="4b549-173">stellt keine implementierten Adorner bereit.</span><span class="sxs-lookup"><span data-stu-id="4b549-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="4b549-174">Weitere Informationen finden Sie unter [Übersicht über Adorner](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b549-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="4b549-175">Klassen, mit denen Benutzer Text eingeben können</span><span class="sxs-lookup"><span data-stu-id="4b549-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="4b549-176">WPF bietet drei primäre Steuerelemente, mit denen Benutzer Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="4b549-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="4b549-177">Jedes Steuerelement zeigt den Text unterschiedlich an.</span><span class="sxs-lookup"><span data-stu-id="4b549-177">Each control displays the text differently.</span></span> <span data-ttu-id="4b549-178">Die folgende Tabelle enthält diese drei textbezogene Steuerelemente, ihre Funktionen bei der Textanzeige und ihre Eigenschaften, die den Text des Steuerelements enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b549-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="4b549-179">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4b549-179">Control</span></span>|<span data-ttu-id="4b549-180">Text wird angezeigt als</span><span class="sxs-lookup"><span data-stu-id="4b549-180">Text is displayed as</span></span>|<span data-ttu-id="4b549-181">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="4b549-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="4b549-182">Unverschlüsselter Text</span><span class="sxs-lookup"><span data-stu-id="4b549-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="4b549-183">Formatierter Text</span><span class="sxs-lookup"><span data-stu-id="4b549-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="4b549-184">Ausgeblendeter Text (Zeichen werden maskiert)</span><span class="sxs-lookup"><span data-stu-id="4b549-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="4b549-185">Klassen, die Ihren Text anzeigen</span><span class="sxs-lookup"><span data-stu-id="4b549-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="4b549-186">Es können mehrere Klassen verwendet werden, um einfachen oder formatierten Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b549-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="4b549-187">Sie können <xref:System.Windows.Controls.TextBlock> verwenden, um kleine Textmengen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b549-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="4b549-188">Wenn Sie große Mengen an Text anzeigen möchten, verwenden Sie die Steuerelemente <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="4b549-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="4b549-189">Der <xref:System.Windows.Controls.TextBlock> verfügt über zwei Inhalts Eigenschaften: <xref:System.Windows.Controls.TextBlock.Text%2A> und <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b549-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="4b549-190">Wenn Sie Text anzeigen möchten, der eine konsistente Formatierung verwendet, ist die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft oft die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="4b549-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="4b549-191">Wenn Sie eine andere Formatierung im gesamten Text verwenden möchten, verwenden Sie die <xref:System.Windows.Controls.TextBlock.Inlines%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4b549-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="4b549-192">Die <xref:System.Windows.Controls.TextBlock.Inlines%2A>-Eigenschaft ist eine Auflistung von <xref:System.Windows.Documents.Inline>-Objekten, die angeben, wie Text formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b549-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="4b549-193">In der folgenden Tabelle wird die Content-Eigenschaft für die Klassen <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>und <xref:System.Windows.Controls.FlowDocumentScrollViewer> aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b549-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="4b549-194">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4b549-194">Control</span></span>|<span data-ttu-id="4b549-195">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="4b549-195">Content property</span></span>|<span data-ttu-id="4b549-196">Inhaltseigenschaftstyp</span><span class="sxs-lookup"><span data-stu-id="4b549-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="4b549-197">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="4b549-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="4b549-198">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="4b549-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="4b549-199">Dokumentieren</span><span class="sxs-lookup"><span data-stu-id="4b549-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="4b549-200">Der <xref:System.Windows.Documents.FlowDocument> implementiert die <xref:System.Windows.Documents.IDocumentPaginatorSource>-Schnittstelle. Daher können alle drei Klassen eine <xref:System.Windows.Documents.FlowDocument> als Inhalt annehmen.</span><span class="sxs-lookup"><span data-stu-id="4b549-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="4b549-201">Klassen, die den Text formatieren</span><span class="sxs-lookup"><span data-stu-id="4b549-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="4b549-202">mit <xref:System.Windows.Documents.TextElement> und den zugehörigen Klassen können Sie Text formatieren.</span><span class="sxs-lookup"><span data-stu-id="4b549-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="4b549-203"><xref:System.Windows.Documents.TextElement> Objekte enthalten und formatieren Text in <xref:System.Windows.Controls.TextBlock>-und <xref:System.Windows.Documents.FlowDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="4b549-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="4b549-204">Die beiden primären Typen von <xref:System.Windows.Documents.TextElement> Objekten sind <xref:System.Windows.Documents.Block> Elemente und <xref:System.Windows.Documents.Inline> Elemente.</span><span class="sxs-lookup"><span data-stu-id="4b549-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="4b549-205">Ein <xref:System.Windows.Documents.Block> Element stellt einen TextBlock dar, z. b. einen Absatz oder eine Liste.</span><span class="sxs-lookup"><span data-stu-id="4b549-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="4b549-206">Ein <xref:System.Windows.Documents.Inline>-Element stellt einen Teil des Texts in einem-Block dar.</span><span class="sxs-lookup"><span data-stu-id="4b549-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="4b549-207">Viele <xref:System.Windows.Documents.Inline> Klassen geben die Formatierung für den Text an, auf den Sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b549-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="4b549-208">Jede <xref:System.Windows.Documents.TextElement> verfügt über ein eigenes Inhalts Modell.</span><span class="sxs-lookup"><span data-stu-id="4b549-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="4b549-209">Weitere Informationen finden Sie unter [Übersicht über das TextElement-Inhaltsmodell](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b549-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b549-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b549-210">See also</span></span>

- [<span data-ttu-id="4b549-211">Erweitert</span><span class="sxs-lookup"><span data-stu-id="4b549-211">Advanced</span></span>](../advanced/index.md)
