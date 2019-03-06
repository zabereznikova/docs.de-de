---
title: 'Vorgehensweise: Animieren der Breite eines Rahmens mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: b131ce444a91e518f6372b7aeac603687141b262
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360947"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Vorgehensweise: Animieren der Breite eines Rahmens mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft eine <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft eine <xref:System.Windows.Controls.Border>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Klasse, um die Stärke des Rahmens graduell zu erhöhen. Im Beispiel wird <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> um eine glatte, lineare Erhöhung zwischen Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> Klasse, um die Stärke des Rahmens abrupt zu erhöhen. Diskrete Keyframes wie diejenigen, die von abgeleiteten <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, die Verschiebung der Animation ist ruckartig.  
  
3.  In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> Klasse, um die Breite des Rahmens zu verringern. Spline-Keyframes wie jene, die von abgeleiteten <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> Eigenschaft. In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
- [Animieren eines BorderThickness-Werts](../controls/how-to-animate-a-borderthickness-value.md)
