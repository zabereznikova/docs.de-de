---
title: 'Gewusst wie: Zeichnen von Text in grafischen Elementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094552"
---
# <a name="how-to-draw-text-to-a-visual"></a>Gewusst wie: Zeichnen von Text in grafischen Elementen
Im folgenden Beispiel wird gezeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingContext>-Objekt Text in eine <xref:System.Windows.Media.DrawingVisual> zeichnen. Ein Zeichnungs Kontext wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>-Methode eines <xref:System.Windows.Media.DrawingVisual> Objekts aufgerufen wird. Sie können Grafiken und Text in einem Zeichnungs Kontext zeichnen.  
  
 Um Text in den Zeichen Kontext zu zeichnen, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawText%2A>-Methode eines <xref:System.Windows.Media.DrawingContext> Objekts. Wenn Sie mit dem Zeichnen von Inhalten in den Zeichnungs Kontext fertig sind, können Sie die <xref:System.Windows.Media.DrawingContext.Close%2A>-Methode zum Schließen des Zeichen Kontexts und zum Beibehalten des Inhalts abrufen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).
