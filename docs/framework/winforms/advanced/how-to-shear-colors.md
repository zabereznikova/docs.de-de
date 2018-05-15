---
title: 'Gewusst wie: Scheren von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 204f15ce44d5ad688be0ea9ac0fa4a90781b25dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="98a28-102">Gewusst wie: Scheren von Farben</span><span class="sxs-lookup"><span data-stu-id="98a28-102">How to: Shear Colors</span></span>
<span data-ttu-id="98a28-103">Scheren erhöht oder verringert eine Farbe Komponente durch einen Betrag proportional zu einer anderen Farbe-Komponente.</span><span class="sxs-lookup"><span data-stu-id="98a28-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="98a28-104">Betrachten Sie beispielsweise die Transformation, in dem die Hälfte der Wert des Blauanteils Rotanteils gestiegen ist.</span><span class="sxs-lookup"><span data-stu-id="98a28-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="98a28-105">Unter solchen eine Transformation werden die Farbe (0,2, 0,5, 1), (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="98a28-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="98a28-106">Neuen Rotanteils ist 0,2 + ((1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="98a28-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98a28-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98a28-107">Example</span></span>  
 <span data-ttu-id="98a28-108">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="98a28-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="98a28-109">Der Code wendet dann die Scheren Transformation, die im vorherigen Abschnitt Pixel in der Abbildung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98a28-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="98a28-110">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das Schertransformation Bild auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="98a28-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="98a28-111">![Scheren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="98a28-111">![Shear Colors](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="98a28-112">Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach der Scheren Transformation.</span><span class="sxs-lookup"><span data-stu-id="98a28-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="98a28-113">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="98a28-113">Original</span></span>|<span data-ttu-id="98a28-114">Verbogen</span><span class="sxs-lookup"><span data-stu-id="98a28-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="98a28-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="98a28-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="98a28-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="98a28-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="98a28-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="98a28-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="98a28-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="98a28-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="98a28-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98a28-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="98a28-123">Compiling the Code</span></span>  
 <span data-ttu-id="98a28-124">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="98a28-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="98a28-125">Ersetzen Sie `ColorBars.bmp` mit einem Image-Name und Pfad auf Ihrem System ungültig.</span><span class="sxs-lookup"><span data-stu-id="98a28-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98a28-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98a28-126">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="98a28-127">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98a28-127">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="98a28-128">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="98a28-128">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
