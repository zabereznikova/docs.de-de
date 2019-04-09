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
ms.openlocfilehash: eb00928205a318b068d49ea3f6f71c398f77bbcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072492"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="9c45a-102">Vorgehensweise: Zeichnen von vertikalem Text in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="9c45a-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="9c45a-103">Im folgenden Codebeispiel wird veranschaulicht, wie Zeichnen von vertikalem Text in einem Formular mithilfe der <xref:System.Drawing.Graphics.DrawString%2A> -Methode der <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="9c45a-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c45a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c45a-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c45a-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9c45a-105">Compiling the Code</span></span>  
 <span data-ttu-id="9c45a-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9c45a-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="9c45a-107">Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="9c45a-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="9c45a-108">Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="9c45a-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9c45a-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="9c45a-109">Robust Programming</span></span>  
 <span data-ttu-id="9c45a-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="9c45a-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9c45a-111">Die Schriftart Arial ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="9c45a-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c45a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c45a-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="9c45a-113">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="9c45a-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="9c45a-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="9c45a-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
