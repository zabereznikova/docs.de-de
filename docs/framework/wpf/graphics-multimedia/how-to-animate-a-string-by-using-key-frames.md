---
title: 'Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1692777a97754fb7f6481b2d9cb8942dcb62df77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie eine Zeichenfolge animiert in diesem Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft von einem <xref:System.Windows.Controls.Button> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.  
  
 Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> Klasse, da eine Zeichenfolge mit Keyframes erstellte Animation nur diskrete Keyframes verwenden kann. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., Änderungen an der Animation schnell ausgeführt und sind nicht feine.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
