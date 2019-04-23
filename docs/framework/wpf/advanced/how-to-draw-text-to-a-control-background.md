---
title: 'Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 76449c88f9a720741c8ed61255e04a40e6a8613f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128452"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="0c853-102">Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="0c853-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="0c853-103">Sie können Text direkt in den Hintergrund eines Steuerelements zeichnen, indem konvertiert eine Textzeichenfolge mit einer <xref:System.Windows.Media.FormattedText> Objekt aus, und klicken Sie dann das Objekt des Steuerelements gezeichnet <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="0c853-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="0c853-104">Sie können dieses Verfahren auch verwenden, für das Zeichnen in den Hintergrund von Objekten abgeleitet <xref:System.Windows.Controls.Panel>, z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="0c853-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="0c853-105">![Steuerelemente zur Anzeige von Text als Hintergrund](./media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="0c853-105">![Controls displaying text as background](./media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="0c853-106">Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen</span><span class="sxs-lookup"><span data-stu-id="0c853-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c853-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c853-107">Example</span></span>  
 <span data-ttu-id="0c853-108">Um auf den Hintergrund eines Steuerelements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt aus, und zeichnen Sie den konvertierten Text des Objekts <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="0c853-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="0c853-109">Weisen Sie anschließend auf die neue <xref:System.Windows.Media.DrawingBrush> Hintergrundeigenschaft des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="0c853-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="0c853-110">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt aus, und zeichnen Sie auf den Hintergrund von einem <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0c853-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c853-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c853-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="0c853-112">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="0c853-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
