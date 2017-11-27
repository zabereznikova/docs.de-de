---
title: "Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dce1a8d1070ed1d016da0c94c1f3ecc1ed9df389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="6bd13-102">Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bd13-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="6bd13-103">Dieses Beispiel zeichnet ein ausgefülltes Rechteck in einem Formular an.</span><span class="sxs-lookup"><span data-stu-id="6bd13-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bd13-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bd13-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6bd13-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6bd13-105">Compiling the Code</span></span>  
 <span data-ttu-id="6bd13-106">Sie können diese Methode nicht aufrufen, der <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6bd13-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="6bd13-107">Der gezeichnete Inhalt wird nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.</span><span class="sxs-lookup"><span data-stu-id="6bd13-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="6bd13-108">Damit der Inhalt automatisch neu gezeichnet werden soll, sollten Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="6bd13-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6bd13-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6bd13-109">Robust Programming</span></span>  
 <span data-ttu-id="6bd13-110">Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics> Objekte.</span><span class="sxs-lookup"><span data-stu-id="6bd13-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd13-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bd13-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.FillRectangle%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="6bd13-112">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="6bd13-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="6bd13-113">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bd13-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="6bd13-114">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="6bd13-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="6bd13-115">Pinsel und gefüllte Formen in GDI+</span><span class="sxs-lookup"><span data-stu-id="6bd13-115">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
