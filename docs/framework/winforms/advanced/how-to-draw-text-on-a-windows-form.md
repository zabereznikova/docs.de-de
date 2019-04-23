---
title: 'Vorgehensweise: Zeichnen von Text in einem Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ae7749deedba03f0a63bb74099d071d5da4fe27e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172977"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="b866a-102">Vorgehensweise: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="b866a-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="b866a-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zum Zeichnen von Text in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="b866a-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="b866a-104">Alternativ können Sie <xref:System.Windows.Forms.TextRenderer> zum Zeichnen von Text in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="b866a-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="b866a-105">Weitere Informationen finden Sie unter [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="b866a-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b866a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b866a-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b866a-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b866a-107">Compiling the Code</span></span>  
 <span data-ttu-id="b866a-108">Sie können nicht aufgerufen werden die <xref:System.Drawing.Graphics.DrawString%2A> -Methode in der die <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b866a-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="b866a-109">Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="b866a-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="b866a-110">Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b866a-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b866a-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b866a-111">Robust Programming</span></span>  
 <span data-ttu-id="b866a-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b866a-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b866a-113">Die Schriftart Arial ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="b866a-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b866a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b866a-114">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="b866a-115">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="b866a-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b866a-116">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="b866a-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
