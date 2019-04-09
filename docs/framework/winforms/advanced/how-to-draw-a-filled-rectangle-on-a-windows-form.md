---
title: 'Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: e551eacf0924c9bffa802fb5d2ba8bae7c1c3a98
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072026"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="4f862-102">Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f862-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="4f862-103">In diesem Beispiel zeichnet ein ausgefülltes Rechteck in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="4f862-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f862-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f862-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f862-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4f862-105">Compiling the Code</span></span>  
 <span data-ttu-id="4f862-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f862-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="4f862-107">Der gezeichnete Inhalt wird nicht neu gezeichnet werden, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="4f862-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="4f862-108">Sie sollten damit wird den Inhalt automatisch neu gezeichnet, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="4f862-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4f862-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4f862-109">Robust Programming</span></span>  
 <span data-ttu-id="4f862-110">Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics> Objekte.</span><span class="sxs-lookup"><span data-stu-id="4f862-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f862-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f862-111">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="4f862-112">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="4f862-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4f862-113">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f862-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4f862-114">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="4f862-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="4f862-115">Pinsel und gefüllte Formen in GDI+</span><span class="sxs-lookup"><span data-stu-id="4f862-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
