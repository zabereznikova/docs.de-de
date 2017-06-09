---
title: "Gewusst wie: Positionieren von untergeordneten Elementen mithilfe der angef&#252;gten Eigenschaften von Canvas | Microsoft Docs"
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
  - "Angefügte Eigenschaften [WPF-Designer]"
  - "Canvas-Steuerelement, Angefügte Eigenschaften"
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Positionieren von untergeordneten Elementen mithilfe der angef&#252;gten Eigenschaften von Canvas
Dieses Beispiel zeigt, wie die [angefügten Eigenschaften](GTMT) von <xref:System.Windows.Controls.Canvas> verwendet werden, um untergeordnete Elemente zu positionieren.  
  
## Beispiel  
 Im folgenden Beispiel werden vier <xref:System.Windows.Controls.Button>\-Elemente als untergeordnete Elemente eines übergeordneten <xref:System.Windows.Controls.Canvas> hinzugefügt.  Jedes untergeordnete Element stellt eine andere angefügte Eigenschaft von <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A> und <xref:System.Windows.Controls.Canvas.Top%2A> dar.  Jeder <xref:System.Windows.Controls.Button> wird relativ zum übergeordneten <xref:System.Windows.Controls.Canvas> und gemäß seines zugeordneten Eigenschaftswerts positioniert.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.Canvas.Bottom%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 <xref:System.Windows.Controls.Canvas.Right%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Button>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)   
 [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)