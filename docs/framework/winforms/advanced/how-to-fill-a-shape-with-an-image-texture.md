---
title: 'Gewusst wie: Ausfüllen einer Form mit einer Bildstruktur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523289"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="794b8-102">Gewusst wie: Ausfüllen einer Form mit einer Bildstruktur</span><span class="sxs-lookup"><span data-stu-id="794b8-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="794b8-103">Sie können mit einer Textur eine geschlossene Form ausfüllen, mithilfe der <xref:System.Drawing.Image> Klasse und die <xref:System.Drawing.TextureBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="794b8-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="794b8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="794b8-104">Example</span></span>  
 <span data-ttu-id="794b8-105">Das folgende Beispiel füllt eine Ellipse mit einem Bild.</span><span class="sxs-lookup"><span data-stu-id="794b8-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="794b8-106">Der Code erstellt ein <xref:System.Drawing.Image> -Objekt und übergibt dann die Adresse des, <xref:System.Drawing.Image> Objekt als Argument an einen <xref:System.Drawing.TextureBrush.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="794b8-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="794b8-107">Die dritte Anweisung wird das Bild skaliert, und die vierte Anweisung füllt die Ellipse mit Kopien der skalierten Bildes gekachelt.</span><span class="sxs-lookup"><span data-stu-id="794b8-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="794b8-108">Im folgenden Code wird die <xref:System.Drawing.TextureBrush.Transform%2A> Eigenschaft enthält die Transformation, die auf das Abbild angewendet wird, bevor es gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="794b8-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="794b8-109">Wird davon ausgegangen Sie, dass das ursprüngliche Bild einer Breite von 640 Pixel und eine Höhe von 480 Pixel verfügt.</span><span class="sxs-lookup"><span data-stu-id="794b8-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="794b8-110">Die Transformation verkleinert das Bild auf 75 × 75, durch die horizontale und vertikale Skalierung Werte festlegen.</span><span class="sxs-lookup"><span data-stu-id="794b8-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="794b8-111">Im folgenden Beispiel die Bildgröße beträgt 75 × 75, und die Ellipse-Größe beträgt 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="794b8-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="794b8-112">Da das Bild kleiner als die Ellipse, die es ausfüllt ist, wird der Ellipse, die mit dem Image angeordnet.</span><span class="sxs-lookup"><span data-stu-id="794b8-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="794b8-113">Kacheln bedeutet, dass das Bild horizontal und vertikal bis die Begrenzung der Form wiederholt wird, wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="794b8-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="794b8-114">Weitere Informationen zu Kacheln finden Sie unter [wie: Kacheln einer Form mit einem Bild](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="794b8-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="794b8-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="794b8-115">Compiling the Code</span></span>  
 <span data-ttu-id="794b8-116">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="794b8-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794b8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="794b8-117">See Also</span></span>  
 [<span data-ttu-id="794b8-118">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="794b8-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
