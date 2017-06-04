---
title: "Gewusst wie: Animieren einer Eigenschaft ohne Storyboard | Microsoft Docs"
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
  - "Animation, Nicht-Storyboard (lokal)"
  - "Lokale Animation"
  - "Nicht-Storyboard-Animation"
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Animieren einer Eigenschaft ohne Storyboard
Dieses Beispiel veranschaulicht eine Möglichkeit, eine Animation ohne ein <xref:System.Windows.Media.Animation.Storyboard> auf eine Eigenschaft anzuwenden.  
  
> [!NOTE]
>  Diese Funktionalität ist in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nicht verfügbar.  Informationen über das Animieren einer Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Verwenden Sie die <xref:System.Windows.UIElement.BeginAnimation%2A>\-Methode, um eine lokale Animation auf eine Eigenschaft anzuwenden.  Für diese Methode sind zwei Parameter erforderlich: eine <xref:System.Windows.DependencyProperty>, die die zu animierende Eigenschaft angibt und die Animation, die auf die Eigenschaft angewendet wird.  
  
## Beispiel  
 Im folgenden Beispiel wird die Animierung von Breite und Hintergrundfarbe einer <xref:System.Windows.Controls.Button> dargestellt.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Zum Animieren von verschiedenen Eigenschaftstypen im <xref:System.Windows.Media.Animation>\-Namespace ist eine Reihe von Animationsklassen vorhanden.  Weitere Informationen über das Animieren von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Weitere Informationen über [Abhängigkeitseigenschaften](GTMT) \(der Eigenschaftentyp, der in diesen Beispielen verwendet wird\) und ihre Features finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Es gibt weitere Möglichkeiten, ohne <xref:System.Windows.Media.Animation.Storyboard>\-Objekte zu animieren. Weitere Informationen finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)