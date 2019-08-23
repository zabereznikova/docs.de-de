---
title: 'Vorgehensweise: Interaktives Steuern einer Uhr'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951337"
---
# <a name="how-to-interactively-control-a-clock"></a>Vorgehensweise: Interaktives Steuern einer Uhr
Mit <xref:System.Windows.Media.Animation.Clock> der- <xref:System.Windows.Media.Animation.ClockController> Eigenschaft eines-Objekts können Sie die Uhr interaktiv starten, anhalten, fortsetzen, suchen, die Uhr bis zum Füllzeitraum verschieben und die Uhr anhalten. Nur die Stammuhr einer Zeit Steuerungsstruktur kann interaktiv gesteuert werden.  
  
> [!NOTE]
> Es gibt weitere Möglichkeiten, Animationen interaktiv zu steuern, die nicht direkt mit Uhren arbeiten müssen: Sie können auch Storyboards verwenden. Storyboards werden sowohl in Markup als auch im Code unterstützt. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft mithilfe eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) oder der [Übersicht über Animationen](animation-overview.md).  
  
 Im folgenden Beispiel werden mehrere Schaltflächen verwendet, um eine Animations Uhr interaktiv zu steuern.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)
- [Übersicht über Animationen](animation-overview.md)
