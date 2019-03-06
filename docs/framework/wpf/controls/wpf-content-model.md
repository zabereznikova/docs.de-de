---
title: WPF-Inhaltsmodell
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
ms.openlocfilehash: bd9dc7a441987b2089f0f21c81311a628ae3cdfa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373087"
---
# <a name="wpf-content-model"></a><span data-ttu-id="dfef7-102">WPF-Inhaltsmodell</span><span class="sxs-lookup"><span data-stu-id="dfef7-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="dfef7-103">ist eine Präsentationsplattform, die viele Steuerelemente und steuerelementähnliche Typen bereitstellt, deren Hauptaufgabe in der Anzeige unterschiedlicher Inhaltstypen besteht.</span><span class="sxs-lookup"><span data-stu-id="dfef7-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="dfef7-104">Um zu bestimmen, welches Steuerelement verwendet oder von welchem Steuerelement abgeleitet werden soll, sollten Sie mit den Objektarten vertraut sein, die ein bestimmtes Steuerelement am besten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="dfef7-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="dfef7-105">In diesem Thema wird das Inhaltsmodell für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente und steuerelementähnliche Typen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="dfef7-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="dfef7-106">Das Inhaltsmodell beschreibt, welche Inhalte in einem Steuerelement verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dfef7-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="dfef7-107">In diesem Thema werden ebenfalls die Inhaltseigenschaften für jedes Inhaltsmodell aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="dfef7-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="dfef7-108">Eine Inhaltseigenschaft ist eine Eigenschaft, die zum Speichern des Inhalts des Objekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfef7-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="dfef7-109">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="dfef7-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="dfef7-110">Einige Steuerelemente können ein Objekt eines beliebigen Typs, z. B. eine Zeichenfolge, enthalten eine <xref:System.DateTime> Objekt oder ein <xref:System.Windows.UIElement> , einen Container für zusätzliche Elemente.</span><span class="sxs-lookup"><span data-stu-id="dfef7-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="dfef7-111">Z. B. eine <xref:System.Windows.Controls.Button> kann ein Bild und Text enthalten oder ein <xref:System.Windows.Controls.CheckBox> darf den Wert des <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="dfef7-112">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Klassen, die beliebigen Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="dfef7-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="dfef7-113">Die folgende Tabelle enthält die Klassen, die von erben <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="dfef7-114">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="dfef7-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="dfef7-115">Content</span><span class="sxs-lookup"><span data-stu-id="dfef7-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="dfef7-116">Ein einzelnes beliebiges Objekt</span><span class="sxs-lookup"><span data-stu-id="dfef7-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="dfef7-117">Ein Header und ein einzelnes Element, die beide beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="dfef7-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="dfef7-118">Eine Auflistung beliebiger Objekte</span><span class="sxs-lookup"><span data-stu-id="dfef7-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="dfef7-119">Ein Header und eine Auflistung von Elementen, die alle beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="dfef7-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="dfef7-120">Steuerelemente, die von diesen Klassen erben, können dieselbe Art von Inhalt enthalten und den Inhalt auf die gleiche Weise behandeln.</span><span class="sxs-lookup"><span data-stu-id="dfef7-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="dfef7-121">Die folgende Abbildung zeigt ein Steuerelement aus den einzelnen Inhaltsmodellen, das ein Bild und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="dfef7-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="dfef7-122">![Button, GroupBox, Listbax, TreeViewItem](./media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="dfef7-122">![Button, GroupBox, Listbax, TreeViewItem](./media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="dfef7-123">Steuerelemente mit einem einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="dfef7-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="dfef7-124">Die <xref:System.Windows.Controls.ContentControl> Klasse enthält nur ein beliebiges Inhaltselement.</span><span class="sxs-lookup"><span data-stu-id="dfef7-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="dfef7-125">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="dfef7-126">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ContentControl> und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="dfef7-127">Die folgende Abbildung zeigt vier Schaltflächen, deren <xref:System.Windows.Controls.ContentControl.Content%2A> festgelegt ist, in eine Zeichenfolge, ein <xref:System.DateTime> Objekt eine <xref:System.Windows.Shapes.Rectangle>, und ein <xref:System.Windows.Controls.Panel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und ein <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="dfef7-128">![Vier Schaltflächen](./media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="dfef7-128">![Four buttons](./media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="dfef7-129">Vier Schaltflächen mit verschiedenen Arten von Inhalten</span><span class="sxs-lookup"><span data-stu-id="dfef7-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="dfef7-130">Ein Beispiel zum Festlegen der <xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft finden Sie unter <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="dfef7-131">Steuerelemente mit einem Header und einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="dfef7-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="dfef7-132">Die <xref:System.Windows.Controls.HeaderedContentControl> Klasse erbt von <xref:System.Windows.Controls.ContentControl> und zeigt den Inhalt mit einem Header an.</span><span class="sxs-lookup"><span data-stu-id="dfef7-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="dfef7-133">Es erbt die Inhaltseigenschaft, <xref:System.Windows.Controls.ContentControl.Content%2A>, von <xref:System.Windows.Controls.ContentControl> und definiert die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Eigenschaft vom Typ <xref:System.Object>daher beide können ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="dfef7-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="dfef7-134">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedContentControl> und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="dfef7-135">Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.TabItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="dfef7-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="dfef7-136">Die erste <xref:System.Windows.Controls.TabItem> hat <xref:System.Windows.UIElement> Objekte als die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="dfef7-137">Die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> nastaven NA hodnotu eine <xref:System.Windows.Controls.StackPanel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="dfef7-138">Die <xref:System.Windows.Controls.ContentControl.Content%2A> nastaven NA hodnotu eine <xref:System.Windows.Controls.StackPanel> , enthält eine <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="dfef7-139">Die zweite <xref:System.Windows.Controls.TabItem> hat eine Zeichenfolge die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und <xref:System.Windows.Controls.TextBlock> in die <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="dfef7-140">![TabControl](./media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="dfef7-140">![TabControl](./media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="dfef7-141">TabControl, das unterschiedliche Typen in der Header-Eigenschaft verwendet</span><span class="sxs-lookup"><span data-stu-id="dfef7-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="dfef7-142">Ein Beispiel zum Erstellen von <xref:System.Windows.Controls.TabItem> Objekten finden Sie <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="dfef7-143">Steuerelemente mit einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="dfef7-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="dfef7-144">Die <xref:System.Windows.Controls.ItemsControl> Klasse erbt von <xref:System.Windows.Controls.Control> und kann mehrere Elemente, z. B. Zeichenfolgen, Objekte oder andere Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="dfef7-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="dfef7-145">Die Inhaltseigenschaften sind <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="dfef7-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dient normalerweise zum Auffüllen der <xref:System.Windows.Controls.ItemsControl> mit einer datenauflistung.</span><span class="sxs-lookup"><span data-stu-id="dfef7-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="dfef7-147">Wenn Sie nicht, verwenden Sie eine Auflistung zum Auffüllen möchten der <xref:System.Windows.Controls.ItemsControl>, Sie können Elemente hinzufügen, mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dfef7-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="dfef7-148">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.ItemsControl> und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="dfef7-149">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ListBox> , enthält die folgenden Elementtypen:</span><span class="sxs-lookup"><span data-stu-id="dfef7-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="dfef7-150">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dfef7-150">A string.</span></span>  
  
