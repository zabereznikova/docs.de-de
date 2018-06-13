---
title: 'Gewusst wie: Interaktives Steuern einer Uhr'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 63e72c48afd9b72a6b334ccdc234d08cef7288f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560223"
---
# <a name="how-to-interactively-control-a-clock"></a>Gewusst wie: Interaktives Steuern einer Uhr
Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, seek, setzen die Uhr auf den Füllzeitraum, und beenden die Uhr. Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.  
  
> [!NOTE]
>  Es gibt andere Möglichkeiten, interaktiv Steuerelement-Animationen, die Sie direkt mit Uhren arbeiten erfordern: Sie können auch die Storyboards. Storyboards sind im Markup und Code unterstützt. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
