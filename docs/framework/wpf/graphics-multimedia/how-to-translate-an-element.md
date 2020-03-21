---
title: 'Gewusst wie: Übersetzen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111971"
---
# <a name="how-to-translate-an-element"></a>Gewusst wie: Übersetzen eines Elements
Dieses Beispiel zeigt, wie ein Element mithilfe <xref:System.Windows.Media.TranslateTransform>einer übersetzt (verschiebt) wird.  
  
 Die <xref:System.Windows.Media.TranslateTransform> Klasse ist besonders nützlich für das Verschieben von Elementen innerhalb von Panels, die keine absolute Positionierung unterstützen. Wenn Sie z. <xref:System.Windows.Media.TranslateTransform> B. eine auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eines <xref:System.Windows.Controls.StackPanel> Elements <xref:System.Windows.Controls.DockPanel>anwenden, können Sie ein Element innerhalb eines oder verschieben.  
  
 Verwenden <xref:System.Windows.Media.TranslateTransform.X%2A> Sie die <xref:System.Windows.Media.TranslateTransform> Eigenschaft des, um den Betrag in Pixel anzugeben, um das Element entlang der x-Achse zu verschieben. Verwenden <xref:System.Windows.Media.TranslateTransform.Y%2A> Sie die Eigenschaft, um den Betrag in Pixel anzugeben, um das Element entlang der y-Achse zu verschieben. Wenden Sie <xref:System.Windows.Media.TranslateTransform> schließlich <xref:System.Windows.UIElement.RenderTransform%2A> die auf die Eigenschaft des Elements an.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.TranslateTransform> wird ein verwendet, um ein Element 50 Pixel nach rechts und 50 Pixel nach unten zu verschieben.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Transformationen](transforms-overview.md)
