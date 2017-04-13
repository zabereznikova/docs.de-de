---
title: "&#220;bersicht &#252;ber ContextMenu | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ContextMenu-Steuerelemente [WPF], Informationen über ContextMenu-Steuerelemente"
  - "Steuerelemente, ContextMenu"
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber ContextMenu
Die <xref:System.Windows.Controls.ContextMenu>\-Klasse stellt das Element dar, das durch ein kontextspezifisches <xref:System.Windows.Controls.Menu> Funktionen verfügbar macht.  Ein Benutzer ruft in der Regel das <xref:System.Windows.Controls.ContextMenu> in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] auf, indem er mit der rechten Maustaste klickt.  In diesem Thema wird das <xref:System.Windows.Controls.ContextMenu>\-Element eingeführt. Außerdem sind Beispiele für dessen Verwendung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code enthalten.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="contextmenu_control"></a>   
## ContextMenu\-Steuerelement  
 <xref:System.Windows.Controls.ContextMenu> ist an ein bestimmtes Steuerelement angefügt.  Durch das <xref:System.Windows.Controls.ContextMenu>\-Element können Sie Benutzern eine Liste mit Elementen zur Verfügung stellen, die Befehle oder Optionen für ein bestimmtes Steuerelement angeben, z. B. <xref:System.Windows.Controls.Button>.  Benutzer klicken mit der rechten Maustaste auf das Steuerelement, damit das Menü angezeigt wird.  In der Regel wird durch Klicken auf ein <xref:System.Windows.Controls.MenuItem> ein Untermenü geöffnet oder ein Befehl durch die Anwendung ausgeführt.  
  
<a name="creating_contextmenus"></a>   
## Erstellen von ContextMenus  
 Im folgenden Beispiel wird das Erstellen von <xref:System.Windows.Controls.ContextMenu> mit Untermenüs veranschaulicht.  Die <xref:System.Windows.Controls.ContextMenu>\-Steuerelemente sind an Schaltflächen\-Steuerelemente angefügt.  
  
 [!code-xml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## Anwenden von Formaten auf ein ContextMenu  
 Durch die Verwendung von <xref:System.Windows.Style> für ein Steuerelement können Sie die Darstellung und das Verhalten von <xref:System.Windows.Controls.ContextMenu> eindrucksvoll verändern, ohne dazu ein benutzerdefiniertes Steuerelement schreiben zu müssen.  Sie können nicht nur visuelle Eigenschaften festlegen, sondern auch Formate auf Teile eines Steuerelements anwenden.  Beispielsweise können Sie das Verhalten von Teilen des Steuerelements anhand von Eigenschaften ändern, zusätzliche Teile zu <xref:System.Windows.Controls.ContextMenu> hinzufügen oder dessen Layout ändern.  Die folgenden Beispiele zeigen verschiedene Möglichkeiten auf, wie Sie <xref:System.Windows.Controls.ContextMenu>\-Steuerelementen Formate hinzufügen können.  
  
 Im ersten Beispiel wird ein Format namens `SimpleSysResources` definiert, und es wird veranschaulicht, wie die aktuellen Systemeinstellungen im Format verwendet werden.  Im Beispiel wird <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> als <xref:System.Windows.Controls.Control.Background%2A>\-Farbe und <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> als <xref:System.Windows.Controls.Control.Foreground%2A>\-Farbe von <xref:System.Windows.Controls.ContextMenu> zugewiesen.  
  
```  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Trigger>\-Element verwendet, um die Darstellung von <xref:System.Windows.Controls.Menu> als Reaktion auf Ereignisse zu ändern, die in <xref:System.Windows.Controls.ContextMenu> ausgelöst werden.  Wenn ein Benutzer die Maus über das Menü bewegt, ändert sich die Darstellung der <xref:System.Windows.Controls.ContextMenu>\-Elemente.  
  
```  
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
  
## Siehe auch  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.Menu>   
 <xref:System.Windows.Controls.MenuItem>   
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)   
 [ContextMenu\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)   
 [Beispiel für WPF\-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)