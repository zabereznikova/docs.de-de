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
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142393"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="5f49e-102">Gewusst wie: Scheren von Farben</span><span class="sxs-lookup"><span data-stu-id="5f49e-102">How to: Shear Colors</span></span>
<span data-ttu-id="5f49e-103">Das Scheren erhöht oder verringert eine Farbkomponente um einen Betrag, der proportional zu einer anderen Farbkomponente ist.</span><span class="sxs-lookup"><span data-stu-id="5f49e-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="5f49e-104">Betrachten Sie beispielsweise die Transformation, bei der die rote Komponente um die Hälfte des Wertes der blauen Komponente erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="5f49e-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="5f49e-105">Bei einer solchen Transformation würde die Farbe (0,2, 0,5, 1) (0,7, 0,5, 1) werden.</span><span class="sxs-lookup"><span data-stu-id="5f49e-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="5f49e-106">Die neue rote Komponente ist 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="5f49e-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f49e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f49e-107">Example</span></span>  
 <span data-ttu-id="5f49e-108">Im folgenden Beispiel <xref:System.Drawing.Image> wird ein Objekt aus der Datei ColorBars4.bmp erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f49e-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="5f49e-109">Anschließend wendet der Code die im vorherigen Absatz beschriebene Schertransformation auf jedes Pixel im Bild an.</span><span class="sxs-lookup"><span data-stu-id="5f49e-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="5f49e-110">Die folgende Abbildung zeigt das Originalbild auf der linken Seite und das abgeserte Bild auf der rechten Seite:</span><span class="sxs-lookup"><span data-stu-id="5f49e-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![Zwei Quadrate mit farbigen Streifen nebeneinander, die das Originalbild und das geerschbte Bild veranschaulichen.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="5f49e-112">In der folgenden Tabelle sind die Farbvektoren für die vier Balken vor und nach der Schertransformation aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f49e-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="5f49e-113">Original</span><span class="sxs-lookup"><span data-stu-id="5f49e-113">Original</span></span>|<span data-ttu-id="5f49e-114">Geschert</span><span class="sxs-lookup"><span data-stu-id="5f49e-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="5f49e-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="5f49e-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="5f49e-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="5f49e-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="5f49e-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="5f49e-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="5f49e-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="5f49e-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5f49e-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5f49e-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5f49e-123">Compiling the Code</span></span>  
 <span data-ttu-id="5f49e-124">Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist.</span><span class="sxs-lookup"><span data-stu-id="5f49e-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="5f49e-125">Ersetzen `ColorBars.bmp` Sie dies durch einen Auf- und nach dem System gültigen Bildnamen und Pfad.</span><span class="sxs-lookup"><span data-stu-id="5f49e-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f49e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f49e-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="5f49e-127">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f49e-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5f49e-128">Neueinfärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="5f49e-128">Recoloring Images</span></span>](recoloring-images.md)
