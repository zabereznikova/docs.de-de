---
title: "Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox | Microsoft Docs"
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
  - "Steuerelemente, Viewbox"
  - "Stretch-Eigenschaften"
  - "StretchDirection-Eigenschaften"
  - "Viewbox-Steuerelement"
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie der Wert einer <xref:System.Windows.Controls.Viewbox.StretchDirection%2A>\-Eigenschaft und einer <xref:System.Windows.Controls.Viewbox.Stretch%2A>\-Eigenschaft einer <xref:System.Windows.Controls.Viewbox> geändert wird.  
  
 Im ersten Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwendet, um ein <xref:System.Windows.Controls.Viewbox>\-Element zu definieren.  Eine <xref:System.Windows.FrameworkElement.MaxWidth%2A>\-Eigenschaft und eine <xref:System.Windows.FrameworkElement.MaxHeight%2A>\-Eigenschaft von 400 werden zugewiesen.  In diesem Beispiel wird ein <xref:System.Windows.Controls.Image>\-Element innerhalb des <xref:System.Windows.Controls.Viewbox> geschachtelt.  <xref:System.Windows.Controls.Button>\-Elemente, die den Eigenschaftswerten der <xref:System.Windows.Controls.Viewbox.Stretch%2A>\-Enumeration und der <xref:System.Windows.Controls.StretchDirection>\-Enumeration entsprechen, ändern das Streckverhalten des geschachtelten <xref:System.Windows.Controls.Image>.  
  
 [!code-xml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Die folgende Code\-Behind\-Datei behandelt die <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignisse, die im vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel definiert wurden.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Viewbox>   
 <xref:System.Windows.Media.Stretch>   
 <xref:System.Windows.Controls.StretchDirection>