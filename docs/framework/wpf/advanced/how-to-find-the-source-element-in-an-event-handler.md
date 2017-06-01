---
title: "Gewusst wie: Suchen des Quellelements in einem Ereignishandler | Microsoft Docs"
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
  - "Ereignishandler, Suchen des Quellelements in"
  - "Quellelement in Ereignishandlern"
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Suchen des Quellelements in einem Ereignishandler
Dieses Beispiel zeigt, wie Sie in einem Ereignishandler nach dem Quellelement suchen.  
  
## Beispiel  
 Das folgende Beispiel zeigt einen <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler, der in einer Code\-Behind\-Datei deklariert wird.  Wenn Benutzer auf die Schaltfläche klicken, der der Handler zugeordnet ist, ändert der Handler einen Eigenschaftswert.  Der Handlercode verwendet die <xref:System.Windows.RoutedEventArgs.Source%2A>\-Eigenschaft der Routingereignisdaten, die in den Ereignisargumenten gemeldet werden, um den <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaftswert für das <xref:System.Windows.RoutedEventArgs.Source%2A>\-Element zu ändern.  
  
 [!code-xml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## Siehe auch  
 <xref:System.Windows.RoutedEventArgs>   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)