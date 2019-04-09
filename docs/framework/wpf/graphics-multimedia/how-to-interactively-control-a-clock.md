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
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186588"
---
# <a name="how-to-interactively-control-a-clock"></a>Vorgehensweise: Interaktives Steuern einer Uhr
Ein <xref:System.Windows.Media.Animation.Clock> des Objekts <xref:System.Windows.Media.Animation.ClockController> Eigenschaft können Sie interaktiv starten, anhalten, fortsetzen, suchen, fahren fort, um die Uhr um seines Füllbereichs, und Beenden der Uhr. Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.  
  
> [!NOTE]
>  Es gibt andere Möglichkeiten, interaktiv Kontrolle-Animationen, die Sie direkt mit Uhren arbeiten benötigen nicht: Sie können auch die Storyboards. Storyboards werden in Markup und Code unterstützt. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) oder [Übersicht über Animationen](animation-overview.md).  
  
 Im folgenden Beispiel werden mehrere Schaltflächen zum eine Animationsuhr interaktiv steuern.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)
- [Übersicht über Animationen](animation-overview.md)
