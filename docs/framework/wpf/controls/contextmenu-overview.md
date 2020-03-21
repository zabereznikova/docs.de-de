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
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185914"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="73631-102">Übersicht über ContextMenu</span><span class="sxs-lookup"><span data-stu-id="73631-102">ContextMenu Overview</span></span>
<span data-ttu-id="73631-103">Die <xref:System.Windows.Controls.ContextMenu> Klasse stellt das Element dar, das <xref:System.Windows.Controls.Menu>Funktionen mithilfe einer kontextspezifischen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="73631-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="73631-104">In der Regel macht <xref:System.Windows.Controls.ContextMenu> ein [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Benutzer die in der durch Rechtsklick auf die Maustaste verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73631-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="73631-105">In diesem <xref:System.Windows.Controls.ContextMenu> Thema wird das Element vorgestellt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Beispiele für die Verwendung in und Code vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="73631-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="73631-106">ContextMenu-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="73631-106">ContextMenu Control</span></span>  
 <span data-ttu-id="73631-107">A <xref:System.Windows.Controls.ContextMenu> ist an ein bestimmtes Steuerelement angefügt.</span><span class="sxs-lookup"><span data-stu-id="73631-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="73631-108">Mit <xref:System.Windows.Controls.ContextMenu> dem Element können Sie Benutzern eine Liste von Elementen präsentieren, die Befehle oder <xref:System.Windows.Controls.Button>Optionen angeben, die einem bestimmten Steuerelement zugeordnet sind, z. B. eine .</span><span class="sxs-lookup"><span data-stu-id="73631-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="73631-109">Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="73631-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="73631-110">In der Regel <xref:System.Windows.Controls.MenuItem> wird durch Klicken auf ein Untermenü ein Untermenü geöffnet oder eine Anwendung veranlasst, einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="73631-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="73631-111">Erstellen von ContextMenus</span><span class="sxs-lookup"><span data-stu-id="73631-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="73631-112">Die folgenden Beispiele zeigen, <xref:System.Windows.Controls.ContextMenu> wie Sie ein mit Untermenüs erstellen.</span><span class="sxs-lookup"><span data-stu-id="73631-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="73631-113">Die <xref:System.Windows.Controls.ContextMenu> Steuerelemente werden an Schaltflächensteuerelemente angehängt.</span><span class="sxs-lookup"><span data-stu-id="73631-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="73631-114">Anwenden von Stilen auf ein ContextMenu</span><span class="sxs-lookup"><span data-stu-id="73631-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="73631-115">Durch die <xref:System.Windows.Style>Verwendung eines Steuerelements können Sie <xref:System.Windows.Controls.ContextMenu> das Erscheinungsbild und Verhalten eines Steuerelements drastisch ändern, ohne ein benutzerdefiniertes Steuerelement zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="73631-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="73631-116">Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden.</span><span class="sxs-lookup"><span data-stu-id="73631-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="73631-117">Sie können z. B. das Verhalten von Teilen des Steuerelements mithilfe von Eigenschaften ändern, <xref:System.Windows.Controls.ContextMenu>oder Sie können Teile zu einer hinzufügen oder das Layout einer ändern.</span><span class="sxs-lookup"><span data-stu-id="73631-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="73631-118">Die folgenden Beispiele zeigen mehrere <xref:System.Windows.Controls.ContextMenu> Möglichkeiten zum Hinzufügen von Stilen zu Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="73631-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="73631-119">Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="73631-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="73631-120">Das Beispiel <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> weist <xref:System.Windows.Controls.Control.Background%2A> die <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> Farbe <xref:System.Windows.Controls.Control.Foreground%2A> und die <xref:System.Windows.Controls.ContextMenu>Farbe der zu.</span><span class="sxs-lookup"><span data-stu-id="73631-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="73631-121">Im folgenden Beispiel <xref:System.Windows.Trigger> wird das Element <xref:System.Windows.Controls.Menu> verwendet, um die Darstellung <xref:System.Windows.Controls.ContextMenu>eines als Antwort auf Ereignisse zu ändern, die auf der ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="73631-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="73631-122">Wenn ein Benutzer die Maus über das <xref:System.Windows.Controls.ContextMenu> Menü bewegt, ändert sich die Darstellung der Elemente.</span><span class="sxs-lookup"><span data-stu-id="73631-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73631-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73631-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="73631-124">Contextmenu</span><span class="sxs-lookup"><span data-stu-id="73631-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="73631-125">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="73631-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="73631-126">Beispiel für WPF-Steuerelementsammlungen</span><span class="sxs-lookup"><span data-stu-id="73631-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
