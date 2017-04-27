---
title: "&#220;bersicht &#252;berToolBar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, ToolBar"
  - "ToolBar-Steuerelement"
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# &#220;bersicht &#252;berToolBar
<xref:System.Windows.Controls.ToolBar>\-Steuerelemente sind Container für eine Gruppe von Befehlen oder Steuerelementen, die in der Regel verwandte Funktionen aufweisen.  Eine <xref:System.Windows.Controls.ToolBar> enthält normalerweise Schaltflächen, die Befehle aufrufen.  
  
   
  
<a name="ToolBarControl"></a>   
## ToolBar\-Steuerelement  
 Das <xref:System.Windows.Controls.ToolBar>\-Steuerelement bezieht seinen Namen von der symbolleistenähnlichen Anordnung von Schaltflächen oder anderen Steuerelementen in einer einzelnen Zeile oder Spalte.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar>\-Steuerelemente bieten einen Überlaufmechanismus, der alle Elemente, die nicht auf natürliche Weise in ein größenbeschränktes <xref:System.Windows.Controls.ToolBar>\-Objekt passen, in einem speziellen Überlaufbereich platziert.  Des Weiteren werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar>\-Steuerelemente in der Regel mit dem verwandten <xref:System.Windows.Controls.ToolBarTray>\-Steuerelement verwendet, das ein spezielles Layoutverhalten aufweist und Unterstützung für vom Benutzer initiierte Größenänderungen und Anordnungen von Symbolleisten bietet.  
  
<a name="Creating_ToolBars"></a>   
## Angeben der Position von ToolBar\-Elementen in einem ToolBarTray  
 Mit den Eigenschaften <xref:System.Windows.Controls.ToolBar.Band%2A> und <xref:System.Windows.Controls.ToolBar.BandIndex%2A> positionieren Sie das <xref:System.Windows.Controls.ToolBar>\-Element im <xref:System.Windows.Controls.ToolBarTray>\-Element.  <xref:System.Windows.Controls.ToolBar.Band%2A> gibt die Position an, an der das <xref:System.Windows.Controls.ToolBar>\-Element im übergeordneten <xref:System.Windows.Controls.ToolBarTray>\-Element positioniert wird.  <xref:System.Windows.Controls.ToolBar.BandIndex%2A> gibt die Reihenfolge an, in der das <xref:System.Windows.Controls.ToolBar>\-Element innerhalb des zugehörigen Bands platziert wird.  Im folgenden Beispiel wird veranschaulicht, wie diese Eigenschaft zum Platzieren von <xref:System.Windows.Controls.ToolBar>\-Steuerelementen in einem <xref:System.Windows.Controls.ToolBarTray> verwendet wird.  
  
 [!code-xml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## ToolBar\-Elemente mit Überlaufelementen  
 Oft enthalten <xref:System.Windows.Controls.ToolBar>\-Steuerelemente mehr Elemente als in die Größe der Symbolleiste passen.  In diesem Fall wird in der <xref:System.Windows.Controls.ToolBar> eine Überlaufschaltfläche angezeigt.  Um die Überlaufelemente anzuzeigen, klickt ein Benutzer auf die Überlaufschaltfläche. Die Elemente werden dann in einem Popupfenster unter der <xref:System.Windows.Controls.ToolBar> angezeigt.  Die folgende Grafik zeigt eine <xref:System.Windows.Controls.ToolBar> mit Überlaufelementen.  
  
 ![ToolBar mit Überlauf](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
Symbolleiste mit Überlaufelementen  
  
 Sie können angeben, wann ein Element einer Symbolleiste im Überlaufbereich platziert wird, indem Sie die angehängte <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>, <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName> oder <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName> festlegen.  Im folgenden Beispiel wird angegeben, dass die letzten vier Schaltflächen der Symbolleiste immer im Überlaufbereich platziert werden.  
  
 [!code-xml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 Die <xref:System.Windows.Controls.ToolBar> verwendet in ihrer <xref:System.Windows.Controls.ControlTemplate> einen <xref:System.Windows.Controls.Primitives.ToolBarPanel> und einen <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>.  Der <xref:System.Windows.Controls.Primitives.ToolBarPanel> ist für das Layout der Elemente auf der Symbolleiste verantwortlich.  Der <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> ist für das Layout der Elemente verantwortlich, die nicht auf die <xref:System.Windows.Controls.ToolBar> passen.  Ein <xref:System.Windows.Controls.ControlTemplate>\-Beispiel für eine <xref:System.Windows.Controls.ToolBar> finden Sie unter  
  
 [ToolBar\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## Siehe auch  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>   
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>   
 [Formatieren von Steuerelementen in einer Symbolleiste](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)   
 [Beispiel für WPF\-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)