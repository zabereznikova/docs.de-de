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
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="2e7c0-102">Gewusst wie: Zeichnen von Text im Hintergrund eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2e7c0-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="2e7c0-103">Sie können Text direkt in den Hintergrund eines Steuer Elements zeichnen, indem Sie eine Text Zeichenfolge in ein <xref:System.Windows.Media.FormattedText> Objekt umrechnen und das Objekt dann in das <xref:System.Windows.Media.DrawingContext>des Steuer Elements zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2e7c0-104">Sie können dieses Verfahren auch zum Zeichnen in den Hintergrund von Objekten verwenden, die von <xref:System.Windows.Controls.Panel>abgeleitet werden, z. b. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="2e7c0-105">![Screenshot der Steuerelemente, die Text als Hintergrund anzeigen.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="2e7c0-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="2e7c0-106">Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen</span><span class="sxs-lookup"><span data-stu-id="2e7c0-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e7c0-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e7c0-107">Example</span></span>  
 <span data-ttu-id="2e7c0-108">Um auf den Hintergrund eines Steuer Elements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt, und zeichnen Sie den konvertierten Text in das <xref:System.Windows.Media.DrawingContext>des Objekts.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2e7c0-109">Weisen Sie dann die neue <xref:System.Windows.Media.DrawingBrush> der Hintergrund Eigenschaft des Steuer Elements zu.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="2e7c0-110">Im folgenden Codebeispiel wird gezeigt, wie ein <xref:System.Windows.Media.FormattedText>-Objekt erstellt und auf den Hintergrund eines <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button>-Objekts gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2e7c0-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="2e7c0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e7c0-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="2e7c0-112">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="2e7c0-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
