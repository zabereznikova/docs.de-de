---
title: 'Gewusst wie: Zeichnen von vertikalem Text in einem Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: afd09a41c46049c5a963558a709b00864fa6180f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521540"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="b0c17-102">Gewusst wie: Zeichnen von vertikalem Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="b0c17-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="b0c17-103">Im folgenden Codebeispiel wird veranschaulicht, wie Zeichnen von vertikalem Text in einem Formular mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> Methode <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="b0c17-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c17-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0c17-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0c17-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b0c17-105">Compiling the Code</span></span>  
 <span data-ttu-id="b0c17-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b0c17-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="b0c17-107">Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="b0c17-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="b0c17-108">Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b0c17-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b0c17-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b0c17-109">Robust Programming</span></span>  
 <span data-ttu-id="b0c17-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="b0c17-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b0c17-111">Die Schriftart Arial ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="b0c17-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c17-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0c17-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="b0c17-113">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="b0c17-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="b0c17-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="b0c17-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
