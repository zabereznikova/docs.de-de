---
title: 'Vorgehensweise: Scheren von Farben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: eff468e5761038723e16eddf84bdcf8849ac30d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720224"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="55cdf-102">Vorgehensweise: Scheren von Farben</span><span class="sxs-lookup"><span data-stu-id="55cdf-102">How to: Shear Colors</span></span>
<span data-ttu-id="55cdf-103">Verzerrens erhöht oder verringert eine Farbe Komponente durch eine Menge, die proportional zu einer anderen Farbe-Komponente.</span><span class="sxs-lookup"><span data-stu-id="55cdf-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="55cdf-104">Betrachten Sie beispielsweise die Transformation, in denen die Rotkomponente um die Hälfte der Wert des Blauanteils erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="55cdf-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="55cdf-105">Unter einer Transformation würde die Farbe ("0.2", "0.5", "1") werden ("0,7", "0.5", "1").</span><span class="sxs-lookup"><span data-stu-id="55cdf-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="55cdf-106">Der neue Rotanteil ist "0,2" + ((1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="55cdf-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55cdf-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55cdf-107">Example</span></span>  
 <span data-ttu-id="55cdf-108">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="55cdf-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="55cdf-109">Anschließend wird der Code im vorherigen Abschnitt auf jedes Pixel in der Abbildung beschriebene Verbiegen Transformation angewendet.</span><span class="sxs-lookup"><span data-stu-id="55cdf-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="55cdf-110">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die Schertransformation auf der rechten Seite an.</span><span class="sxs-lookup"><span data-stu-id="55cdf-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="55cdf-111">![Scheren von Farben](./media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="55cdf-111">![Shear Colors](./media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="55cdf-112">Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach der Transformation Verbiegen.</span><span class="sxs-lookup"><span data-stu-id="55cdf-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="55cdf-113">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="55cdf-113">Original</span></span>|<span data-ttu-id="55cdf-114">Verbogen</span><span class="sxs-lookup"><span data-stu-id="55cdf-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="55cdf-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="55cdf-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="55cdf-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="55cdf-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="55cdf-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="55cdf-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="55cdf-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="55cdf-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="55cdf-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55cdf-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="55cdf-123">Compiling the Code</span></span>  
 <span data-ttu-id="55cdf-124">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="55cdf-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="55cdf-125">Ersetzen Sie dies `ColorBars.bmp` mit einem Image-Name und Pfad auf Ihrem System ungültig.</span><span class="sxs-lookup"><span data-stu-id="55cdf-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cdf-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55cdf-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="55cdf-127">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55cdf-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="55cdf-128">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="55cdf-128">Recoloring Images</span></span>](recoloring-images.md)
