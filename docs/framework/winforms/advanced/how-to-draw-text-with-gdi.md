---
title: 'Vorgehensweise: Zeichnen von Text mit GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956544"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="ad848-102">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="ad848-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="ad848-103">Mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode in <xref:System.Windows.Forms.TextRenderer> der-Klasse können Sie auf die GDI-Funktionalität zum Zeichnen von Text in einem Formular oder Steuerelement zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad848-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="ad848-104">Das GDI-Text Rendering bietet in der Regel eine bessere Leistung und eine präzisere Text Messung als GDI+.</span><span class="sxs-lookup"><span data-stu-id="ad848-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad848-105">Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden<xref:System.Windows.Forms.TextRenderer> der-Klasse werden zum Drucken nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ad848-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="ad848-106">Wenn Sie drucken, verwenden Sie <xref:System.Drawing.Graphics.DrawString%2A> immer die Methoden <xref:System.Drawing.Graphics> der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ad848-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad848-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad848-107">Example</span></span>  
 <span data-ttu-id="ad848-108">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode Text in mehreren Zeilen innerhalb eines Rechtecks zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ad848-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="ad848-109">Zum Rendering von Text mit <xref:System.Windows.Forms.TextRenderer> der-Klasse <xref:System.Drawing.IDeviceContext>benötigen Sie, <xref:System.Drawing.Font>wie z <xref:System.Drawing.Graphics> . b. und, einen Speicherort zum Zeichnen des Texts und die Farbe, in der der Text gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad848-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="ad848-110">Optional können Sie die Textformatierung mithilfe der <xref:System.Windows.Forms.TextFormatFlags> -Enumeration angeben.</span><span class="sxs-lookup"><span data-stu-id="ad848-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="ad848-111">Weitere Informationen zum Abrufen eines <xref:System.Drawing.Graphics>finden [Sie unter Gewusst wie: Erstellen Sie Grafik Objekte zum](how-to-create-graphics-objects-for-drawing.md)zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ad848-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="ad848-112">Weitere Informationen zum Erstellen eines <xref:System.Drawing.Font>finden [Sie unter Gewusst wie: Erstellen von Schriftfamilien und](how-to-construct-font-families-and-fonts.md)Schriftarten</span><span class="sxs-lookup"><span data-stu-id="ad848-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad848-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ad848-113">Compiling the Code</span></span>  
 <span data-ttu-id="ad848-114">Das vorangehende Codebeispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>ist.</span><span class="sxs-lookup"><span data-stu-id="ad848-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad848-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad848-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="ad848-116">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="ad848-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
