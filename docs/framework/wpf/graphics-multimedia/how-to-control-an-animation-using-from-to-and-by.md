---
title: 'Gewusst wie: Steuern von Animationen mit From, To und By'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451784"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Gewusst wie: Steuern von Animationen mit From, To und By
Eine "from/to/by"-oder "Basic Animation"-Animation erstellt einen Übergang zwischen zwei Zielwerten (Weitere Informationen finden Sie unter [Übersicht über Animationen](animation-overview.md) ). Um die Zielwerte einer grundlegenden Animation festzulegen, verwenden Sie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  In der folgenden Tabelle wird zusammengefasst, wie die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> zusammen oder separat verwendet werden können, um die Zielwerte einer Animation zu bestimmen.  
  
|Angegebene Eigenschaften|Resultierendes Verhalten|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Die Animation verläuft von dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, mit dem Basiswert der zu animierenden Eigenschaft oder dem Ausgabewert einer vorherigen Animation, abhängig davon, wie die vorherige Animation konfiguriert wurde.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation verläuft von dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, mit dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft angegeben wird|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Die Animation wechselt von dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft angegeben wird, zu dem Wert, der durch die Summe der Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> angegeben wird.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation verläuft vom Basiswert der animierten Eigenschaft oder vom Ausgabewert einer vorherigen Animation bis zu dem Wert, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft angegeben wird.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Die Animation verläuft vom Basiswert der zu animierenden Eigenschaft oder vom Ausgabewert einer vorherigen Animation bis zur Summe dieses Werts und des Werts, der durch die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft angegeben wird.|  
  
> [!NOTE]
> Legen Sie nicht sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft als auch die <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>-Eigenschaft für die gleiche Animation fest.  
  
 Um andere Interpolationsmethoden zu verwenden oder eine Animation zwischen mehr als zwei Zielwerten auszuführen, verwenden Sie eine Keyframe-Animation. Weitere Informationen finden Sie unter [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) .  
  
 Informationen zum Anwenden mehrerer Animationen auf eine einzelne Eigenschaft finden Sie unter [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt die unterschiedlichen Auswirkungen beim Festlegen der Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>und <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> von Animationen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
