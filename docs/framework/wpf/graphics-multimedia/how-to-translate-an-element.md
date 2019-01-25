---
title: 'Vorgehensweise: Übersetzen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 75b8f72647b1597396fde5d21f8378d3ce586a25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672872"
---
# <a name="how-to-translate-an-element"></a>Vorgehensweise: Übersetzen eines Elements
In diesem Beispiel wird veranschaulicht, wie übersetzt (verschoben) ein Element mit einem <xref:System.Windows.Media.TranslateTransform>.  
  
 Die <xref:System.Windows.Media.TranslateTransform> Klasse ist besonders nützlich für das Verschieben von Elementen in Bereichen, in denen keine absolute Positionierung unterstützt werden. Z. B. durch Anwenden einer <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eines Elements, verschieben Sie ein Element in eine <xref:System.Windows.Controls.StackPanel> oder <xref:System.Windows.Controls.DockPanel>.  
  
 Verwenden der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft der <xref:System.Windows.Media.TranslateTransform> , des Werts in Pixel, um das Element entlang der x-Achse verschoben werden soll. Verwenden der <xref:System.Windows.Media.TranslateTransform.Y%2A> Eigenschaft des Werts in Pixel, um das Element entlang der y-Achse verschoben werden soll. Wenden Sie schließlich die <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TranslateTransform> auf ein Element 50 Pixel nach rechts und 50 Pixel nach unten zu verschieben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
