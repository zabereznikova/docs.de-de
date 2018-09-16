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
ms.openlocfilehash: 54fd823594fba4500f35ed1d69720a3309e54a36
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666771"
---
# <a name="contextmenu-overview"></a>Übersicht über ContextMenu
Die <xref:System.Windows.Controls.ContextMenu> Klasse darstellt, das Element, das Funktionen verfügbar macht, indem Sie ein kontextspezifisches <xref:System.Windows.Controls.Menu>. Ein Benutzer in der Regel macht der <xref:System.Windows.Controls.ContextMenu> in die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mit der rechten Maustaste in der Maustaste. In diesem Thema werden die <xref:System.Windows.Controls.ContextMenu> Element und enthält Beispiele zu dessen Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code.  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a>ContextMenu-Steuerelement  
 Ein <xref:System.Windows.Controls.ContextMenu> an ein bestimmtes Steuerelement angefügt ist. Die <xref:System.Windows.Controls.ContextMenu> Element können Sie Benutzern eine Liste von Elementen zur Verfügung stellen, die Befehle oder Optionen, die ein Steuerelement zugeordnet, z. B. sind angeben einer <xref:System.Windows.Controls.Button>. Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen. Klicken Sie in der Regel eine <xref:System.Windows.Controls.MenuItem> ein Untermenü geöffnet oder bewirkt, dass eine Anwendung, einen Befehl auszuführen.  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a>Erstellen von ContextMenus  
 Die folgenden Beispiele zeigen, wie Sie erstellen eine <xref:System.Windows.Controls.ContextMenu> mit Untermenüs. Die <xref:System.Windows.Controls.ContextMenu> Steuerelemente an Steuerelemente angefügt werden.  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a>Anwenden von Stilen auf ein ContextMenu  
 Mithilfe eines Steuerelements <xref:System.Windows.Style>, Sie können das Aussehen und Verhalten der drastisch ändern eine <xref:System.Windows.Controls.ContextMenu> ohne ein benutzerdefiniertes Steuerelement schreiben zu müssen. Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden. Beispielsweise können Sie das Verhalten von Teilen des Steuerelements mithilfe von Eigenschaften ändern, oder Sie können Teile zum Hinzufügen oder Ändern des Layouts, eine <xref:System.Windows.Controls.ContextMenu>. Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Hinzufügen zu <xref:System.Windows.Controls.ContextMenu> Steuerelemente.  
  
 Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können. Das Beispiel weist <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> als die <xref:System.Windows.Controls.Control.Background%2A> Farbe und <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> als die <xref:System.Windows.Controls.Control.Foreground%2A> Farbe der <xref:System.Windows.Controls.ContextMenu>.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Trigger> Element so ändern Sie die Darstellung einer <xref:System.Windows.Controls.Menu> als Reaktion auf Ereignisse, die auf ausgelöst werden die <xref:System.Windows.Controls.ContextMenu>. Wenn ein Benutzer die Maus bewegt, über das Menü, das die Darstellung der <xref:System.Windows.Controls.ContextMenu> Elemente geändert wird.  
  
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
 [Beispiel für WPF-Steuerelementsammlungen](https://go.microsoft.com/fwlink/?LinkID=160053)