-   <span data-ttu-id="dfef7-151">Ein <xref:System.DateTime>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="dfef7-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="dfef7-152">Ein <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="dfef7-153">Ein <xref:System.Windows.Controls.Panel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="dfef7-154">![ListBox mit vier Inhaltstypen](./media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="dfef7-154">![ListBox with four types of content](./media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="dfef7-155">Ein Listenfeld, das mehrere Inhaltstypen enthält</span><span class="sxs-lookup"><span data-stu-id="dfef7-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="dfef7-156">Steuerelemente mit einem Header und einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="dfef7-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="dfef7-157">Die <xref:System.Windows.Controls.HeaderedItemsControl> Klasse erbt von <xref:System.Windows.Controls.ItemsControl> und kann mehrere Elemente, z. B. Zeichenfolgen, Objekte oder andere Elemente und einen Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="dfef7-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="dfef7-158">Es erbt die <xref:System.Windows.Controls.ItemsControl> -Inhaltseigenschaften, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, und <xref:System.Windows.Controls.ItemsControl.Items%2A>, und definiert die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> -Eigenschaft, die ein beliebiges Objekt sein kann.</span><span class="sxs-lookup"><span data-stu-id="dfef7-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="dfef7-159">Die folgenden Steuerelemente erben von <xref:System.Windows.Controls.HeaderedItemsControl> und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="dfef7-160">Klassen mit einer Auflistung von UIElement-Objekten</span><span class="sxs-lookup"><span data-stu-id="dfef7-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="dfef7-161">Die <xref:System.Windows.Controls.Panel> -Klasse positioniert und ordnet untergeordnete <xref:System.Windows.UIElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="dfef7-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="dfef7-162">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="dfef7-163">Die folgenden Klassen erben von der <xref:System.Windows.Controls.Panel> Klasse, und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="dfef7-164">Weitere Informationen finden Sie unter [Übersicht über Panel-Elemente](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfef7-164">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="dfef7-165">Klassen, die sich auf die Anzeige eines UIElement-Objekts auswirken</span><span class="sxs-lookup"><span data-stu-id="dfef7-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="dfef7-166">Die <xref:System.Windows.Controls.Decorator> -Klasse wendet visuelle Effekte auf oder um ein einzelnes untergeordnetes Element <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="dfef7-167">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="dfef7-168">Die folgenden Klassen erben von <xref:System.Windows.Controls.Decorator> und verwenden dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dfef7-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="dfef7-169">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.TextBox> aufweist (versehen mit) eine <xref:System.Windows.Controls.Border> darum.</span><span class="sxs-lookup"><span data-stu-id="dfef7-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="dfef7-170">![TextBox mit schwarzem Rahmen](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="dfef7-170">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="dfef7-171">Textfeld mit einem Rahmen</span><span class="sxs-lookup"><span data-stu-id="dfef7-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="dfef7-172">Klassen, die visuelles Feedback zu einem UIElement bereitstellen</span><span class="sxs-lookup"><span data-stu-id="dfef7-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="dfef7-173">Die <xref:System.Windows.Documents.Adorner> -Klasse stellt visuelle Hinweise zu einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dfef7-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="dfef7-174">Verwenden Sie z. B. eine <xref:System.Windows.Documents.Adorner> um Elementen funktionale Handles hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dfef7-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="dfef7-175">Die <xref:System.Windows.Documents.Adorner> Klasse stellt ein Framework bereit, sodass Sie eigene Adorner erstellen können.</span><span class="sxs-lookup"><span data-stu-id="dfef7-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="dfef7-176">stellt keine implementierten Adorner bereit.</span><span class="sxs-lookup"><span data-stu-id="dfef7-176">does not provide any implemented adorners.</span></span> <span data-ttu-id="dfef7-177">Weitere Informationen finden Sie unter [Übersicht über Adorner](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfef7-177">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="dfef7-178">Klassen, mit denen Benutzer Text eingeben können</span><span class="sxs-lookup"><span data-stu-id="dfef7-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="dfef7-179">WPF bietet drei primäre Steuerelemente, mit denen Benutzer Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="dfef7-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="dfef7-180">Jedes Steuerelement zeigt den Text unterschiedlich an.</span><span class="sxs-lookup"><span data-stu-id="dfef7-180">Each control displays the text differently.</span></span> <span data-ttu-id="dfef7-181">Die folgende Tabelle enthält diese drei textbezogene Steuerelemente, ihre Funktionen bei der Textanzeige und ihre Eigenschaften, die den Text des Steuerelements enthalten.</span><span class="sxs-lookup"><span data-stu-id="dfef7-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="dfef7-182">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dfef7-182">Control</span></span>|<span data-ttu-id="dfef7-183">Text wird angezeigt als</span><span class="sxs-lookup"><span data-stu-id="dfef7-183">Text is displayed as</span></span>|<span data-ttu-id="dfef7-184">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="dfef7-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="dfef7-185">Nur-Text</span><span class="sxs-lookup"><span data-stu-id="dfef7-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="dfef7-186">Formatierter Text</span><span class="sxs-lookup"><span data-stu-id="dfef7-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="dfef7-187">Ausgeblendeter Text (Zeichen werden maskiert)</span><span class="sxs-lookup"><span data-stu-id="dfef7-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="dfef7-188">Klassen, die Ihren Text anzeigen</span><span class="sxs-lookup"><span data-stu-id="dfef7-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="dfef7-189">Es können mehrere Klassen verwendet werden, um einfachen oder formatierten Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dfef7-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="dfef7-190">Sie können <xref:System.Windows.Controls.TextBlock> um kleine Mengen an Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dfef7-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="dfef7-191">Wenn Sie große Textmengen anzeigen möchten, verwenden Sie die <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, oder <xref:System.Windows.Controls.FlowDocumentScrollViewer> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="dfef7-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="dfef7-192">Die <xref:System.Windows.Controls.TextBlock> verfügt über zwei Inhaltseigenschaften: <xref:System.Windows.Controls.TextBlock.Text%2A> und <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfef7-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="dfef7-193">Wenn Sie möchten, um Text anzuzeigen, die konsistente Formatierung, verwendet der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft ist häufig die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="dfef7-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="dfef7-194">Wenn Sie im gesamten Text eine andere Formatierung verwenden möchten, verwenden Sie die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dfef7-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="dfef7-195">Die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft ist eine Sammlung von <xref:System.Windows.Documents.Inline> -Objekte, die Formatierung von Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dfef7-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="dfef7-196">Die folgende Tabelle listet die Inhaltseigenschaft für <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer> Klassen.</span><span class="sxs-lookup"><span data-stu-id="dfef7-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="dfef7-197">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dfef7-197">Control</span></span>|<span data-ttu-id="dfef7-198">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="dfef7-198">Content property</span></span>|<span data-ttu-id="dfef7-199">Inhaltseigenschaftstyp</span><span class="sxs-lookup"><span data-stu-id="dfef7-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="dfef7-200">Dokument</span><span class="sxs-lookup"><span data-stu-id="dfef7-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="dfef7-201">Dokument</span><span class="sxs-lookup"><span data-stu-id="dfef7-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="dfef7-202">Dokument</span><span class="sxs-lookup"><span data-stu-id="dfef7-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="dfef7-203">Die <xref:System.Windows.Documents.FlowDocument> implementiert die <xref:System.Windows.Documents.IDocumentPaginatorSource> Schnittstelle; deshalb können alle drei Klassen durchführen einer <xref:System.Windows.Documents.FlowDocument> als Inhalt.</span><span class="sxs-lookup"><span data-stu-id="dfef7-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="dfef7-204">Klassen, die den Text formatieren</span><span class="sxs-lookup"><span data-stu-id="dfef7-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="dfef7-205"><xref:System.Windows.Documents.TextElement> und den zugehörigen Klassen können Sie Text formatieren.</span><span class="sxs-lookup"><span data-stu-id="dfef7-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="dfef7-206"><xref:System.Windows.Documents.TextElement> -Objekte enthalten, und Formatieren von Text in <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="dfef7-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="dfef7-207">Die zwei primären Typen von <xref:System.Windows.Documents.TextElement> Objekte sind <xref:System.Windows.Documents.Block> Elemente und <xref:System.Windows.Documents.Inline> Elemente.</span><span class="sxs-lookup"><span data-stu-id="dfef7-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="dfef7-208">Ein <xref:System.Windows.Documents.Block> -Element stellt einen Textblock, z. B. einen Absatz oder eine Liste dar.</span><span class="sxs-lookup"><span data-stu-id="dfef7-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="dfef7-209">Ein <xref:System.Windows.Documents.Inline> -Element stellt einen Teil des Texts in einem Block dar.</span><span class="sxs-lookup"><span data-stu-id="dfef7-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="dfef7-210">Viele <xref:System.Windows.Documents.Inline> -Klassen geben die Formatierung für den Text, der auf dem sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="dfef7-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="dfef7-211">Jede <xref:System.Windows.Documents.TextElement> verfügt über ein eigenes Inhaltsmodell.</span><span class="sxs-lookup"><span data-stu-id="dfef7-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="dfef7-212">Weitere Informationen finden Sie unter [Übersicht über das TextElement-Inhaltsmodell](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfef7-212">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfef7-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfef7-213">See also</span></span>
- [<span data-ttu-id="dfef7-214">Erweitert</span><span class="sxs-lookup"><span data-stu-id="dfef7-214">Advanced</span></span>](../advanced/index.md)
