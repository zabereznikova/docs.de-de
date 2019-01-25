---
title: 'Vorgehensweise: Zeichnen von Text auf ein Steuerelement&#39;im Hintergrund'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: d580330de5ef3841979fffc61db336064f1643f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740418"
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>Vorgehensweise: Zeichnen von Text auf ein Steuerelement&#39;im Hintergrund
Sie können Text direkt in den Hintergrund eines Steuerelements zeichnen, indem konvertiert eine Textzeichenfolge mit einer <xref:System.Windows.Media.FormattedText> Objekt aus, und klicken Sie dann das Objekt des Steuerelements gezeichnet <xref:System.Windows.Media.DrawingContext>. Sie können dieses Verfahren auch verwenden, für das Zeichnen in den Hintergrund von Objekten abgeleitet <xref:System.Windows.Controls.Panel>, z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.  
  
 ![Steuerelemente zur Anzeige von Text als Hintergrund](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen  
  
## <a name="example"></a>Beispiel  
 Um auf den Hintergrund eines Steuerelements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt aus, und zeichnen Sie den konvertierten Text des Objekts <xref:System.Windows.Media.DrawingContext>. Weisen Sie anschließend auf die neue <xref:System.Windows.Media.DrawingBrush> Hintergrundeigenschaft des Steuerelements.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt aus, und zeichnen Sie auf den Hintergrund von einem <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button> Objekt.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.FormattedText>
- [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
