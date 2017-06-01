---
title: "Gewusst wie: Steuern von Animationen mit From, To und By | Microsoft Docs"
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
  - "Animation von/zu/von"
  - "Basisanimation"
  - "Animation, grundlegende animation"
  - "From/To/By-Animation"
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Steuern von Animationen mit From, To und By
"From/To/By" oder "grundlegende Animation" erstellt einen Übergang zwischen zwei Zielwerten (finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) eine Einführung in die verschiedenen Arten von Animationen). Verwenden Sie zum Festlegen der Zielwerte einer grundlegenden Animation die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.  Die folgende Tabelle enthält wie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften gemeinsam verwendet werden können oder einzeln Zielwerte einer Animation zu bestimmen.  
  
|Angegebenen Eigenschaften|Resultierende Verhalten|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Verläuft die Animation von dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft mit dem Basiswert der animierten Eigenschaft oder einer vorherigen Animation Ausgabewert, je nach Konfiguration die vorherige Animation.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Verläuft die Animation von dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft auf den angegebenen Wert durch die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Verläuft die Animation von dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft auf den angegebenen Wert durch die Summe der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation vom Basiswert der animierten Eigenschaft wechselt oder eine vorherige Animation Ausgabewert angegebene Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Verläuft die Animation von dem Basiswert der animierten Eigenschaft oder einer vorherigen Animation Ausgabewert die Summe dieses Werts und dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft.|  
  
> [!NOTE]
>  Legen Sie nicht sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft und die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft in derselben Animation.  
  
 Um andere Interpolationsmethoden zu verwenden oder eine Animation zwischen mehr als zwei Zielwerte, verwenden Sie eine Keyframe-Animation. Finden Sie unter [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) Weitere Informationen.  
  
 Informationen zum Anwenden mehrerer Animationen auf eine einzelne Eigenschaft finden Sie unter [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt die verschiedenen Effekte der Einstellung <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaften für Animationen.  
  
## <a name="example"></a>Beispiel  
 [!code-xml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Aus, To und By Animation Target Values Sample](http://go.microsoft.com/fwlink/?LinkID=159988)