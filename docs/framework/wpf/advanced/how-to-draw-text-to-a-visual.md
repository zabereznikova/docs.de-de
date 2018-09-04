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
ms.openlocfilehash: bc7a4f989137ec2b021d27a6e112ff1aebd99d07
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523242"
---
# <a name="how-to-draw-text-to-a-visual"></a>Gewusst wie: Zeichnen von Text in grafischen Elementen
Das folgende Beispiel zeigt das Zeichnen von Text auf einer <xref:System.Windows.Media.DrawingVisual> mithilfe einer <xref:System.Windows.Media.DrawingContext> Objekt. Ein Zeichnungskontext wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> Methode eine <xref:System.Windows.Media.DrawingVisual> Objekt. Sie können Grafiken und Text in einen Zeichnungskontext zeichnen.  
  
 Verwenden Sie zum Zeichnen von Text in den Zeichnungskontext der <xref:System.Windows.Media.DrawingContext.DrawText%2A> Methode eine <xref:System.Windows.Media.DrawingContext> Objekt. Wenn Sie das Zeichnen von Inhalten in den Zeichnungskontext fertig sind, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A> Methode, um den Zeichnungskontext schließen und den Inhalt beizubehalten.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).
