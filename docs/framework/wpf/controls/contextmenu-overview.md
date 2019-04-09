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
ms.openlocfilehash: 1818718d3ca9e8f56da99d6e504b41b217bfd980
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203547"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="93566-102">Übersicht über ContextMenu</span><span class="sxs-lookup"><span data-stu-id="93566-102">ContextMenu Overview</span></span>
<span data-ttu-id="93566-103">Die <xref:System.Windows.Controls.ContextMenu> Klasse darstellt, das Element, das Funktionen verfügbar macht, indem Sie ein kontextspezifisches <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="93566-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="93566-104">Ein Benutzer in der Regel macht der <xref:System.Windows.Controls.ContextMenu> in die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mit der rechten Maustaste in der Maustaste.</span><span class="sxs-lookup"><span data-stu-id="93566-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="93566-105">In diesem Thema werden die <xref:System.Windows.Controls.ContextMenu> Element und enthält Beispiele zu dessen Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code.</span><span class="sxs-lookup"><span data-stu-id="93566-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="93566-106">ContextMenu-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="93566-106">ContextMenu Control</span></span>  
 <span data-ttu-id="93566-107">Ein <xref:System.Windows.Controls.ContextMenu> an ein bestimmtes Steuerelement angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="93566-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="93566-108">Die <xref:System.Windows.Controls.ContextMenu> Element können Sie Benutzern eine Liste von Elementen zur Verfügung stellen, die Befehle oder Optionen, die ein Steuerelement zugeordnet, z. B. sind angeben einer <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="93566-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="93566-109">Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="93566-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="93566-110">Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> ein Untermenü geöffnet oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="93566-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="93566-111">Erstellen von ContextMenus</span><span class="sxs-lookup"><span data-stu-id="93566-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="93566-112">Die folgenden Beispiele zeigen, wie Sie erstellen eine <xref:System.Windows.Controls.ContextMenu> mit Untermenüs.</span><span class="sxs-lookup"><span data-stu-id="93566-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="93566-113">Die <xref:System.Windows.Controls.ContextMenu> Steuerelemente an Steuerelemente angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="93566-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="93566-114">Anwenden von Stilen auf ein ContextMenu</span><span class="sxs-lookup"><span data-stu-id="93566-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="93566-115">Mithilfe eines Steuerelements <xref:System.Windows.Style>, Sie können das Aussehen und Verhalten der drastisch ändern eine <xref:System.Windows.Controls.ContextMenu> ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="93566-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="93566-116">Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden.</span><span class="sxs-lookup"><span data-stu-id="93566-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="93566-117">Beispielsweise können Sie das Verhalten von Teilen des Steuerelements mithilfe von Eigenschaften ändern, oder Sie können Teile zum Hinzufügen oder Ändern des Layouts, eine <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="93566-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="93566-118">Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Hinzufügen zu <xref:System.Windows.Controls.ContextMenu> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="93566-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="93566-119">Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="93566-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="93566-120">Das Beispiel weist <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> als die <xref:System.Windows.Controls.Control.Background%2A> Farbe und <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> als die <xref:System.Windows.Controls.Control.Foreground%2A> Farbe der <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="93566-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="93566-121">Im folgenden Beispiel wird der <xref:System.Windows.Trigger> Element so ändern Sie die Darstellung einer <xref:System.Windows.Controls.Menu> als Reaktion auf Ereignisse, die auf ausgelöst werden die <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="93566-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="93566-122">Wenn ein Benutzer die Maus bewegt, über das Menü, das die Darstellung der <xref:System.Windows.Controls.ContextMenu> Elemente geändert wird.</span><span class="sxs-lookup"><span data-stu-id="93566-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93566-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93566-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="93566-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="93566-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="93566-125">ContextMenu-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="93566-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="93566-126">Beispiel für WPF-Steuerelementsammlungen</span><span class="sxs-lookup"><span data-stu-id="93566-126">WPF Controls Gallery Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160053)
