---
title: 'Vorgehensweise: Drehen von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175538"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f7f33-102">Vorgehensweise: Drehen von Farben</span><span class="sxs-lookup"><span data-stu-id="f7f33-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f7f33-103">Drehung in einer vierdimensionalen Farbraum ist schwierig, zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7f33-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f7f33-104">Wir können es vorstellbar, stimmen zu einer der festen Farbkomponenten vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f7f33-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f7f33-105">Nehmen wir an, dass in jedem die alpha-Komponente auf 1 festgesetzt (vollständig deckend) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f7f33-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f7f33-106">Dann können wir einen dreidimensionalen Farbraum mit roten, grünen und blauen Achsen visualisieren, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7f33-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Abbildung der Drehung mit roten, grünen und blauen Achsen.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="f7f33-108">Eine Farbe kann als ein Punkt im 3D-Raum betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f7f33-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="f7f33-109">Beispielsweise wird der Punkt im Raum (1, 0, 0) darstellt, die Farbe Rot, und der Punkt im Raum (0, 1, 0) darstellt, die Farbe Grün.</span><span class="sxs-lookup"><span data-stu-id="f7f33-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f7f33-110">Die folgende Abbildung zeigt was es bedeutet, die die Farbe (1, 0, 0) gedreht, über einen Winkel von 60 Grad in der Rot-Grün-Ebene.</span><span class="sxs-lookup"><span data-stu-id="f7f33-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f7f33-111">Drehung in einer Ebene Parallel zur Rot-Grün-Ebene kann als Drehung um die blauen Achse betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="f7f33-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Abbildung der Drehung um die blauen Achse.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="f7f33-113">Die folgende Abbildung zeigt das Initialisieren einer Farbmatrix zum Ausführen der Rotation zu jeder der drei Koordinatenachsen (Rot, Grün, Blau):</span><span class="sxs-lookup"><span data-stu-id="f7f33-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Initialisieren einer Farbmatrix zum Ausführen von Rotationen um drei Achsen an.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="f7f33-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7f33-115">Example</span></span>  
 <span data-ttu-id="f7f33-116">Im folgenden Beispiel wird ein Bild, das alle eine Farbe ("1", "0", "0,6") und wendet eine Drehung um 60 Grad die blaue Achse an.</span><span class="sxs-lookup"><span data-stu-id="f7f33-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f7f33-117">Der Winkel der Drehung wird sich in einer Ebene überflüssig, die parallel zu der Rot-Grün-Ebene ist.</span><span class="sxs-lookup"><span data-stu-id="f7f33-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f7f33-118">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das Bild Farben gedreht, auf der rechten Seite an:</span><span class="sxs-lookup"><span data-stu-id="f7f33-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Abbildung der ursprüngliche Bild und Bild Farben gedreht.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="f7f33-120">Die folgende Abbildung zeigt eine Visualisierung der Color-Drehung, die in den folgenden Code ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="f7f33-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Abbildung der Visualisierung der Drehung Farbe.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f7f33-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f7f33-122">Compiling the Code</span></span>  
 <span data-ttu-id="f7f33-123">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f7f33-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f7f33-124">Ersetzen Sie dies `RotationInput.bmp` mit einer Bilddateinamen gültigen und Pfad auf Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="f7f33-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f33-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7f33-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f7f33-126">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7f33-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f7f33-127">Neueinfärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="f7f33-127">Recoloring Images</span></span>](recoloring-images.md)
