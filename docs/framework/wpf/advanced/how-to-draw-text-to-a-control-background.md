---
title: 'Gewusst wie: Zeichnen von Text im Hintergrund eines Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424364"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>Gewusst wie: Zeichnen von Text im Hintergrund eines Steuerelements
Sie können Text direkt in den Hintergrund eines Steuer Elements zeichnen, indem Sie eine Text Zeichenfolge in ein <xref:System.Windows.Media.FormattedText> Objekt umrechnen und das Objekt dann in das <xref:System.Windows.Media.DrawingContext>des Steuer Elements zeichnen. Sie können dieses Verfahren auch zum Zeichnen in den Hintergrund von Objekten verwenden, die von <xref:System.Windows.Controls.Panel>abgeleitet werden, z. b. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.  
  
 ![Screenshot der Steuerelemente, die Text als Hintergrund anzeigen.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen  
  
## <a name="example"></a>Beispiel  
 Um auf den Hintergrund eines Steuer Elements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt, und zeichnen Sie den konvertierten Text in das <xref:System.Windows.Media.DrawingContext>des Objekts. Weisen Sie dann die neue <xref:System.Windows.Media.DrawingBrush> der Hintergrund Eigenschaft des Steuer Elements zu.  
  
 Im folgenden Codebeispiel wird gezeigt, wie ein <xref:System.Windows.Media.FormattedText>-Objekt erstellt und auf den Hintergrund eines <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button>-Objekts gezeichnet wird.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.FormattedText>
- [Zeichnen von formatiertem Text](drawing-formatted-text.md)
