---
title: 'Gewusst wie: Animieren in einem Stil'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: e0741a869ab81875aaa25340de851ef939e11a6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-in-a-style"></a>Gewusst wie: Animieren in einem Stil
In diesem Beispiel wird gezeigt, wie zum Animieren von Eigenschaften in einem Format festgelegt wird. Wenn Sie innerhalb eines Stils animieren, kann nur die Framework-Element, das für das die Formatvorlage definiert wird direkt angesprochen werden. Um ein freezable-Objekt als Ziel festzulegen, müssen Sie "nach unten aus einer Eigenschaft des formatierten Elements dot".  
  
 Im folgenden Beispiel werden mehrere Animationen in einem Stil definiert und angewendet eine <xref:System.Windows.Controls.Button>. Wenn der Benutzer die Maus auf die Schaltfläche richtet, es ausgeblendet wird von nicht transparenten, teilweise transparent und zurück wiederholt. Wenn der Benutzer die Maus deaktiviert die Schaltfläche richtet, wird es vollständig deckend. Wenn die Schaltfläche geklickt wird, ändert sich die Hintergrundfarbe von Orange in Weiß und wieder zurück. Da die <xref:System.Windows.Media.SolidColorBrush> verwendet, um das Paint-Ereignis der Schaltfläche kann nicht direkt angewendet werden, wird darauf über der Schaltfläche Farbgebung <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Beachten Sie, dass wenn Sie innerhalb eines Stils animieren, ist es möglich, Zielobjekte, die nicht vorhanden sind. Nehmen wir beispielsweise an, die der Stil verwendet eine <xref:System.Windows.Media.SolidColorBrush> auf eine Schaltfläche Hintergrundeigenschaft festgelegt, aber zu einem bestimmten Zeitpunkt den Stil überschrieben werden, und der Hintergrund der Schaltfläche wird festgelegt, mit einem <xref:System.Windows.Media.LinearGradientBrush>.  Versucht, die zu animierende den <xref:System.Windows.Media.SolidColorBrush> wird nicht lösen eine Ausnahme aus, die Animation fehl einfach im Hintergrund.  
  
 Weitere Informationen über Syntax zum finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Weitere Informationen zur Animation finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Weitere Informationen zu Stilen finden Sie unter der [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).
