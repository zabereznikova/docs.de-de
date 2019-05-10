---
title: 'Vorgehensweise: Zeichnen von vertikalem Text in einem Windows Form'
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
ms.openlocfilehash: 660d7abae5463c976e60b7d9caeae8a798d122ca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626174"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="4cca2-102">Vorgehensweise: Zeichnen von vertikalem Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="4cca2-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="4cca2-103">Im folgenden Codebeispiel wird veranschaulicht, wie Zeichnen von vertikalem Text in einem Formular mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> -Methode der <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="4cca2-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cca2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cca2-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4cca2-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4cca2-105">Compiling the Code</span></span>  
 <span data-ttu-id="4cca2-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4cca2-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="4cca2-107">Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="4cca2-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="4cca2-108">Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="4cca2-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4cca2-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4cca2-109">Robust Programming</span></span>  
 <span data-ttu-id="4cca2-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="4cca2-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="4cca2-111">Die Schriftart Arial ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="4cca2-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cca2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cca2-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="4cca2-113">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="4cca2-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4cca2-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="4cca2-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
