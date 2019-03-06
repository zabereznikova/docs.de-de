---
title: 'Vorgehensweise: Steuern von Animationen mit From, To und By'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 35973a2a3dea233468f91c6bd24851be088b84e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373841"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Vorgehensweise: Steuern von Animationen mit From, To und By
"From/To/By" oder "grundlegende Animation" erstellt einen Übergang zwischen zwei Zielwerten (finden Sie unter [Übersicht über Animationen](animation-overview.md) eine Einführung in die verschiedenen Arten von Animationen). Verwenden Sie zum Festlegen der Zielwerte einer grundlegenden Animation die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.  Die folgende Tabelle enthält die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften können zusammen verwendet werden oder separat um die Zielwerte einer Animation zu bestimmen.  
  
|Angegebene Eigenschaften|Resultierendes Verhalten|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Der Animation erfolgt ab dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft mit dem Basiswert der animierten Eigenschaft oder einer vorherigen Animation Ausgabewert, je nach die vorherige Animation Konfiguration.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Der Animation erfolgt ab dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft angegebene Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Der Animation erfolgt ab dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft auf den durch die Summe der angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaften.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Durchlaufen Sie die Animation vom Basiswert der animierten Eigenschaft oder die Ausgabe einer vorherigen Animation Wert, der dem angegebenen Wert der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Ausgabe der Animation erfolgt ab dem Basiswert der animierten Eigenschaft oder einer vorherigen Animation Wert die Summe dieses Werts und der Wert von der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft.|  
  
> [!NOTE]
>  Legen Sie nicht sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft und die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Eigenschaft in derselben Animation.  
  
 Um andere Interpolationsmethoden zu verwenden oder eine Animation zwischen mehr als zwei Zielwerten auszuführen, verwenden Sie eine Keyframe-Animation. Finden Sie unter [Übersicht über Keyframe Animationen](key-frame-animations-overview.md) für Weitere Informationen.  
  
 Informationen zum Anwenden mehrerer Animationen auf eine einzelne Eigenschaft finden Sie unter [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt die verschiedenen Auswirkungen der Einstellung <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, und <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaften für Animationen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://go.microsoft.com/fwlink/?LinkID=159988)
