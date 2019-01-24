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
ms.openlocfilehash: 93c2d754ec899c96a50fef3dcef680434f564276
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657544"
---
# <a name="how-to-interactively-control-a-clock"></a>Vorgehensweise: Interaktives Steuern einer Uhr
Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, suchen, fahren fort, um die Uhr um seines Füllbereichs, und Beenden der Uhr. Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.  
  
> [!NOTE]
>  Es gibt andere Möglichkeiten, interaktiv Kontrolle-Animationen, die Sie direkt mit Uhren arbeiten benötigen nicht: Sie können auch die Storyboards. Storyboards werden in Markup und Code unterstützt. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Siehe auch
- [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
