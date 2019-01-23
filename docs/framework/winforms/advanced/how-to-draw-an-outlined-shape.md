---
title: 'Vorgehensweise: Zeichnen der Kontur eine Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 8a7bd12fb1bdab6ea429a889521b7dd6c649a5e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512592"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="3a61a-102">Vorgehensweise: Zeichnen der Kontur eine Form</span><span class="sxs-lookup"><span data-stu-id="3a61a-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="3a61a-103">In diesem Beispiel zeichnet konturierte Ellipsen und Rechtecke in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="3a61a-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a61a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a61a-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a61a-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3a61a-105">Compiling the Code</span></span>  
 <span data-ttu-id="3a61a-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3a61a-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="3a61a-107">Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="3a61a-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="3a61a-108">Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="3a61a-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3a61a-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="3a61a-109">Robust Programming</span></span>  
 <span data-ttu-id="3a61a-110">Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Pen> und <xref:System.Drawing.Graphics> Objekte.</span><span class="sxs-lookup"><span data-stu-id="3a61a-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a61a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a61a-111">See also</span></span>
- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [<span data-ttu-id="3a61a-112">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="3a61a-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3a61a-113">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="3a61a-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="3a61a-114">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a61a-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
