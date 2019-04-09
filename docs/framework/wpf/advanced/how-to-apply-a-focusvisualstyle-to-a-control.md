---
title: 'Vorgehensweise: Anwenden eines FocusVisualStyle auf ein Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133548"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Vorgehensweise: Anwenden eines FocusVisualStyle auf ein Steuerelement
Dieses Beispiel zeigt Ihnen das Erstellen eines visuellen Fokusstils in Ressourcen und Anwenden der Formatvorlage auf ein Steuerelement, mit der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert ein Format, das zusätzliche Zusammensetzung von Steuerelementen, die nur gültig, wenn das Steuerelement mit Fokus im Tastatur wird die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Dies erfolgt durch die Definition eines Stils mit einem <xref:System.Windows.Controls.ControlTemplate>, und klicken Sie dann diesen Stil als eine Ressource verweisen, beim Festlegen der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
 Ein externes Rechteck, einem Rahmen ähnelt befindet sich außerhalb des rechteckigen Bereichs. Es sei denn, die andernfalls geändert wird, verwendet die Größe des Formats der <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen-Steuerelements, in dem der visuelle Fokusstil angewendet wird. In diesem Beispiel wird die negative Werte für die <xref:System.Windows.FrameworkElement.Margin%2A> zu der Rahmen etwas außerhalb das Steuerelement mit Fokus dargestellt.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> wird auf alle Steuerelement-Vorlage-Format, das ist additiv expliziter Stil oder einem Designstil der primäre Stil für ein Steuerelement kann immer noch mit erstellt werden ein <xref:System.Windows.Controls.ControlTemplate> und diesen Stil auf die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft.  
  
 Fokus visuelle Stile konsistent werden, über ein Thema oder eine Benutzeroberfläche verwendet sollten, anstatt einen anderen Wert für jedes Element den Fokus erhalten kann. Weitere Informationen finden Sie unter [Fokusstile in Steuerelementen und FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Fokusstile in Steuerelementen und FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
