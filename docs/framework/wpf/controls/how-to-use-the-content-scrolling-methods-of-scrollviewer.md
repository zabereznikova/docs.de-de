---
title: "Gewusst wie: Verwenden der ScrollViewer-Bildlaufmethoden | Microsoft Docs"
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
  - "IScrollInfo-Schnittstelle"
  - "Bildlaufmethoden"
  - "ScrollViewer-Steuerelement, Bildlaufmethoden"
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Verwenden der ScrollViewer-Bildlaufmethoden
In diesem Beispiel wird die Verwendung der Bildlaufmethoden des <xref:System.Windows.Controls.ScrollViewer>\-Elements veranschaulicht.  Mithilfe dieser Methoden kann ein Bildlauf in Zeilen\- oder Seitenschritten in einem <xref:System.Windows.Controls.ScrollViewer> durchgeführt werden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ScrollViewer> mit dem Namen `sv1` erstellt, der ein untergeordnetes <xref:System.Windows.Controls.TextBlock>\-Element hostet.  Da das <xref:System.Windows.Controls.TextBlock>\-Element größer als das übergeordnete <xref:System.Windows.Controls.ScrollViewer>\-Element ist, werden Bildlaufleisten eingeblendet, die den Bildlauf ermöglichen.  <xref:System.Windows.Controls.Button>\-Elemente, die die verschiedenen Bildlaufmethoden darstellen, werden auf der linken Seite in einem separaten <xref:System.Windows.Controls.StackPanel>\-Objekt angedockt.  Jedes <xref:System.Windows.Controls.Button>\-Element in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei ruft eine zugeordnete benutzerdefinierte Methode auf, die das Bildlaufverhalten im <xref:System.Windows.Controls.ScrollViewer>\-Element steuert.  
  
 [!code-xml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ScrollViewer.LineUp%2A>\-Methode und die <xref:System.Windows.Controls.ScrollViewer.LineDown%2A>\-Methode verwendet.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.StackPanel>