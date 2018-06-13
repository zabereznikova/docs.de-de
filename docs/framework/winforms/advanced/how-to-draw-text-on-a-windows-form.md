---
title: 'Gewusst wie: Zeichnen von Text in einem Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: 9369a4ed26107bdc395d455ba6fb8420fd895d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524783"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="843d6-102">Gewusst wie: Zeichnen von Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="843d6-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="843d6-103">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zum Zeichnen von Text in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="843d6-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="843d6-104">Alternativ können Sie <xref:System.Windows.Forms.TextRenderer> zum Zeichnen von Text in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="843d6-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="843d6-105">Weitere Informationen finden Sie unter [wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="843d6-105">For more information, see [How to: Draw Text with GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="843d6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="843d6-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="843d6-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="843d6-107">Compiling the Code</span></span>  
 <span data-ttu-id="843d6-108">Sie nicht aufrufen, die <xref:System.Drawing.Graphics.DrawString%2A> Methode in der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="843d6-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="843d6-109">Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="843d6-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="843d6-110">Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="843d6-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="843d6-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="843d6-111">Robust Programming</span></span>  
 <span data-ttu-id="843d6-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="843d6-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="843d6-113">Die Schriftart Arial ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="843d6-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843d6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="843d6-114">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="843d6-115">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="843d6-115">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="843d6-116">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="843d6-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
