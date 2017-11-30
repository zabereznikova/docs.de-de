---
title: 'Gewusst wie: Steuern von Animationen mit From, To und By'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Gewusst wie: Steuern von Animationen mit From, To und By
"Von/zu/von" oder "grundlegende Animation" erstellt einen Übergang zwischen zwei Zielwerten (finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) eine Einführung in die verschiedenen Arten von Animationen). Verwenden Sie zum Festlegen der Zielwerte einer grundlegenden Animation seine <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.  Die folgende Tabelle enthält wie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften dürfen zusammen verwendet werden oder separat um Zielwerte einer Animation zu bestimmen.  
  
|Angegebene Eigenschaften|Resultierendes Verhalten|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Im Verlauf des Animation aus dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft oder einer vorherigen Animation dem Basiswert der animierten Eigenschaft Ausgabewert, abhängig von der Konfiguration der vorherigen Animation.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Im Verlauf des Animation aus dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft auf den Wert gemäß der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Im Verlauf des Animation aus dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> auf den Wert, der durch die Summe der angegebenen Eigenschaft der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation Zustand aus dem Basiswert der animierten Eigenschaft oder eine vorherige Animation Ausgabewert angegebene Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Im Verlauf des Animation aus dem Basiswert der animierten Eigenschaft oder einer vorherigen Animation Ausgabewert die Summe dieses Werts und auf dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft.|  
  
> [!NOTE]
>  Legen Sie nicht sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft und die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft in derselben Animation.  
  
 Um andere Interpolationsmethoden zu verwenden oder eine Animation zwischen mehr als zwei Zielwerten auszuführen, verwenden Sie eine Keyframe-Animation. Finden Sie unter [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) für Weitere Informationen.  
  
 Informationen zum Anwenden mehrerer Animationen auf eine einzelne Eigenschaft finden Sie unter [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt unterschiedlichen Auswirkungen der Einstellung <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaften von Animationen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](http://go.microsoft.com/fwlink/?LinkID=159988)
