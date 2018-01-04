---
title: 'Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f255ff38ec7ee79f02a0cd40a3f0143c36e1c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft von einem <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft eine <xref:System.Windows.Controls.Border>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde verwendet eine Instanz der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Klasse, um die Stärke des Rahmens allmählich erhöhen. Im Beispiel wird <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> einen smooth linearen Anstieg zwischen Werten zu erstellen.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> Klasse, um die Stärke des Rahmens abrupt zu erhöhen. Diskrete Keyframes wie abgeleitet <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., die Verschiebung der Animation holprig ist.  
  
3.  In den letzten zwei Sekunden verwendet eine Instanz der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> Klasse, um die Stärke eines Rahmens zu verringern. Spline-Keyframes wie abgeleitet <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> erstellen Sie einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> Eigenschaft. In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Animieren eines BorderThickness-Werts](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
