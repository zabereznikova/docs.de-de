---
title: 'Gewusst wie: Verschieben von Bildfarben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 48f506f76ff6e9ca648822d073b6f6a852b9ca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522535"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="80125-102">Gewusst wie: Verschieben von Bildfarben</span><span class="sxs-lookup"><span data-stu-id="80125-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="80125-103">Eine Übersetzung Fügt einen Wert für eine oder mehrere der vier Farbkomponenten.</span><span class="sxs-lookup"><span data-stu-id="80125-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="80125-104">Die Farbe Matrix Einträge, die Übersetzungen darstellen, werden in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="80125-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="80125-105">Die Komponente zu übersetzende</span><span class="sxs-lookup"><span data-stu-id="80125-105">Component to be translated</span></span>|<span data-ttu-id="80125-106">Matrixeintrag</span><span class="sxs-lookup"><span data-stu-id="80125-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="80125-107">Rot</span><span class="sxs-lookup"><span data-stu-id="80125-107">Red</span></span>|<span data-ttu-id="80125-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="80125-108">[4][0]</span></span>|  
|<span data-ttu-id="80125-109">Grün</span><span class="sxs-lookup"><span data-stu-id="80125-109">Green</span></span>|<span data-ttu-id="80125-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="80125-110">[4][1]</span></span>|  
|<span data-ttu-id="80125-111">Blau</span><span class="sxs-lookup"><span data-stu-id="80125-111">Blue</span></span>|<span data-ttu-id="80125-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="80125-112">[4][2]</span></span>|  
|<span data-ttu-id="80125-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="80125-113">Alpha</span></span>|<span data-ttu-id="80125-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="80125-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80125-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80125-115">Example</span></span>  
 <span data-ttu-id="80125-116">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="80125-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="80125-117">Der Code fügt dann 0,75 an die rote Komponente jedes Pixels in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="80125-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="80125-118">Das ursprüngliche Image wird zusammen mit den transformierten Bild gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="80125-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="80125-119">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das transformierte Bild auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="80125-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="80125-120">![Verschieben von Farben](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="80125-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="80125-121">Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach die rote Übersetzung.</span><span class="sxs-lookup"><span data-stu-id="80125-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="80125-122">Beachten Sie, weil der Maximalwert für eine Komponente Farbe 1 ist, nicht die rote Komponente in der zweiten Zeile geändert wird.</span><span class="sxs-lookup"><span data-stu-id="80125-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="80125-123">(Entsprechend ist der minimale Wert für eine Komponente Farbe 0.)</span><span class="sxs-lookup"><span data-stu-id="80125-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="80125-124">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="80125-124">Original</span></span>|<span data-ttu-id="80125-125">Übersetzt</span><span class="sxs-lookup"><span data-stu-id="80125-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="80125-126">Schwarz (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="80125-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="80125-128">Rot (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="80125-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="80125-130">Grün (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="80125-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="80125-132">Blau (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="80125-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="80125-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80125-134">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="80125-134">Compiling the Code</span></span>  
 <span data-ttu-id="80125-135">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="80125-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="80125-136">Ersetzen Sie `ColorBars.bmp` mit einem Dateinamen und Pfad, die auf Ihrem System gültig sind.</span><span class="sxs-lookup"><span data-stu-id="80125-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80125-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80125-137">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="80125-138">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80125-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="80125-139">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="80125-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
