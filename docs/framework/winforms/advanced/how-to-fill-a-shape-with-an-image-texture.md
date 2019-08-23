---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Bildstruktur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911688"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="a42cc-102">Vorgehensweise: Ausfüllen einer Form mit einer Bildstruktur</span><span class="sxs-lookup"><span data-stu-id="a42cc-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="a42cc-103">Sie können eine geschlossene Form mithilfe der <xref:System.Drawing.Image> -Klasse und der <xref:System.Drawing.TextureBrush> -Klasse mit einer Textur auffüllen.</span><span class="sxs-lookup"><span data-stu-id="a42cc-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42cc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a42cc-104">Example</span></span>  
 <span data-ttu-id="a42cc-105">Im folgenden Beispiel wird eine Ellipse mit einem Bild gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a42cc-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="a42cc-106">Der Code erstellt ein <xref:System.Drawing.Image> -Objekt und übergibt dann die Adresse dieses <xref:System.Drawing.Image> Objekts als Argument an einen <xref:System.Drawing.TextureBrush.%23ctor%2A> -Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a42cc-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="a42cc-107">Die dritte Anweisung skaliert das Bild, und die vierte Anweisung füllt die Ellipse mit wiederholten Kopien des skalierten Bilds.</span><span class="sxs-lookup"><span data-stu-id="a42cc-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="a42cc-108">Im folgenden Code enthält die <xref:System.Drawing.TextureBrush.Transform%2A> -Eigenschaft die Transformation, die auf das Bild angewendet wird, bevor es gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a42cc-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="a42cc-109">Angenommen, das ursprüngliche Bild hat eine Breite von 640 Pixeln und eine Höhe von 480 Pixel.</span><span class="sxs-lookup"><span data-stu-id="a42cc-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="a42cc-110">Die Transformation verkleinert das Bild auf 75 × 75 durch Festlegen der horizontalen und vertikalen Skalierungs Werte.</span><span class="sxs-lookup"><span data-stu-id="a42cc-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a42cc-111">Im folgenden Beispiel ist die Bildgröße 75 × 75 und die Ellipse-Größe 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="a42cc-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="a42cc-112">Da das Bild kleiner als die Ellipse ist, die es füllt, wird die Ellipse mit dem Bild gekachelt.</span><span class="sxs-lookup"><span data-stu-id="a42cc-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="a42cc-113">Das tiult bedeutet, dass das Bild horizontal und vertikal wiederholt wird, bis die Grenze der Form erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="a42cc-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="a42cc-114">Weitere Informationen zum tiult finden [Sie unter Gewusst wie: Kacheln Sie eine Form mit](how-to-tile-a-shape-with-an-image.md)einem Bild.</span><span class="sxs-lookup"><span data-stu-id="a42cc-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a42cc-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a42cc-115">Compiling the Code</span></span>  
 <span data-ttu-id="a42cc-116">Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter des- <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers ist.</span><span class="sxs-lookup"><span data-stu-id="a42cc-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42cc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a42cc-117">See also</span></span>

- [<span data-ttu-id="a42cc-118">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="a42cc-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
