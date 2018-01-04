---
title: WPF-Inhaltsmodell
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d708674682ffd7b0d13c9cbe828e28bbc26e260
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-content-model"></a><span data-ttu-id="c7daa-102">WPF-Inhaltsmodell</span><span class="sxs-lookup"><span data-stu-id="c7daa-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="c7daa-103"> ist eine Präsentationsplattform, die viele Steuerelemente und steuerelementähnliche Typen bereitstellt, deren Hauptaufgabe in der Anzeige unterschiedlicher Inhaltstypen besteht.</span><span class="sxs-lookup"><span data-stu-id="c7daa-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="c7daa-104">Um zu bestimmen, welches Steuerelement verwendet oder von welchem Steuerelement abgeleitet werden soll, sollten Sie mit den Objektarten vertraut sein, die ein bestimmtes Steuerelement am besten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c7daa-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="c7daa-105">In diesem Thema wird das Inhaltsmodell für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente und steuerelementähnliche Typen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="c7daa-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="c7daa-106">Das Inhaltsmodell beschreibt, welche Inhalte in einem Steuerelement verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c7daa-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="c7daa-107">In diesem Thema werden ebenfalls die Inhaltseigenschaften für jedes Inhaltsmodell aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="c7daa-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="c7daa-108">Eine Inhaltseigenschaft ist eine Eigenschaft, die zum Speichern des Inhalts des Objekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7daa-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="c7daa-109">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="c7daa-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="c7daa-110">Einige Steuerelemente können ein Objekt eines beliebigen Typs, z. B. eine Zeichenfolge enthalten eine <xref:System.DateTime> -Objekt, oder ein <xref:System.Windows.UIElement> also ein Container für zusätzliche Elemente.</span><span class="sxs-lookup"><span data-stu-id="c7daa-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="c7daa-111">Z. B. eine <xref:System.Windows.Controls.Button> darf ein Bild und Text; oder ein <xref:System.Windows.Controls.CheckBox> darf den Wert des <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="c7daa-112">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt es vier Klassen, die beliebigen Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7daa-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="c7daa-113">Die folgende Tabelle enthält die Klassen, die von erben <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="c7daa-114">Klassen mit beliebigem Inhalt</span><span class="sxs-lookup"><span data-stu-id="c7daa-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="c7daa-115">Inhalt</span><span class="sxs-lookup"><span data-stu-id="c7daa-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="c7daa-116">Ein einzelnes beliebiges Objekt</span><span class="sxs-lookup"><span data-stu-id="c7daa-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="c7daa-117">Ein Header und ein einzelnes Element, die beide beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="c7daa-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="c7daa-118">Eine Auflistung beliebiger Objekte</span><span class="sxs-lookup"><span data-stu-id="c7daa-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="c7daa-119">Ein Header und eine Auflistung von Elementen, die alle beliebige Objekte sind</span><span class="sxs-lookup"><span data-stu-id="c7daa-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="c7daa-120">Steuerelemente, die von diesen Klassen erben, können dieselbe Art von Inhalt enthalten und den Inhalt auf die gleiche Weise behandeln.</span><span class="sxs-lookup"><span data-stu-id="c7daa-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="c7daa-121">Die folgende Abbildung zeigt ein Steuerelement aus den einzelnen Inhaltsmodellen, das ein Bild und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="c7daa-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="c7daa-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="c7daa-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="c7daa-123">Steuerelemente mit einem einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="c7daa-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="c7daa-124">Die <xref:System.Windows.Controls.ContentControl> Klasse enthält ein einzelnes Stück beliebiger Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c7daa-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="c7daa-125">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="c7daa-126">Die folgenden Steuerelemente, die von erben <xref:System.Windows.Controls.ContentControl> und Inhaltsmodell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7daa-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="c7daa-127">Die folgende Abbildung zeigt vier Schaltflächen, deren <xref:System.Windows.Controls.ContentControl.Content%2A> festgelegt ist, in eine Zeichenfolge ein <xref:System.DateTime> -Objekt, eine <xref:System.Windows.Shapes.Rectangle>, und ein <xref:System.Windows.Controls.Panel> , enthält eine <xref:System.Windows.Shapes.Ellipse> und ein <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="c7daa-128">![Vier Schaltflächen](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="c7daa-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="c7daa-129">Vier Schaltflächen mit verschiedenen Arten von Inhalten</span><span class="sxs-lookup"><span data-stu-id="c7daa-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="c7daa-130">Ein Beispiel zum Festlegen der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft finden Sie unter <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="c7daa-131">Steuerelemente mit einem Header und einzelnen beliebigen Objekt</span><span class="sxs-lookup"><span data-stu-id="c7daa-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="c7daa-132">Die <xref:System.Windows.Controls.HeaderedContentControl> Klasse erbt von <xref:System.Windows.Controls.ContentControl> und zeigt den Inhalt mit einem Header an.</span><span class="sxs-lookup"><span data-stu-id="c7daa-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="c7daa-133">Erbt die Content-Eigenschaft <xref:System.Windows.Controls.ContentControl.Content%2A>, aus <xref:System.Windows.Controls.ContentControl> und definiert die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> -Eigenschaft, die vom Typ <xref:System.Object>; aus diesem Grund dürfen ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="c7daa-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="c7daa-134">Die folgenden Steuerelemente, die von erben <xref:System.Windows.Controls.HeaderedContentControl> und Inhaltsmodell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7daa-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="c7daa-135">Die folgende Abbildung zeigt zwei <xref:System.Windows.Controls.TabItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="c7daa-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="c7daa-136">Die erste <xref:System.Windows.Controls.TabItem> hat <xref:System.Windows.UIElement> Objekte wie die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und die <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="c7daa-137">Die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> festgelegt ist, um eine <xref:System.Windows.Controls.StackPanel> , enthält ein <xref:System.Windows.Shapes.Ellipse> und ein <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="c7daa-138">Der <xref:System.Windows.Controls.ContentControl.Content%2A> festgelegt ist, um eine <xref:System.Windows.Controls.StackPanel> , enthält eine <xref:System.Windows.Controls.TextBlock> und eine <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="c7daa-139">Die zweite <xref:System.Windows.Controls.TabItem> hat eine Zeichenfolge der <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und ein <xref:System.Windows.Controls.TextBlock> in der <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="c7daa-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="c7daa-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="c7daa-141">TabControl, das unterschiedliche Typen in der Header-Eigenschaft verwendet</span><span class="sxs-lookup"><span data-stu-id="c7daa-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="c7daa-142">Ein Beispiel zum Erstellen von <xref:System.Windows.Controls.TabItem> Objekte finden Sie unter <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="c7daa-143">Steuerelemente mit einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="c7daa-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="c7daa-144">Die <xref:System.Windows.Controls.ItemsControl> Klasse erbt von <xref:System.Windows.Controls.Control> und können mehrere Elemente enthalten, z. B. Zeichenfolgen, Objekte oder andere Elemente.</span><span class="sxs-lookup"><span data-stu-id="c7daa-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="c7daa-145">Die Inhaltseigenschaften sind <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="c7daa-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>dient normalerweise zum Auffüllen der <xref:System.Windows.Controls.ItemsControl> mit einer Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="c7daa-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="c7daa-147">Wenn Sie nicht, verwenden Sie eine Auflistung zum Auffüllen möchten der <xref:System.Windows.Controls.ItemsControl>, können Sie Elemente hinzufügen, mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7daa-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="c7daa-148">Die folgenden Steuerelemente, die von erben <xref:System.Windows.Controls.ItemsControl> und Inhaltsmodell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7daa-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="c7daa-149">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.ListBox> , die diese Typen von Elementen enthält:</span><span class="sxs-lookup"><span data-stu-id="c7daa-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="c7daa-150">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c7daa-150">A string.</span></span>  
  
-   <span data-ttu-id="c7daa-151">Ein <xref:System.DateTime>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c7daa-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="c7daa-152">Ein <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="c7daa-153">Ein <xref:System.Windows.Controls.Panel> , enthält eine <xref:System.Windows.Shapes.Ellipse> und ein <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="c7daa-154">![ListBox mit vier Inhaltstypen](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="c7daa-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="c7daa-155">Ein Listenfeld, das mehrere Inhaltstypen enthält</span><span class="sxs-lookup"><span data-stu-id="c7daa-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="c7daa-156">Steuerelemente mit einem Header und einer Auflistung von beliebigen Objekten</span><span class="sxs-lookup"><span data-stu-id="c7daa-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="c7daa-157">Die <xref:System.Windows.Controls.HeaderedItemsControl> Klasse erbt von <xref:System.Windows.Controls.ItemsControl> und können mehrere Elemente enthalten, z. B. Zeichenfolgen, Objekte oder andere Elemente und einen Header.</span><span class="sxs-lookup"><span data-stu-id="c7daa-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="c7daa-158">Sie erbt die <xref:System.Windows.Controls.ItemsControl> Inhaltseigenschaften, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, und <xref:System.Windows.Controls.ItemsControl.Items%2A>, und definiert die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> -Eigenschaft, die ein beliebiges Objekt sein kann.</span><span class="sxs-lookup"><span data-stu-id="c7daa-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="c7daa-159">Die folgenden Steuerelemente, die von erben <xref:System.Windows.Controls.HeaderedItemsControl> und Inhaltsmodell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7daa-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="c7daa-160">Klassen mit einer Auflistung von UIElement-Objekten</span><span class="sxs-lookup"><span data-stu-id="c7daa-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="c7daa-161">Die <xref:System.Windows.Controls.Panel> Klasse positioniert und ordnet untergeordnete <xref:System.Windows.UIElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="c7daa-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="c7daa-162">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="c7daa-163">Die folgenden Klassen erben von der <xref:System.Windows.Controls.Panel> Klasse erstellt und dessen Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="c7daa-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="c7daa-164">Weitere Informationen finden Sie unter [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7daa-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="c7daa-165">Klassen, die sich auf die Anzeige eines UIElement-Objekts auswirken</span><span class="sxs-lookup"><span data-stu-id="c7daa-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="c7daa-166">Die <xref:System.Windows.Controls.Decorator> Klasse gilt visuelle Effekte auf oder um ein einzelnes untergeordnetes <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="c7daa-167">Die Inhaltseigenschaft ist <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="c7daa-168">Die folgenden Klassen erben von <xref:System.Windows.Controls.Decorator> und Inhaltsmodell verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7daa-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="c7daa-169">Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.TextBox> mit dem (ergänzt wird mit) eine <xref:System.Windows.Controls.Border> herum.</span><span class="sxs-lookup"><span data-stu-id="c7daa-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="c7daa-170">![TextBox mit schwarzem Rahmen](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="c7daa-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="c7daa-171">Textfeld mit einem Rahmen</span><span class="sxs-lookup"><span data-stu-id="c7daa-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="c7daa-172">Klassen, die visuelles Feedback zu einem UIElement bereitstellen</span><span class="sxs-lookup"><span data-stu-id="c7daa-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="c7daa-173">Die <xref:System.Windows.Documents.Adorner> -Klasse bietet visuelle Hinweise für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c7daa-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="c7daa-174">Verwenden Sie z. B. eine <xref:System.Windows.Documents.Adorner> funktionale Handles Elemente hinzufügen oder Zustandsinformationen zu einem Steuerelement bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c7daa-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="c7daa-175">Die <xref:System.Windows.Documents.Adorner> Klasse stellt ein Framework bereit, sodass Sie eigene Adorner erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c7daa-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="c7daa-176"> stellt keine implementierten Adorner bereit.</span><span class="sxs-lookup"><span data-stu-id="c7daa-176"> does not provide any implemented adorners.</span></span> <span data-ttu-id="c7daa-177">Weitere Informationen finden Sie unter [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7daa-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="c7daa-178">Klassen, mit denen Benutzer Text eingeben können</span><span class="sxs-lookup"><span data-stu-id="c7daa-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="c7daa-179">WPF bietet drei primäre Steuerelemente, mit denen Benutzer Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="c7daa-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="c7daa-180">Jedes Steuerelement zeigt den Text unterschiedlich an.</span><span class="sxs-lookup"><span data-stu-id="c7daa-180">Each control displays the text differently.</span></span> <span data-ttu-id="c7daa-181">Die folgende Tabelle enthält diese drei textbezogene Steuerelemente, ihre Funktionen bei der Textanzeige und ihre Eigenschaften, die den Text des Steuerelements enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7daa-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="c7daa-182">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c7daa-182">Control</span></span>|<span data-ttu-id="c7daa-183">Text wird angezeigt als</span><span class="sxs-lookup"><span data-stu-id="c7daa-183">Text is displayed as</span></span>|<span data-ttu-id="c7daa-184">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="c7daa-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="c7daa-185">Nur-Text</span><span class="sxs-lookup"><span data-stu-id="c7daa-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="c7daa-186">Formatierter Text</span><span class="sxs-lookup"><span data-stu-id="c7daa-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="c7daa-187">Ausgeblendeter Text (Zeichen werden maskiert)</span><span class="sxs-lookup"><span data-stu-id="c7daa-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="c7daa-188">Klassen, die Ihren Text anzeigen</span><span class="sxs-lookup"><span data-stu-id="c7daa-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="c7daa-189">Es können mehrere Klassen verwendet werden, um einfachen oder formatierten Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7daa-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="c7daa-190">Sie können <xref:System.Windows.Controls.TextBlock> um kleine Mengen von Text anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7daa-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="c7daa-191">Wenn Sie große Mengen von Text anzeigen möchten, verwenden Sie die <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, oder <xref:System.Windows.Controls.FlowDocumentScrollViewer> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="c7daa-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="c7daa-192">Die <xref:System.Windows.Controls.TextBlock> verfügt über zwei Inhaltseigenschaften: <xref:System.Windows.Controls.TextBlock.Text%2A> und <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7daa-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="c7daa-193">Wenn der Text angezeigt, die konsistente Formatierung verwendet werden soll die <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft ist häufig die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="c7daa-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="c7daa-194">Wenn Sie andere Formatierung im gesamten Text verwenden möchten, verwenden Sie die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7daa-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="c7daa-195">Die <xref:System.Windows.Controls.TextBlock.Inlines%2A> Eigenschaft ist eine Auflistung von <xref:System.Windows.Documents.Inline> -Objekten, die angeben, wie Text zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="c7daa-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="c7daa-196">Die folgende Tabelle enthält die Content-Eigenschaft für <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer> Klassen.</span><span class="sxs-lookup"><span data-stu-id="c7daa-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="c7daa-197">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c7daa-197">Control</span></span>|<span data-ttu-id="c7daa-198">Inhaltseigenschaft</span><span class="sxs-lookup"><span data-stu-id="c7daa-198">Content property</span></span>|<span data-ttu-id="c7daa-199">Inhaltseigenschaftstyp</span><span class="sxs-lookup"><span data-stu-id="c7daa-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="c7daa-200">Dokument</span><span class="sxs-lookup"><span data-stu-id="c7daa-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="c7daa-201">Dokument</span><span class="sxs-lookup"><span data-stu-id="c7daa-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="c7daa-202">Dokument</span><span class="sxs-lookup"><span data-stu-id="c7daa-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="c7daa-203">Die <xref:System.Windows.Documents.FlowDocument> implementiert die <xref:System.Windows.Documents.IDocumentPaginatorSource> Schnittstelle; alle drei Klassen können Schalten Sie daher eine <xref:System.Windows.Documents.FlowDocument> als Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c7daa-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="c7daa-204">Klassen, die den Text formatieren</span><span class="sxs-lookup"><span data-stu-id="c7daa-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="c7daa-205"><xref:System.Windows.Documents.TextElement>und seinen verwandten Klassen ermöglichen es Ihnen, Text zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="c7daa-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="c7daa-206"><xref:System.Windows.Documents.TextElement>-Objekte enthalten und Formatieren von Text in <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="c7daa-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="c7daa-207">Die zwei Haupttypen von <xref:System.Windows.Documents.TextElement> Objekte sind <xref:System.Windows.Documents.Block> Elemente und <xref:System.Windows.Documents.Inline> Elemente.</span><span class="sxs-lookup"><span data-stu-id="c7daa-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="c7daa-208">Ein <xref:System.Windows.Documents.Block> -Element stellt einen Textblock, z. B. einen Absatz oder eine Liste dar.</span><span class="sxs-lookup"><span data-stu-id="c7daa-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="c7daa-209">Ein <xref:System.Windows.Documents.Inline> -Element stellt einen Teil des Texts in einem Block dar.</span><span class="sxs-lookup"><span data-stu-id="c7daa-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="c7daa-210">Viele <xref:System.Windows.Documents.Inline> Klassen geben Formatierung für den Text, der auf die sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7daa-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="c7daa-211">Jede <xref:System.Windows.Documents.TextElement> verfügt über einen eigenen Inhaltsmodell.</span><span class="sxs-lookup"><span data-stu-id="c7daa-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="c7daa-212">Weitere Informationen finden Sie unter [Übersicht über das TextElement-Inhaltsmodell](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7daa-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7daa-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7daa-213">See Also</span></span>  
 [<span data-ttu-id="c7daa-214">Erweitert</span><span class="sxs-lookup"><span data-stu-id="c7daa-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
