---
title: "Übersicht über Menu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ab5092b1bc9db22390a18b2c1cb1ad5725a2037
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="menu-overview"></a><span data-ttu-id="b58bc-102">Übersicht über Menu</span><span class="sxs-lookup"><span data-stu-id="b58bc-102">Menu Overview</span></span>
<span data-ttu-id="b58bc-103">Die <xref:System.Windows.Controls.Menu> -Klasse ermöglicht es Ihnen, zum Organisieren von Elementen, die Befehlen und Ereignishandlern in einer hierarchischen Reihenfolge zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b58bc-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="b58bc-104">Jede <xref:System.Windows.Controls.Menu> Element enthält eine Auflistung von <xref:System.Windows.Controls.MenuItem> Elemente.</span><span class="sxs-lookup"><span data-stu-id="b58bc-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="b58bc-105">Menu-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b58bc-105">Menu Control</span></span>  
 <span data-ttu-id="b58bc-106">Die <xref:System.Windows.Controls.Menu> Steuerelement stellt eine Liste von Elementen, die Befehle oder Optionen für eine Anwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="b58bc-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="b58bc-107">Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> öffnet ein Untermenü oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b58bc-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="b58bc-108">Erstellen von Menüs</span><span class="sxs-lookup"><span data-stu-id="b58bc-108">Creating Menus</span></span>  
 <span data-ttu-id="b58bc-109">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Menu> zum Bearbeiten von Text in einem <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b58bc-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="b58bc-110">Die <xref:System.Windows.Controls.Menu> enthält <xref:System.Windows.Controls.MenuItem> Objekten, die <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, und <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaften und die <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, und <xref:System.Windows.Controls.MenuItem.Click> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b58bc-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="b58bc-111">MenuItems mit Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="b58bc-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="b58bc-112">Tastenkombinationen sind Zeichenkombinationen, die mit der Tastatur aufzurufenden eingegeben werden können <xref:System.Windows.Controls.Menu> Befehle.</span><span class="sxs-lookup"><span data-stu-id="b58bc-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="b58bc-113">Die Tastenkombination für **Kopieren** ist beispielsweise STRG+C.</span><span class="sxs-lookup"><span data-stu-id="b58bc-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="b58bc-114">Es gibt zwei Eigenschaften zur Verwendung mit Tastenkombinationen und Menüelemente –<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> oder <xref:System.Windows.Controls.MenuItem.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="b58bc-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="b58bc-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="b58bc-115">InputGestureText</span></span>  
 <span data-ttu-id="b58bc-116">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> Eigenschaft zuweisen Tastenkombinationstext <xref:System.Windows.Controls.MenuItem> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b58bc-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="b58bc-117">Dadurch wird nur die Tastenkombination im Menüelement platziert.</span><span class="sxs-lookup"><span data-stu-id="b58bc-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="b58bc-118">Es erfolgt keine Zuordnung zwischen den Befehl mit der <xref:System.Windows.Controls.MenuItem>.</span><span class="sxs-lookup"><span data-stu-id="b58bc-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="b58bc-119">Die Anwendung muss die Eingabe des Benutzers bearbeiten, um die Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b58bc-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="b58bc-120">Befehl</span><span class="sxs-lookup"><span data-stu-id="b58bc-120">Command</span></span>  
 <span data-ttu-id="b58bc-121">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.MenuItem.Command%2A> zu verknüpfende Eigenschaft der **öffnen** und **speichern** Befehle mit <xref:System.Windows.Controls.MenuItem> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="b58bc-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="b58bc-122">Nicht nur ist die Befehlseigenschaft ordnen Sie einen Befehl mit einem <xref:System.Windows.Controls.MenuItem>, sondern stellt auch die Eingabeaktion Text, der als Verknüpfung.</span><span class="sxs-lookup"><span data-stu-id="b58bc-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="b58bc-123">Die <xref:System.Windows.Controls.MenuItem> -Klasse verfügt auch über eine <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> Eigenschaft, die das Element angibt, in dem der Befehl auftritt.</span><span class="sxs-lookup"><span data-stu-id="b58bc-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="b58bc-124">Wenn <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> ist nicht festgelegt ist, wird der Befehl in das Element, das über den Tastaturfokus verfügt.</span><span class="sxs-lookup"><span data-stu-id="b58bc-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="b58bc-125">Weitere Informationen zu Befehlen finden Sie unter [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b58bc-125">For more information about commands, see [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="b58bc-126">Menu-Format</span><span class="sxs-lookup"><span data-stu-id="b58bc-126">Menu Styling</span></span>  
 <span data-ttu-id="b58bc-127">Mit Formatieren von Steuerelementen können Sie deutlich das Aussehen und Verhalten der ändern <xref:System.Windows.Controls.Menu> Steuerelemente ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b58bc-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="b58bc-128">Sie können auch anwenden, zusätzlich zum Festlegen von Eigenschaften visueller Elemente, eine <xref:System.Windows.Style> für einzelne Teile eines Steuerelements ändern das Verhalten von Teilen des Steuerelements über Eigenschaften, zusätzliche Teile hinzufügen oder Ändern des Layouts eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="b58bc-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="b58bc-129">Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Hinzufügen einer <xref:System.Windows.Style> zu einem <xref:System.Windows.Controls.Menu> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b58bc-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="b58bc-130">Im erste Codebeispiel definiert eine <xref:System.Windows.Style> aufgerufen `Simple` veranschaulicht, wie die aktuellen Systemeinstellungen in Ihr Format zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b58bc-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="b58bc-131">Der Code weist die Farbe von `MenuHighlightBrush` als Hintergrundfarbe des Menüs und die Farbe von `MenuTextBrush` als Vordergrundfarbe des Menüs zu.</span><span class="sxs-lookup"><span data-stu-id="b58bc-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="b58bc-132">Beachten Sie, dass Sie zum Zuweisen der Pinsel Ressourcenschlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="b58bc-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="b58bc-133">Das folgende Beispiel verwendet <xref:System.Windows.Trigger> Elemente, die Ihnen ermöglichen, ändern Sie die Darstellung von einer <xref:System.Windows.Controls.MenuItem> als Antwort auf Ereignisse, die auftreten, auf die <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="b58bc-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="b58bc-134">Wenn Sie den Mauszeiger über die <xref:System.Windows.Controls.Menu>, Vordergrundfarbe und Schriftartmerkmale der Menüelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b58bc-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b58bc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b58bc-135">See Also</span></span>  
 [<span data-ttu-id="b58bc-136">Beispiel für WPF-Steuerelementsammlungen</span><span class="sxs-lookup"><span data-stu-id="b58bc-136">WPF Controls Gallery Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160053)
