---
title: "Gewusst wie: Zeichnen einer mit einer Textur ausgefüllten Linie"
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
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aaba7981dc68bf7bdfe6dbd45685e61f7b763a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="2d863-102">Gewusst wie: Zeichnen einer mit einer Textur ausgefüllten Linie</span><span class="sxs-lookup"><span data-stu-id="2d863-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="2d863-103">Statt eine Linie mit einer Volltonfarbe, können Sie eine Zeile mit einer Textur zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2d863-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="2d863-104">Zum Zeichnen von Linien und Kurven mit einer Textur erstellen Sie eine <xref:System.Drawing.TextureBrush> Objekts, und übergeben, die <xref:System.Drawing.TextureBrush> -Objekt an eine <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="2d863-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="2d863-105">Wenn der Stift eine Linie oder Kurve zeichnet, überdeckt die Strichbreite des Stifts bestimmte Pixel gekachelt, und die Bitmap der Texturpinsel zugeordneten wird verwendet, um die Ebene (unsichtbar) Kachel.</span><span class="sxs-lookup"><span data-stu-id="2d863-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d863-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d863-106">Example</span></span>  
 <span data-ttu-id="2d863-107">Das folgende Beispiel erstellt eine <xref:System.Drawing.Bitmap> Objekt aus der Datei `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="2d863-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="2d863-108">Dieser Bitmap dient zum Erstellen einer <xref:System.Drawing.TextureBrush> -Objekt, und die <xref:System.Drawing.TextureBrush> Objekt dient zum Erstellen einer <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="2d863-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="2d863-109">Der Aufruf von <xref:System.Drawing.Graphics.DrawImage%2A> zeichnet die Bitmap mit der linken oberen Ecke an (0, 0).</span><span class="sxs-lookup"><span data-stu-id="2d863-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="2d863-110">Der Aufruf von <xref:System.Drawing.Graphics.DrawEllipse%2A> verwendet die <xref:System.Drawing.Pen> Objekt zum Zeichnen einer texturierten Ellipse.</span><span class="sxs-lookup"><span data-stu-id="2d863-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="2d863-111">Die folgende Abbildung zeigt die Bitmap und der texturierten Ellipse.</span><span class="sxs-lookup"><span data-stu-id="2d863-111">The following illustration shows the bitmap and the textured ellipse.</span></span>  
  
 <span data-ttu-id="2d863-112">![Stifte](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span><span class="sxs-lookup"><span data-stu-id="2d863-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d863-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2d863-113">Compiling the Code</span></span>  
 <span data-ttu-id="2d863-114">Erstellen eines Windows Form, und behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2d863-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="2d863-115">Fügen Sie den vorangehenden Code in der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="2d863-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2d863-116">Ersetzen Sie `Texture.jpg` mit einem Bild auf Ihrem System ungültig.</span><span class="sxs-lookup"><span data-stu-id="2d863-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d863-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d863-117">See Also</span></span>  
 [<span data-ttu-id="2d863-118">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="2d863-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="2d863-119">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d863-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
