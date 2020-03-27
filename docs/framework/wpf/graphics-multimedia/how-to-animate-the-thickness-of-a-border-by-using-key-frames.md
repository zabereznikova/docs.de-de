---
title: 'Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344691"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes
Dieses Beispiel zeigt, <xref:System.Windows.Controls.Control.BorderThickness%2A> wie die <xref:System.Windows.Controls.Border>Eigenschaft einer animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> wird die <xref:System.Windows.Controls.Control.BorderThickness%2A> Klasse <xref:System.Windows.Controls.Border>verwendet, um die Eigenschaft einer zu animieren. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in der ersten Hälfte der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Sekunde eine Instanz der Klasse, um die Dicke der Grenze schrittweise zu erhöhen. Im Beispiel <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> wird eine glatte lineare Erhöhung zwischen Werten erstellt.  
  
2. Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> eine Instanz der Klasse, um plötzlich die Dicke der Grenze zu erhöhen. Diskrete Schlüsselbilder, wie <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> sie von plötzlichen Sprüngen zwischen Werten abgeleitet werden, d. h. die Bewegung der Animation ist ruckartig.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> eine Instanz der Klasse, um die Dicke des Rahmens zu verringern. Spline-Schlüsselrahmen, wie <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> sie von abgeleitet werden, erstellen <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> einen Variablenübergang zwischen Werten entsprechend den Werten der Eigenschaft. In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
- [Animieren eines BorderThickness-Werts](../controls/how-to-animate-a-borderthickness-value.md)
