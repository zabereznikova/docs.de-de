---
title: 'Gewusst wie: Drehen von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111334"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f71c9-102">Gewusst wie: Drehen von Farben</span><span class="sxs-lookup"><span data-stu-id="f71c9-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f71c9-103">Die Rotation in einem vierdimensionalen Farbraum ist schwer zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="f71c9-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f71c9-104">Wir können es einfacher machen, die Rotation zu visualisieren, indem wir uns darauf einigen, eine der Farbkomponenten festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="f71c9-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f71c9-105">Angenommen, wir stimmen zu, die Alphakomponente auf 1 festzuhalten (vollständig undurchsichtig).</span><span class="sxs-lookup"><span data-stu-id="f71c9-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f71c9-106">Dann können wir einen dreidimensionalen Farbraum mit roten, grünen und blauen Achsen visualisieren, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f71c9-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Abbildung, die die Drehung mit roten, grünen und blauen Achsen anzeigt.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="f71c9-108">Eine Farbe kann als ein Punkt im 3D-Raum betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f71c9-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="f71c9-109">Beispielsweise stellt der Punkt (1, 0, 0) im Raum die Farbe Rot und der Punkt (0, 1, 0) im Raum die Farbe Grün dar.</span><span class="sxs-lookup"><span data-stu-id="f71c9-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f71c9-110">Die folgende Abbildung zeigt, was es bedeutet, die Farbe (1, 0, 0) in der rot-grünen Ebene um einen Winkel von 60 Grad zu drehen.</span><span class="sxs-lookup"><span data-stu-id="f71c9-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f71c9-111">Die Rotation in einer Ebene parallel zur rot-grünen Ebene kann als Rotation um die blaue Achse betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f71c9-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Abbildung, die die Drehung um die blaue Achse zeigt.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="f71c9-113">Die folgende Abbildung zeigt, wie Sie eine Farbmatrix initialisieren, um Rotationen um jede der drei Koordinatenachsen (rot, grün, blau) durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="f71c9-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Initialisieren Sie eine Farbmatrix, um Drehungen um drei Achsen durchzuführen.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="f71c9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f71c9-115">Example</span></span>  
 <span data-ttu-id="f71c9-116">Im folgenden Beispiel wird ein Bild mit einer Farbe (1, 0, 0,6) verwendet und eine 60-Grad-Drehung um die blaue Achse angewendet.</span><span class="sxs-lookup"><span data-stu-id="f71c9-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f71c9-117">Der Drehwinkel wird in einer Ebene, die parallel zur rot-grünen Ebene verläuft, ausgefegt.</span><span class="sxs-lookup"><span data-stu-id="f71c9-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f71c9-118">Die folgende Abbildung zeigt das Originalbild auf der linken Seite und das farblich gedrehte Bild auf der rechten Seite:</span><span class="sxs-lookup"><span data-stu-id="f71c9-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Abbildung, die Originalbild und farblich gedrehtes Bild zeigt.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="f71c9-120">Die folgende Abbildung zeigt eine Visualisierung der Farbrotation, die im folgenden Code durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="f71c9-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Abbildung, die die Visualisierung der Farbrotation zeigt.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f71c9-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f71c9-122">Compiling the Code</span></span>  
 <span data-ttu-id="f71c9-123">Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist.</span><span class="sxs-lookup"><span data-stu-id="f71c9-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f71c9-124">Ersetzen `RotationInput.bmp` Sie dies durch einen Bilddateinamen und einen Pfad, der auf Ihrem System gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f71c9-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71c9-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f71c9-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f71c9-126">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f71c9-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f71c9-127">Neueinfärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="f71c9-127">Recoloring Images</span></span>](recoloring-images.md)
