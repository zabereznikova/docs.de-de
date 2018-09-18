---
title: 'Gewusst wie: Animieren in einem Stil (WPF)'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: a455bbfb9defbcf83f7e490f60031917a3b41779
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46005647"
---
# <a name="how-to-animate-in-a-style"></a>Gewusst wie: Animieren in einem Stil

Dieses Beispiel zeigt, wie zum Animieren von Eigenschaften innerhalb eines Stils. Wenn Sie innerhalb eines Stils zu animieren, kann nur die FrameworkElement, das für das der Stil definiert wird direkt vorgesehen. Um einem freezable-Objekts als Ziel festzulegen, müssen Sie "nach unten aus einer Eigenschaft des formatierten Elements dot".

Im folgenden Beispiel sind mehrere Animationen in einem Stil definiert und angewendet werden, um eine <xref:System.Windows.Controls.Button>. Wenn der Benutzer die Maus über die Schaltfläche bewegt werden, es wird von nicht transparenten teilweise transparent und zurück wiederholt. Wenn der Benutzer die Maus der Schaltfläche weg bewegt, wird es vollständig deckend. Wenn die Schaltfläche geklickt wird, ändert sich die Hintergrundfarbe von Orange in Weiß und wieder ein. Da die <xref:System.Windows.Media.SolidColorBrush> zum Zeichnen die Schaltfläche kann nicht direkt angewendet werden, erfolgt von der Schaltfläche Farbgebung <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.

## <a name="example"></a>Beispiel

[!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Beachten Sie, dass beim Animieren in einem Stil möglich, Zielobjekte, die nicht vorhanden. Nehmen wir beispielsweise an, der Stil verwendet eine <xref:System.Windows.Media.SolidColorBrush> auf eine Schaltfläche der Background-Eigenschaft festgelegt, aber zu einem bestimmten Zeitpunkt das Format überschrieben werden, und der Hintergrund der Schaltfläche festgelegt ist, mit einem <xref:System.Windows.Media.LinearGradientBrush>.  Animieren möchten die <xref:System.Windows.Media.SolidColorBrush> wird nicht löst eine Ausnahme, die Animation einfach im Hintergrund fehl.

Weitere Informationen über Syntax zum finden Sie unter den [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Weitere Informationen zur Animation finden Sie unter den [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Weitere Informationen zu Stilen finden Sie unter den [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).
