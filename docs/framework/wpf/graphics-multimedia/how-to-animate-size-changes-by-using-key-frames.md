---
title: 'Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344663"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes
In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.ArcSegment.Size%2A> Klasse <xref:System.Windows.Media.ArcSegment>verwendet, um die Eigenschaft einer zu animieren. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in der ersten Hälfte der Animation <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens schrittweise zu erhöhen. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.  
  
2. Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens plötzlich zu erhöhen. Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> wie plötzliche Sprünge zwischen Werten erstellen, d. h., die Größenänderungen treten plötzlich auf und sind nicht subtil.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens zu erhöhen. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft. In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
