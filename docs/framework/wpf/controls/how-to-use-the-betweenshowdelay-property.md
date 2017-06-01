---
title: "Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft | Microsoft Docs"
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
  - "BetweenShowDelay-Uhrzeiteigenschaft"
  - "ToolStrip-Steuerelement, BetweenShowDelay-Uhrzeiteigenschaft"
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden der BetweenShowDelay-Eigenschaft
Dieses Beispiel veranschaulicht die Verwendung der <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>\-Zeiteigenschaft, um QuickInfos schnell — ohne oder ohne große Verzögerung — anzuzeigen, wenn ein Benutzer den Mauszeiger von einer QuickInfo direkt auf eine andere Quickinfo bewegt.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>\-Eigenschaft auf eine Sekunde \(1000 Millisekunden\) und die <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>\-Eigenschaft auf zwei Sekunden \(2000 Millisekunden\) festgelegt, für die QuickInfo beider <xref:System.Windows.Shapes.Ellipse> \-Steuerelemente.  Wenn die QuickInfo für eine der Ellipsen angezeigt wird, und Sie dann den Mauszeiger innerhalb von zwei Sekunden über eine andere Ellipse bewegen und dort halten, wird die QuickInfo für die zweite Ellipse sofort angezeigt.  
  
 In den folgenden beiden Szenarien wird <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> angewendet, wodurch die QuickInfo der zweiten Ellipse mit einer Sekunde Verzögerung angezeigt wird:  
  
-   Wenn mehr als zwei Sekunden vergehen, bevor der Mauszeiger auf die zweite Schaltfläche bewegt wird.  
  
-   Wenn die QuickInfo am Anfang des Zeitintervalls für die erste Ellipse nicht angezeigt wird.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md)