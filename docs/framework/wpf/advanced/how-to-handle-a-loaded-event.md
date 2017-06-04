---
title: "Gewusst wie: Behandeln eines geladenen Ereignisses | Microsoft Docs"
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
  - "Ereignisse, Geladen"
  - "Geladene Ereignisse"
  - "XAML, Geladene Ereignisse"
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Behandeln eines geladenen Ereignisses
In diesem Beispiel wird veranschaulicht, wie das <xref:System.Windows.FrameworkElement.Loaded?displayProperty=fullName>\-Ereignis behandelt wird, und es wird ein entsprechendes Szenario für die Behandlung dieses Ereignisses dargestellt.  Der Handler erstellt eine <xref:System.Windows.Controls.Button>, wenn die Seite geladen wird.  
  
## Beispiel  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zusammen mit einer Code\-Behind\-Datei verwendet.  
  
 [!code-xml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement>   
 [Objektlebensdauer\-Ereignisse](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)