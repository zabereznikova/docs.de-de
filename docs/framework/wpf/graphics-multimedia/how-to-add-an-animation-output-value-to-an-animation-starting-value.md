---
title: "Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a670a29e4bd982418ac92ef0e2ac65635763671
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert
In diesem Beispiel wird gezeigt, wie ein Anfangswert der Animation einen Ausgabewert der Animation hinzugefügt wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft gibt an, ob den Ausgabewert der Animation auf den Startwert (Basiswert) einer animierten Eigenschaft hinzugefügt werden soll. Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft mit dem meisten grundlegenden und die meisten Keyframes Animationen. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt die Auswirkung der Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimation> und mithilfe der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sammeln von Animationen während Wiederholungszyklen](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Animation und zeitlichen Steuerung](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
