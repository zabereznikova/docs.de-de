---
title: 'Vorgehensweise: Zuschneiden und Skalieren von Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189884"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="9b795-102">Vorgehensweise: Zuschneiden und Skalieren von Bildern</span><span class="sxs-lookup"><span data-stu-id="9b795-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="9b795-103">Die <xref:System.Drawing.Graphics> Klasse bietet mehrere <xref:System.Drawing.Graphics.DrawImage%2A> Methoden, von denen einige über die Parameter für Quell- und Ziel, die Sie zum Zuschneiden und Skalieren von Bildern verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9b795-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b795-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b795-104">Example</span></span>  
 <span data-ttu-id="9b795-105">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datenträgerdatei Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="9b795-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="9b795-106">Der Code zeichnet das gesamte Apple-Bild in seiner ursprünglichen Größe.</span><span class="sxs-lookup"><span data-stu-id="9b795-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="9b795-107">Der Code ruft dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt, das einen Teil des Apple-Images in einem Zielrechteck zu zeichnen, die größer als das Originalbild von Apple.</span><span class="sxs-lookup"><span data-stu-id="9b795-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="9b795-108">Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, welcher Teil der Apple zu zeichnenden unter Verwendung des fünften und sechsten Argumente.</span><span class="sxs-lookup"><span data-stu-id="9b795-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="9b795-109">In diesem Fall wird die Apple 75 Prozent der Breite und 75 Prozent seiner Höhe zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9b795-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="9b795-110">Die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode bestimmt, wo Sie zugeschnittene Apple gezeichnet werden soll und wie groß, um die zugeschnittenen Apfels anhand des Zielrechtecks, dies ist durch das zweite Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="9b795-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="9b795-111">In diesem Fall ist das Zielrechteck, 30 Prozent breiter und 30 Prozent höher als das Originalbild.</span><span class="sxs-lookup"><span data-stu-id="9b795-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="9b795-112">Die folgende Abbildung zeigt die ursprünglichen Apple und die skalierte Apple zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9b795-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![Screenshot von einer ursprünglichen Bild und die gleichen zugeschnitten.](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b795-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9b795-114">Compiling the Code</span></span>  
 <span data-ttu-id="9b795-115">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="9b795-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="9b795-116">Achten Sie darauf, ersetzen Sie dies `Apple.gif` mit einer Bilddateinamen und den Pfad, die auf Ihrem System gültig sind.</span><span class="sxs-lookup"><span data-stu-id="9b795-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b795-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b795-117">See also</span></span>

- [<span data-ttu-id="9b795-118">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="9b795-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="9b795-119">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="9b795-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
