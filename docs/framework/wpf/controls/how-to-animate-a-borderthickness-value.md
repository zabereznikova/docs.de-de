---
title: 'Vorgehensweise: Animieren eines BorderThickness-Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4f38895f58e1a41a8a66b31a116e94f5b02492f7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368937"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Vorgehensweise: Animieren eines BorderThickness-Werts
In diesem Beispiel wird gezeigt, wie zum Animieren von Änderungen an die Stärke eines Rahmens mithilfe der <xref:System.Windows.Media.Animation.ThicknessAnimation> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Animation die Stärke eines Rahmens mithilfe von <xref:System.Windows.Media.Animation.ThicknessAnimation>. Im Beispiel wird die <xref:System.Windows.Controls.Border.BorderThickness%2A> Eigenschaft <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Animieren der Breite eines Rahmens mithilfe von Keyframes](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
