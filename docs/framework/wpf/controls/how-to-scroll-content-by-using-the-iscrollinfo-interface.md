---
title: "Gewusst wie: Durchf&#252;hren eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle | Microsoft Docs"
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
  - "Scrollen von Inhalt"
  - "ScrollViewer-Steuerelement, Scrollen von Inhalt"
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Durchf&#252;hren eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle
Dieses Beispiel veranschaulicht, wie mithilfe der <xref:System.Windows.Controls.Primitives.IScrollInfo>\-Schnittstelle ein Bildlauf durch Inhalte durchgeführt wird.  
  
## Beispiel  
 Im folgenden Beispiel werden die Features der <xref:System.Windows.Controls.Primitives.IScrollInfo>\-Schnittstelle veranschaulicht.  Im Beispiel wird ein <xref:System.Windows.Controls.StackPanel>\-Element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] erstellt, das in einem übergeordneten <xref:System.Windows.Controls.ScrollViewer>\-Element geschachtelt ist.  In den untergeordneten Elementen von <xref:System.Windows.Controls.StackPanel> kann ein logischer Bildlauf mithilfe der Methoden durchgeführt werden, die in der <xref:System.Windows.Controls.Primitives.IScrollInfo>\-Schnittstelle definiert sind. Im Code können die untergeordneten Elemente in eine Instanz von <xref:System.Windows.Controls.StackPanel> \(`sp1`\) umgewandelt werden.  
  
 [!code-xml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Jede <xref:System.Windows.Controls.Button> der Datei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] löst eine zugeordnete benutzerdefinierte Methode aus, durch die das Bildlaufverhalten in <xref:System.Windows.Controls.StackPanel> gesteuert wird.  Das folgende Beispiel veranschaulicht die Verwendung der Methoden <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>. Außerdem wird die übliche Verwendung aller Positionierungsmethoden dargestellt, die in der <xref:System.Windows.Controls.Primitives.IScrollInfo>\-Klasse definiert werden.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 <xref:System.Windows.Controls.StackPanel>   
 [Übersicht über ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)