---
title: 'Gewusst wie: Animieren von Color mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344746"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Gewusst wie: Animieren von Color mithilfe von Keyframes
In diesem Beispiel wird <xref:System.Windows.Media.SolidColorBrush.Color%2A> gezeigt, wie die von a <xref:System.Windows.Media.SolidColorBrush> mithilfe von Schlüsselrahmen animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.SolidColorBrush.Color%2A> Klasse <xref:System.Windows.Media.SolidColorBrush>verwendet, um die Eigenschaft einer zu animieren. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in den ersten zwei Sekunden <xref:System.Windows.Media.Animation.LinearColorKeyFrame> eine Instanz der Klasse, um die Farbe schrittweise von grün in rot zu ändern. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearColorKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.  
  
2. Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> eine Instanz der Klasse, um die Farbe schnell von Rot in Gelb zu ändern. Diskrete Schlüsselbilder <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> wie erstellen plötzliche Änderungen zwischen Werten, d. h., die Farbänderung in diesem Teil der Animation erfolgt schnell und ist nicht subtil.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineColorKeyFrame> eine Instanz der Klasse, um die Farbe erneut zu ändern – diesmal von Gelb zurück in Grün. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineColorKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft. In diesem Beispiel beginnt die Farbveränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
