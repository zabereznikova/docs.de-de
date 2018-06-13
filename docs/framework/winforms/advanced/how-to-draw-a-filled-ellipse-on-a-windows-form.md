---
title: 'Gewusst wie: Zeichnen einer ausgefüllten Ellipse in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: b892670031e795ecd27b194cdf2cf818f4af6254
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521432"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="ca81d-102">Gewusst wie: Zeichnen einer ausgefüllten Ellipse in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca81d-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="ca81d-103">Dieses Beispiel zeichnet eine ausgefüllte Ellipse in einem Formular an.</span><span class="sxs-lookup"><span data-stu-id="ca81d-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca81d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca81d-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca81d-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ca81d-105">Compiling the Code</span></span>  
 <span data-ttu-id="ca81d-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="ca81d-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="ca81d-107">Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="ca81d-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="ca81d-108">Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ca81d-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ca81d-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ca81d-109">Robust Programming</span></span>  
 <span data-ttu-id="ca81d-110">Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ca81d-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca81d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca81d-111">See Also</span></span>  
 [<span data-ttu-id="ca81d-112">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca81d-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="ca81d-113">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="ca81d-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="ca81d-114">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="ca81d-114">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="ca81d-115">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="ca81d-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
