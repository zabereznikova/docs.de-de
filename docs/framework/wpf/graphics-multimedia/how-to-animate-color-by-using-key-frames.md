---
title: 'Vorgehensweise: Animieren von Color mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8d7dbe70f25b4712d1384a751a02053fb7f287ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645092"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Vorgehensweise: Animieren von Color mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft eine <xref:System.Windows.Media.SolidColorBrush>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In den ersten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearColorKeyFrame> Klasse, um die Farbe allmählich von Grün zu Rot zu ändern. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearColorKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> Klasse, um die Farbe schnell von Rot über Gelb zu ändern. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> abrupte Veränderungen zwischen Werten, d. h. erstellen, die farbveränderung in diesem Teil der Animation tritt schnell auf und ist.  
  
3.  In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineColorKeyFrame> Klasse, um die Farbe erneut zu ändern – in diesem Fall von Gelb zu Grün. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineColorKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel beginnt die Farbveränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
