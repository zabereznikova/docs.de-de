---
title: 'Vorgehensweise: Steuern von Animationen mit „From“, „To“ und „By“'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 812217a2905671567271687b974a435dd85cea47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930087"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Vorgehensweise: Steuern von Animationen mit „From“, „To“ und „By“
Eine "from/to/by"-oder "Basic Animation"-Animation erstellt einen Übergang zwischen zwei Zielwerten (Weitere Informationen finden Sie unter [Übersicht über Animationen](animation-overview.md) ). Um die Zielwerte einer grundlegenden Animation festzulegen, verwenden <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>Sie <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>die Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> , und.  In der folgenden Tabelle wird zusammen <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>gefasst <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, wie <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> die-,-und-Eigenschaften zusammen oder separat verwendet werden können, um die Zielwerte einer Animation zu bestimmen.  
  
|Angegebene Eigenschaften|Resultierendes Verhalten|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Die Animation wechselt von dem Wert, der von <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> der-Eigenschaft angegeben wird, zum Basiswert der zu animierenden Eigenschaft oder zum Ausgabewert einer vorherigen Animation, je nachdem, wie die vorherige Animation konfiguriert wurde.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation verläuft von dem Wert, der von <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> der-Eigenschaft angegeben wird, mit <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> dem von der-Eigenschaft angegebenen Wert.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Die Animation wechselt von dem Wert, der von <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft angegeben wird, zu dem Wert, der <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> durch die Summe der Eigenschaften und angegeben wird.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Die Animation verläuft vom Basiswert der animierten Eigenschaft oder vom Ausgabewert einer vorherigen Animation bis zu dem Wert, der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> von der-Eigenschaft angegeben wird.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Die Animation verläuft vom Basiswert der zu animierenden Eigenschaft oder vom Ausgabewert einer vorherigen Animation bis zur Summe dieses Werts und des Werts, der von <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> der-Eigenschaft angegeben wird.|  
  
> [!NOTE]
> Legen Sie nicht sowohl die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Eigenschaft als <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> auch die-Eigenschaft für die gleiche Animation fest.  
  
 Um andere Interpolationsmethoden zu verwenden oder eine Animation zwischen mehr als zwei Zielwerten auszuführen, verwenden Sie eine Keyframe-Animation. Weitere Informationen finden Sie unter [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md) .  
  
 Informationen zum Anwenden mehrerer Animationen auf eine einzelne Eigenschaft finden Sie unter [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt die unterschiedlichen Auswirkungen der <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>Einstellung <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>der Eigenschaften <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> , und für Animationen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://go.microsoft.com/fwlink/?LinkID=159988)
