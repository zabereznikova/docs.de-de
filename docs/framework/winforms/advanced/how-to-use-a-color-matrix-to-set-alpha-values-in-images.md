---
title: 'Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423735"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="de112-102">Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern</span><span class="sxs-lookup"><span data-stu-id="de112-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="de112-103">Die <xref:System.Drawing.Bitmap>-Klasse (die von der <xref:System.Drawing.Image>-Klasse erbt) und die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse bieten Funktionen zum erhalten und Festlegen von Pixelwerten.</span><span class="sxs-lookup"><span data-stu-id="de112-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="de112-104">Sie können die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse verwenden, um die Alpha Werte für ein gesamtes Bild zu ändern, oder Sie können die <xref:System.Drawing.Bitmap.SetPixel%2A>-Methode der <xref:System.Drawing.Bitmap>-Klasse zum Ändern einzelner Pixelwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="de112-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de112-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de112-105">Example</span></span>  
 <span data-ttu-id="de112-106">Die <xref:System.Drawing.Imaging.ImageAttributes>-Klasse verfügt über zahlreiche Eigenschaften, mit denen Sie Bilder während des Renderings ändern können.</span><span class="sxs-lookup"><span data-stu-id="de112-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="de112-107">Im folgenden Beispiel wird ein <xref:System.Drawing.Imaging.ImageAttributes>-Objekt verwendet, um alle Alpha Werte auf 80 Prozent ihrer Werte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="de112-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="de112-108">Dies erfolgt durch Initialisieren einer Farbmatrix und Festlegen des alphaskalierungswerts in der Matrix auf 0,8.</span><span class="sxs-lookup"><span data-stu-id="de112-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="de112-109">Die Adresse der Farbmatrix wird an die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>-Methode des <xref:System.Drawing.Imaging.ImageAttributes>-Objekts und das <xref:System.Drawing.Imaging.ImageAttributes>-Objekt an die <xref:System.Drawing.Graphics.DrawString%2A>-Methode des <xref:System.Drawing.Graphics> Objekts übermittelt.</span><span class="sxs-lookup"><span data-stu-id="de112-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="de112-110">Während des Renderings werden die Alpha Werte in der Bitmap in 80 Prozent ihrer Art konvertiert.</span><span class="sxs-lookup"><span data-stu-id="de112-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="de112-111">Dies führt zu einem Bild, das mit dem Hintergrund kombiniert wird.</span><span class="sxs-lookup"><span data-stu-id="de112-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="de112-112">Wie die folgende Abbildung zeigt, sieht das Bitmap-Bild transparent aus. Sie sehen, dass die schwarze Linie durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="de112-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="de112-113">![Screenshot der Alpha Mischung mithilfe einer Matrix](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span><span class="sxs-lookup"><span data-stu-id="de112-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="de112-114">Wenn sich das Bild über dem weißen Teil des Hintergrunds befindet, wurde das Bild mit der Farbe weiß gemischt.</span><span class="sxs-lookup"><span data-stu-id="de112-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="de112-115">Wenn das Bild die schwarze Linie überschreitet, wird das Bild mit der Farbe schwarz gemischt.</span><span class="sxs-lookup"><span data-stu-id="de112-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de112-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="de112-116">Compiling the Code</span></span>  
 <span data-ttu-id="de112-117">Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, bei dem es sich um einen Parameter <xref:System.Windows.Forms.PaintEventHandler>handelt.</span><span class="sxs-lookup"><span data-stu-id="de112-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de112-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de112-118">See also</span></span>

- [<span data-ttu-id="de112-119">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de112-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="de112-120">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="de112-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
