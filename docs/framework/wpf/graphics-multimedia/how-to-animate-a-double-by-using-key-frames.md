---
title: 'Gewusst wie: Animieren eines Doubles mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344931"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Gewusst wie: Animieren eines Doubles mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie der <xref:System.Double> Wert einer Eigenschaft animiert wird, die mithilfe von Schlüsselrahmen eine verwendet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Rechteck über den Bildschirm bewegt. Im Beispiel <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.TranslateTransform.X%2A> Klasse verwendet, um die Eigenschaft einer <xref:System.Windows.Media.TranslateTransform> auf eine <xref:System.Windows.Shapes.Rectangle>angewendeten zu animieren. In dieser sich ständig wiederholenden Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. Verwendet in den ersten drei Sekunden <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> eine Instanz der Klasse, um das Rechteck entlang eines Pfads mit einer konstanten Rate von seiner Startposition zur 500-Position zu verschieben. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.  
  
2. Verwendet am Ende der vierten Sekunde eine <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> Instanz der Klasse, um das Rechteck plötzlich an die nächste Position zu verschieben. Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> wie erstellen plötzliche Sprünge zwischen Werten. In diesem Beispiel befindet sich das Rechteck an der Startposition und wird anschließend plötzlich an der Position 500 angezeigt.  
  
3. Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> eine Instanz der Klasse, um das Rechteck wieder an seine Ausgangsposition zu verschieben. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> zwischen Werten entsprechend dem Wert der Eigenschaft. In diesem Beispiel bewegt sich das Rechteck zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Aus Gründen der Konsistenz mit anderen Animationsbeispielen <xref:System.Windows.Media.Animation.Storyboard> verwenden die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>Codeversionen dieses Beispiels ein Objekt, um die anzuwenden. Wenn Sie eine einzelne Animation im Code anwenden, <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> ist es auch <xref:System.Windows.Media.Animation.Storyboard>einfacher, die Methode anstelle einer zu verwenden. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
