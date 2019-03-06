---
title: 'Vorgehensweise: Formatieren von "UIElement" als transparent oder halbtransparent'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370526"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Vorgehensweise: Formatieren von "UIElement" als transparent oder halbtransparent
Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.UIElement> transparent oder halbtransparent. Ein Element transparent oder halbtransparent Sie legen fest, um die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Der Wert `0.0` Blendet das Element völlig transparent, während ein Wert von `1.0` Blendet das Element nicht vollständig transparent. Der Wert `0.5` Blendet das Element 50 % undurchsichtig usw. Eines Elements <xref:System.Windows.UIElement.Opacity%2A> nastaven NA hodnotu `1.0` standardmäßig.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Opacity%2A> einer Schaltfläche auf `0.25`, dass die Schaltfläche und seinen Inhalt (in diesem Fall wird der Text der Schaltfläche) mit 25 % nicht transparent.  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Wenn Inhalt des Elements eine eigene haben <xref:System.Windows.UIElement.Opacity%2A> Einstellungen, die diese Werte werden auf die die enthaltende Elemente multipliziert <xref:System.Windows.UIElement.Opacity%2A>.  
  
 Im folgenden Beispiel wird einer Schaltfläche <xref:System.Windows.UIElement.Opacity%2A> zu `0.25`, und die <xref:System.Windows.UIElement.Opacity%2A> von einer <xref:System.Windows.Controls.Image> Steuerelement die Schaltfläche, um mit im `0.5`. Daher wird das Bild 12,5 % deckend angezeigt: 0.25 * 0.5 = 0.125.  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Eine weitere Möglichkeit zum Steuern der Durchlässigkeit eines Elements die Durchlässigkeit des festzulegen ist die <xref:System.Windows.Media.Brush> ab, der das Element zeichnet. Dieser Ansatz ermöglicht es Ihnen, selektiv Änderungen an der Durchlässigkeit von Teilen eines Elements und bietet Leistungsvorteile gegenüber der Verwendung des Elements <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A> von einer <xref:System.Windows.Media.SolidColorBrush> zum Zeichnen der Schaltfläche verwendet <xref:System.Windows.Controls.Control.Background%2A> nastaven NA hodnotu `0.25`. Daher Hintergrund des Pinsels ist 25 % undurchsichtig ist, dessen Inhalt (der Text der Schaltfläche) bleiben jedoch 100 % ige Deckkraft steht.  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 Sie können auch die Deckkraft einzelner Farben, innerhalb eines Pinsels steuern. Weitere Informationen zu Farben und Pinsel finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Ein Beispiel, das zeigt, wie die Durchlässigkeit eines Elements zu animieren, finden Sie unter [Animieren der Durchlässigkeit eines Elements oder eines Pinsels](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
