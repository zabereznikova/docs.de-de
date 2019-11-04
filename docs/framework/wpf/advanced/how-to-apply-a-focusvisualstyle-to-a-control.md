---
title: 'Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459810"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement
In diesem Beispiel wird gezeigt, wie Sie einen visuellen Fokus Stil in Ressourcen erstellen und den Stil auf ein Steuerelement anwenden, indem Sie die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>-Eigenschaft verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Stil definiert, mit dem zusätzliche Steuerelement Zusammensetzung erstellt werden, die nur angewendet wird, wenn sich das Steuerelement in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]auf die Tastatur konzentriert Dies wird erreicht, indem ein Stil mit einem <xref:System.Windows.Controls.ControlTemplate>definiert und dann beim Festlegen der Eigenschaft <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> als Ressource referenziert wird.  
  
 Ein externes Rechteck, das einem Rahmen ähnelt, wird außerhalb des rechteckigen Bereichs platziert. Sofern nicht anders geändert, verwendet die Größe des Stils die <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen Steuer Elements, auf das der visuelle Fokus Stil angewendet wird. In diesem Beispiel werden negative Werte für das <xref:System.Windows.FrameworkElement.Margin%2A> festgelegt, damit der Rahmen leicht außerhalb des Steuer Elements angezeigt wird.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> ist ein Additiv zu einem Steuerelement Vorlagen Stil, der entweder aus einem expliziten Stil oder einem Design Stil stammt. der primäre Stil für ein Steuerelement kann weiterhin mithilfe eines <xref:System.Windows.Controls.ControlTemplate> erstellt und dieser Stil auf die <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft festgelegt werden.  
  
 Visuelle Fokus Stile sollten konsistent für ein Design oder eine Benutzeroberfläche verwendet werden, anstatt für jedes Fokussier Bare Element einen anderen zu verwenden. Weitere Informationen finden Sie unter Formatieren [für den Fokus in Steuerelementen und Focus VisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Fokusstile in Steuerelementen und FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
