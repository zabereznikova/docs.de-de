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
ms.openlocfilehash: e862f02e736cb8507dde5036700d751f8af0a226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552869"
---
# <a name="contextmenu-overview"></a>Übersicht über ContextMenu
Die <xref:System.Windows.Controls.ContextMenu> -Klasse stellt das Element, die Funktionalität bereitstellt, mit einem kontextspezifisch <xref:System.Windows.Controls.Menu>. Ein Benutzer in der Regel stellt die <xref:System.Windows.Controls.ContextMenu> in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] durch Rechtsklick auf die Maustaste los. Dieses Thema enthält die <xref:System.Windows.Controls.ContextMenu> Element sowie Beispiele für die Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code.  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>ContextMenu-Steuerelement  
 Ein <xref:System.Windows.Controls.ContextMenu> auf ein bestimmtes Steuerelement angefügt ist. Die <xref:System.Windows.Controls.ContextMenu> Element ermöglicht es Ihnen, Benutzer mit einer Liste von Elementen dar, die Befehle oder Optionen, die einem bestimmten Steuerelement zugeordnet, z. B. sind angeben einer <xref:System.Windows.Controls.Button>. Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen. Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> öffnet ein Untermenü oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Erstellen von ContextMenus  
 Die folgenden Beispiele zeigen, wie zum Erstellen einer <xref:System.Windows.Controls.ContextMenu> mit Untermenüs. Die <xref:System.Windows.Controls.ContextMenu> Steuerelemente Schaltflächen-Steuerelemente angefügt werden.  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Anwenden von Stilen auf ein ContextMenu  
 Mithilfe eines Steuerelements <xref:System.Windows.Style>, Sie können das Aussehen und Verhalten von erheblich ändern einer <xref:System.Windows.Controls.ContextMenu> ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden. Beispielsweise können Sie das Verhalten von Teilen des Steuerelements mithilfe von Eigenschaften ändern, oder Sie können Teile hinzufügen oder Ändern des Layouts einer <xref:System.Windows.Controls.ContextMenu>. Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Hinzufügen zu <xref:System.Windows.Controls.ContextMenu> Steuerelemente.  
  
 Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können. Im Beispiel weist <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> als die <xref:System.Windows.Controls.Control.Background%2A> Farbe und <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> als die <xref:System.Windows.Controls.Control.Foreground%2A> Farbe der <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Trigger> Element so ändern Sie die Darstellung von einer <xref:System.Windows.Controls.Menu> als Antwort auf Ereignisse, die ausgelöst werden, auf die <xref:System.Windows.Controls.ContextMenu>. Wenn ein Benutzer die Maus bewegt, über das Menü, die Darstellung der <xref:System.Windows.Controls.ContextMenu> Elemente ändert.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [ContextMenu-Stile und -Vorlagen](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 [Beispiel für WPF-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)
