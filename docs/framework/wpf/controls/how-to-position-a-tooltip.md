---
title: "Gewusst wie: Positionieren einer QuickInfo | Microsoft Docs"
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
  - "Positionieren von ToolTip-Steuerelementen"
  - "ToolStrip-Steuerelement, Positionieren"
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Positionieren einer QuickInfo
In diesem Beispiel wird gezeigt, wie die Position eines QuickInfos auf dem Bildschirm angegeben wird.  
  
## Beispiel  
 Sie können ein QuickInfo mithilfe eines Satzes aus fünf Eigenschaften positionieren, die in den Klassen <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> definiert sind.  In der folgenden Tabelle werden diese beiden Sätze von je fünf Eigenschaften mit Links zu den jeweils zugehörigen Referenzdokumentationen nach Klassen geordnet aufgeführt.  
  
### Zugehörige QuickInfo\-Eigenschaften nach Klasse geordnet  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=fullName>\-Klasseneigenschaften|<xref:System.Windows.Controls.ToolTipService?displayProperty=fullName>\-Klasseneigenschaften|  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=fullName>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=fullName>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=fullName>|  
  
 Wenn Sie den Inhalt eines QuickInfos mithilfe eines <xref:System.Windows.Controls.ToolTip> \-Objekts definieren, können Sie die Eigenschaften beider Klassen verwenden. Die <xref:System.Windows.Controls.ToolTipService>\-Eigenschaften haben jedoch Vorrang.  Verwenden Sie die <xref:System.Windows.Controls.ToolTipService>\-Eigenschaften für QuickInfos, die nicht als <xref:System.Windows.Controls.ToolTip>\-Objekte definiert sind.  
  
 Die folgenden Darstellungen zeigen, wie ein QuickInfo mithilfe dieser Eigenschaften positioniert wird.  Obwohl in den [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispielen dieser Darstellungen gezeigt wird, wie die Eigenschaften festgelegt werden, die durch die <xref:System.Windows.Controls.ToolTip>\-Klasse definiert sind, folgen die entsprechenden Eigenschaften der <xref:System.Windows.Controls.ToolTipService>\-Klasse denselben Layoutregeln.  Weitere Informationen zu den möglichen Werten für die Placement\-Eigenschaft finden Sie unter [Verhalten beim Platzieren von Popups](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  
  
 ![QuickInfo&#45;Platzierung](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")  
  
        QuickInfo\-Platzierung mithilfe der Placement\-Eigenschaft  
  
 ![Platzieren einer QuickInfo mithilfe eines Platzierungsrechtecks](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
  
        QuickInfo\-Platzierung mithilfe der Eigenschaften Placement und PlacementRectangle  
  
 ![QuickInfo&#45;Platzierungsdiagramm](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
  
        QuickInfo\-Platzierung mithilfe der Eigenschaften Placement, PlacementRectangle und Offset  
  
 Im folgenden Beispiel wird dargestellt, wie mithilfe der <xref:System.Windows.Controls.ToolTip>\-Eigenschaften die Position eines QuickInfos angegeben wird, dessen Inhalt ein <xref:System.Windows.Controls.ToolTip>\-Objekt ist.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 Im folgenden Beispiel wird dargestellt, wie mithilfe der <xref:System.Windows.Controls.ToolTipService>\-Eigenschaften die Position eines QuickInfos angegeben wird, dessen Inhalt kein <xref:System.Windows.Controls.ToolTip>\-Objekt ist.  
  
 [!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)   
 [Use the ContextMenuService and ToolTipService](http://msdn.microsoft.com/de-de/809b0e9c-d612-4cda-b8af-1a698c68f4d1)