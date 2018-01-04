---
title: 'Gewusst wie: Animieren eines Doubles mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87717f6e2691142efa54a7e363f1038f8b74c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Gewusst wie: Animieren eines Doubles mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie den Wert einer Eigenschaft animieren, akzeptiert eine <xref:System.Double> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Rechteck über den Bildschirm bewegt. Im Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Klasse zu animierende der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft eine <xref:System.Windows.Media.TranslateTransform> angewendet, um eine <xref:System.Windows.Shapes.Rectangle>. In dieser sich ständig wiederholenden Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  Während der ersten drei Sekunden wird eine Instanz der dem <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> Klasse, um das Rechteck entlang eines Pfads mit konstanter Geschwindigkeit von der Startposition der 500 Position zu verschieben. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> einen smooth linearen Übergang zwischen den Werten zu erstellen.  
  
2.  Am Ende der vierten Sekunde verwendet eine Instanz der <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> Klasse, um das Rechteck plötzlich in der nächsten Position zu verschieben. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> plötzlichen Sprünge zwischen Werten. In diesem Beispiel befindet sich das Rechteck an der Startposition und wird anschließend plötzlich an der Position 500 angezeigt.  
  
3.  In den letzten zwei Sekunden verwendet eine Instanz der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> Klasse, um das Rechteck zurück an seine Anfangsposition zu verschieben. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> erzeugen einen variablen Übergang zwischen Werten entsprechend dem Wert von der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel bewegt sich das Rechteck zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Aus Gründen der Konsistenz mit anderen Animation Beispiele für die Codeversionen der in diesem Beispiel verwenden eine <xref:System.Windows.Media.Animation.Storyboard> Objekt anzuwendende der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Alternativ beim Anwenden einer Animation im Code ist es einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
