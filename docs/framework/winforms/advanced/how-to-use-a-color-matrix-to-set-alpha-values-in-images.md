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
ms.openlocfilehash: ed129cd9487ba1416cd69b2e13f59747856cb598
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522345"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="a25dd-102">Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern</span><span class="sxs-lookup"><span data-stu-id="a25dd-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="a25dd-103">Die <xref:System.Drawing.Bitmap> Klasse (geerbt von der <xref:System.Drawing.Image> Klasse) und die <xref:System.Drawing.Imaging.ImageAttributes> Klasse bieten Funktionen für Pixelwerte festlegen und abrufen.</span><span class="sxs-lookup"><span data-stu-id="a25dd-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="a25dd-104">Können Sie die <xref:System.Drawing.Imaging.ImageAttributes> Klasse so ändern Sie den Alpha-Werte für ein vollständiges Bild, oder Sie rufen die <xref:System.Drawing.Bitmap.SetPixel%2A> Methode der <xref:System.Drawing.Bitmap> Klasse, um die einzelnen Pixels-Werte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a25dd-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a25dd-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a25dd-105">Example</span></span>  
 <span data-ttu-id="a25dd-106">Die <xref:System.Drawing.Imaging.ImageAttributes> -Klasse verfügt über zahlreiche Eigenschaften, die Sie verwenden können, während des Renderings Bilder ändern.</span><span class="sxs-lookup"><span data-stu-id="a25dd-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="a25dd-107">Im folgenden Beispiel ein <xref:System.Drawing.Imaging.ImageAttributes> Objekt wird verwendet, um alle Alphawerte auf 80 Prozent des Originalwerts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a25dd-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="a25dd-108">Dies erfolgt durch Initialisieren einer Farbmatrix und den Wert in der Matrix mit 0,8 Skalierung Alpha festlegen.</span><span class="sxs-lookup"><span data-stu-id="a25dd-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="a25dd-109">An die Adresse der Farbmatrix übergeben wird die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> Methode der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt, und die <xref:System.Drawing.Imaging.ImageAttributes> -Objekt übergeben wird die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a25dd-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="a25dd-110">Beim Rendern, werden die Alphawerte in der Bitmap-80 % des Originalwerts konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a25dd-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="a25dd-111">Dies führt zu einem Bild, das mit dem Hintergrund gemischt ist.</span><span class="sxs-lookup"><span data-stu-id="a25dd-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="a25dd-112">Wie in die folgende Abbildung gezeigt, sieht das Bitmap-Bild transparent; Sie können die durchgehende schwarze Linie durchzogen sehen.</span><span class="sxs-lookup"><span data-stu-id="a25dd-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="a25dd-113">![Alphablending mit einer Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "Bild2")</span><span class="sxs-lookup"><span data-stu-id="a25dd-113">![Alpha Blending Using a Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="a25dd-114">Das Bild über den weißen Bereich des Hintergrunds vorhanden ist, hat das Bild mit der Farbe Weiß gemischt wurden.</span><span class="sxs-lookup"><span data-stu-id="a25dd-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="a25dd-115">In dem das Bild für die schwarze Linie schneidet wird das Abbild mit der Farbe Schwarz gemischt.</span><span class="sxs-lookup"><span data-stu-id="a25dd-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a25dd-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a25dd-116">Compiling the Code</span></span>  
 <span data-ttu-id="a25dd-117">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a25dd-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25dd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a25dd-118">See Also</span></span>  
 [<span data-ttu-id="a25dd-119">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a25dd-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="a25dd-120">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="a25dd-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
