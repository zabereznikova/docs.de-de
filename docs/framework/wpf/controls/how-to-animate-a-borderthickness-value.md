---
title: 'Gewusst wie: Animieren eines BorderThickness-Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124662"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Gewusst wie: Animieren eines BorderThickness-Werts
In diesem Beispiel wird gezeigt, wie Änderungen an der Breite eines Rahmens mithilfe der <xref:System.Windows.Media.Animation.ThicknessAnimation>-Klasse animiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Breite eines Rahmens mithilfe von <xref:System.Windows.Media.Animation.ThicknessAnimation>animiert. Im Beispiel wird die <xref:System.Windows.Controls.Border.BorderThickness%2A>-Eigenschaft von <xref:System.Windows.Controls.Border>verwendet.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Das komplette Beispiel finden Sie unter [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Gewusst-wie-Themen zu Animation und zeitliche Steuerung](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Animieren der Breite eines Rahmens mithilfe von Keyframes](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
