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
# <a name="contextmenu-overview"></a>Übersicht über ContextMenu
Die <xref:System.Windows.Controls.ContextMenu> Klasse stellt das Element dar, das <xref:System.Windows.Controls.Menu>Funktionen mithilfe einer kontextspezifischen verfügbar macht. In der Regel macht <xref:System.Windows.Controls.ContextMenu> ein [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Benutzer die in der durch Rechtsklick auf die Maustaste verfügbar. In diesem <xref:System.Windows.Controls.ContextMenu> Thema wird das Element vorgestellt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Beispiele für die Verwendung in und Code vorgestellt.  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>ContextMenu-Steuerelement  
 A <xref:System.Windows.Controls.ContextMenu> ist an ein bestimmtes Steuerelement angefügt. Mit <xref:System.Windows.Controls.ContextMenu> dem Element können Sie Benutzern eine Liste von Elementen präsentieren, die Befehle oder <xref:System.Windows.Controls.Button>Optionen angeben, die einem bestimmten Steuerelement zugeordnet sind, z. B. eine . Das Menü wird mit einem Rechtsklick mit der Maus aufgerufen. In der Regel <xref:System.Windows.Controls.MenuItem> wird durch Klicken auf ein Untermenü ein Untermenü geöffnet oder eine Anwendung veranlasst, einen Befehl auszuführen.  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>Erstellen von ContextMenus  
 Die folgenden Beispiele zeigen, <xref:System.Windows.Controls.ContextMenu> wie Sie ein mit Untermenüs erstellen. Die <xref:System.Windows.Controls.ContextMenu> Steuerelemente werden an Schaltflächensteuerelemente angehängt.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>Anwenden von Stilen auf ein ContextMenu  
 Durch die <xref:System.Windows.Style>Verwendung eines Steuerelements können Sie <xref:System.Windows.Controls.ContextMenu> das Erscheinungsbild und Verhalten eines Steuerelements drastisch ändern, ohne ein benutzerdefiniertes Steuerelement zu schreiben. Zusätzlich zur Festlegung von visuellen Eigenschaften können Sie auch Stile auf Teilelemente eines Steuerelements anwenden. Sie können z. B. das Verhalten von Teilen des Steuerelements mithilfe von Eigenschaften ändern, <xref:System.Windows.Controls.ContextMenu>oder Sie können Teile zu einer hinzufügen oder das Layout einer ändern. Die folgenden Beispiele zeigen mehrere <xref:System.Windows.Controls.ContextMenu> Möglichkeiten zum Hinzufügen von Stilen zu Steuerelementen.  
  
 Im ersten Beispiel wird ein Stil mit der Bezeichnung `SimpleSysResources` definiert. An diesem Beispiel können Sie sehen, wie die aktuellen Systemeinstellungen in Ihrem Stil verwendet werden können. Das Beispiel <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> weist <xref:System.Windows.Controls.Control.Background%2A> die <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> Farbe <xref:System.Windows.Controls.Control.Foreground%2A> und die <xref:System.Windows.Controls.ContextMenu>Farbe der zu.  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Im folgenden Beispiel <xref:System.Windows.Trigger> wird das Element <xref:System.Windows.Controls.Menu> verwendet, um die Darstellung <xref:System.Windows.Controls.ContextMenu>eines als Antwort auf Ereignisse zu ändern, die auf der ausgelöst werden. Wenn ein Benutzer die Maus über das <xref:System.Windows.Controls.ContextMenu> Menü bewegt, ändert sich die Darstellung der Elemente.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [Contextmenu](contextmenu.md)
- [ContextMenu-Stile und -Vorlagen](contextmenu-styles-and-templates.md)
- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
