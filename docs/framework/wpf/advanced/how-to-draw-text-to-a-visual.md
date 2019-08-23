---
title: 'Vorgehensweise: Zeichnen von Text in grafischen Elementen'
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
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963849"
---
# <a name="how-to-draw-text-to-a-visual"></a>Vorgehensweise: Zeichnen von Text in grafischen Elementen
Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines <xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingContext> -Objekts Text in einen zeichnen können. Ein Zeichnungs Kontext wird zurückgegeben, indem <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> die-Methode <xref:System.Windows.Media.DrawingVisual> eines-Objekts aufgerufen wird. Sie können Grafiken und Text in einem Zeichnungs Kontext zeichnen.  
  
 Um Text in den Zeichen Kontext zu zeichnen, verwenden <xref:System.Windows.Media.DrawingContext.DrawText%2A> Sie die- <xref:System.Windows.Media.DrawingContext> Methode eines-Objekts. Wenn Sie mit dem Zeichnen von Inhalten in den Zeichen Kontext fertig sind <xref:System.Windows.Media.DrawingContext.Close%2A> , müssen Sie die-Methode zum Schließen des Zeichen Kontexts und zum Speichern des Inhalts abrufen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).
