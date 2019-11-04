---
title: Animieren in einem Stil (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 617d41ca1c97463bf1c61c0d1e2728756fd8f1fb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459242"
---
# <a name="how-to-animate-in-a-style"></a>Animieren in einem Stil

Dieses Beispiel zeigt, wie Eigenschaften innerhalb eines Stils animiert werden. Bei der Animation innerhalb eines Stils kann nur das Framework-Element, für das der Stil definiert ist, direkt als Ziel festgelegt werden. Um ein frei wählbares Objekt als Ziel festzulegen, müssen Sie einen "punktdown" von einer Eigenschaft des formatierten Elements durchsetzen.

Im folgenden Beispiel werden mehrere Animationen innerhalb eines Stils definiert und auf eine <xref:System.Windows.Controls.Button>angewendet. Wenn der Benutzer den Mauszeiger über die Schaltfläche bewegt, wird er wiederholt von der nicht transparenten zur teilweise durchlässigen und wieder zurückgeführt. Wenn der Benutzer den Mauszeiger aus der Schaltfläche bewegt, wird er vollständig nicht transparent. Wenn auf die Schaltfläche geklickt wird, ändert sich die Hintergrundfarbe von Orange in weiß und wieder zurück. Da der <xref:System.Windows.Media.SolidColorBrush>, der zum Zeichnen der Schaltfläche verwendet wird, nicht direkt als Ziel festgelegt werden kann, erfolgt der Zugriff darauf, indem er die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft der Schaltfläche

## <a name="example"></a>Beispiel

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Beachten Sie, dass es bei der Animation innerhalb eines Stils möglich ist, Objekte zu erstellen, die nicht vorhanden sind. Angenommen, Ihr Stil verwendet einen <xref:System.Windows.Media.SolidColorBrush>, um die Background-Eigenschaft einer Schaltfläche festzulegen, aber an einem bestimmten Punkt wird der Stil überschrieben, und der Hintergrund der Schaltfläche wird mit einem <xref:System.Windows.Media.LinearGradientBrush>festgelegt.  Der Versuch, den <xref:System.Windows.Media.SolidColorBrush> zu animieren, löst keine Ausnahme aus. die Animation führt einfach im Hintergrund zu einem Fehler.

Weitere Informationen zur Syntax der Storyboard-Zielplattform finden Sie in der [Übersicht über Storyboards](storyboards-overview.md). Weitere Informationen zur Animation finden Sie unter [Übersicht über Animationen](animation-overview.md). Weitere Informationen zu Stilen finden Sie unter [formatieren und](../../../desktop-wpf/fundamentals/styles-templates-overview.md)Vorlagen.
