---
title: 'Gewusst wie: Interaktives Steuern einer Uhr'
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
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: debe65ef1587171dc2f324a19da4b43e7274c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
