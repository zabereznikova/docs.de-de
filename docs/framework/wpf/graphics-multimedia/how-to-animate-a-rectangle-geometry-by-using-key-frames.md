---
title: 'Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344675"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes
In diesem Beispiel wird <xref:System.Windows.Media.RectangleGeometry.Rect%2A> gezeigt, <xref:System.Windows.Media.RectangleGeometry> wie die Eigenschaft eines mithilfe von Schlüsselbildern animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.RectangleGeometry.Rect%2A> Klasse <xref:System.Windows.Media.RectangleGeometry>verwendet, um die Eigenschaft einer zu animieren. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in den ersten zwei Sekunden <xref:System.Windows.Media.Animation.LinearRectKeyFrame> eine Instanz der Klasse, um eine allmähliche Änderung der Position, Breite und Höhe eines Rechtecks zu animieren. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.  
  
2. Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> eine Instanz der Klasse, um die Höhe des Rechtecks plötzlich zu verringern. Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> wie erstellen plötzliche Änderungen zwischen Werten, das heißt, die Abnahme der Höhe erfolgt schnell und ist nicht subtil.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineRectKeyFrame> eine Instanz der Klasse, um das Rechteck wieder auf seine ursprüngliche Größe und Position zu ändern. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineRectKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft. In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
