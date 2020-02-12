---
title: Übersicht über ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: b973d47711632f4c0fe56f042545598272c79d2d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124363"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="dfd7e-102">Übersicht über ContextMenu</span><span class="sxs-lookup"><span data-stu-id="dfd7e-102">ContextMenu Overview</span></span>
<span data-ttu-id="dfd7e-103">Die <xref:System.Windows.Controls.ContextMenu>-Klasse stellt das Element dar, das Funktionen mithilfe eines kontextspezifischen <xref:System.Windows.Controls.Menu>verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="dfd7e-104">Normalerweise macht ein Benutzer den <xref:System.Windows.Controls.ContextMenu> im [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] verfügbar, indem er mit der rechten Maustaste auf die Maustaste klickt.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="dfd7e-105">In diesem Thema wird das <xref:System.Windows.Controls.ContextMenu>-Element vorgestellt, und es werden Beispiele für die Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="dfd7e-106">ContextMenu-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dfd7e-106">ContextMenu Control</span></span>  
 <span data-ttu-id="dfd7e-107">Ein <xref:System.Windows.Controls.ContextMenu> wird an ein bestimmtes Steuerelement angefügt.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="dfd7e-108">Mit dem <xref:System.Windows.Controls.ContextMenu>-Element können Sie Benutzern eine Liste von Elementen präsentieren, mit denen Befehle oder Optionen angegeben werden, die einem bestimmten Steuerelement zugeordnet sind, z. b. ein <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="dfd7e-109">Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="dfd7e-110">Wenn Sie auf eine <xref:System.Windows.Controls.MenuItem> klicken, wird in der Regel ein Untermenü geöffnet, oder eine Anwendung führt einen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="dfd7e-111">Erstellen von ContextMenus</span><span class="sxs-lookup"><span data-stu-id="dfd7e-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="dfd7e-112">In den folgenden Beispielen wird gezeigt, wie eine <xref:System.Windows.Controls.ContextMenu> mit Untermenüs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="dfd7e-113">Die <xref:System.Windows.Controls.ContextMenu>-Steuerelemente werden an Schaltflächen Steuerelemente angefügt.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="dfd7e-114">Anwenden von Stilen auf ein ContextMenu</span><span class="sxs-lookup"><span data-stu-id="dfd7e-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="dfd7e-115">Mithilfe eines Steuer Elements <xref:System.Windows.Style>können Sie die Darstellung und das Verhalten einer <xref:System.Windows.Controls.ContextMenu> drastisch ändern, ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="dfd7e-116">Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="dfd7e-117">Beispielsweise können Sie das Verhalten der Teile des Steuer Elements ändern, indem Sie Eigenschaften verwenden, oder Sie können einem <xref:System.Windows.Controls.ContextMenu>Teile hinzufügen oder das Layout einer ändern.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="dfd7e-118">In den folgenden Beispielen werden verschiedene Möglichkeiten zum Hinzufügen von Stilen zu <xref:System.Windows.Controls.ContextMenu>-Steuerelementen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="dfd7e-119">Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="dfd7e-120">Im Beispiel wird <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> als <xref:System.Windows.Controls.Control.Background%2A> Farbe zugewiesen und <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> als <xref:System.Windows.Controls.Control.Foreground%2A> Farbe des <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="dfd7e-121">Im folgenden Beispiel wird das <xref:System.Windows.Trigger>-Element verwendet, um die Darstellung einer <xref:System.Windows.Controls.Menu> als Reaktion auf Ereignisse zu ändern, die auf dem <xref:System.Windows.Controls.ContextMenu>ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="dfd7e-122">Wenn ein Benutzer die Maus über das Menü bewegt, wird die Darstellung der <xref:System.Windows.Controls.ContextMenu> Elemente geändert.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfd7e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfd7e-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="dfd7e-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="dfd7e-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="dfd7e-125">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="dfd7e-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="dfd7e-126">Beispiel für WPF-Steuerelementsammlungen</span><span class="sxs-lookup"><span data-stu-id="dfd7e-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
