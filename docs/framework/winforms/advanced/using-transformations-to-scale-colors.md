---
title: Skalieren von Farben mithilfe von Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 9255dd4adba19bfef1332e5e3dfa463ee96f43f0
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653989"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="fa8e0-102">Skalieren von Farben mithilfe von Transformationen</span><span class="sxs-lookup"><span data-stu-id="fa8e0-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="fa8e0-103">Die Skalierungstransformation multipliziert mindestens eine der vier Farbkomponenten durch eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="fa8e0-104">Die Farbe Matrix Einträge, die Skalierung darstellen, werden in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="fa8e0-105">Komponente skaliert werden</span><span class="sxs-lookup"><span data-stu-id="fa8e0-105">Component to be scaled</span></span>|<span data-ttu-id="fa8e0-106">Matrixeintrag</span><span class="sxs-lookup"><span data-stu-id="fa8e0-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="fa8e0-107">Rot</span><span class="sxs-lookup"><span data-stu-id="fa8e0-107">Red</span></span>|<span data-ttu-id="fa8e0-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="fa8e0-108">[0][0]</span></span>|  
|<span data-ttu-id="fa8e0-109">Grün</span><span class="sxs-lookup"><span data-stu-id="fa8e0-109">Green</span></span>|<span data-ttu-id="fa8e0-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="fa8e0-110">[1][1]</span></span>|  
|<span data-ttu-id="fa8e0-111">Blau</span><span class="sxs-lookup"><span data-stu-id="fa8e0-111">Blue</span></span>|<span data-ttu-id="fa8e0-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="fa8e0-112">[2][2]</span></span>|  
|<span data-ttu-id="fa8e0-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="fa8e0-113">Alpha</span></span>|<span data-ttu-id="fa8e0-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="fa8e0-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="fa8e0-115">Skalieren einer Farbe</span><span class="sxs-lookup"><span data-stu-id="fa8e0-115">Scaling One Color</span></span>  
 <span data-ttu-id="fa8e0-116">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="fa8e0-117">Klicken Sie dann skaliert der Code die blaue Komponente der einzelnen Pixel in der Abbildung, um den Faktor 2.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="fa8e0-118">Das ursprüngliche Bild wird zusammen mit den transformierten Bild gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="fa8e0-119">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die skalierten Bild auf der rechten Seite an:</span><span class="sxs-lookup"><span data-stu-id="fa8e0-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot, in dem die ursprünglichen und skalierten Farben verglichen.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="fa8e0-121">Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach der blauen Skalierung.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="fa8e0-122">Beachten Sie, dass die blaue Komponente in der vierten Farbleiste aus 0.8 auf 0.6 ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="fa8e0-123">Der Grund dafür ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] behält nur der Bruchteil des Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="fa8e0-124">Beispielsweise (: (2)(0.8) = 1.6, und der Bruchteil von 1.6 ist 0.6.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="fa8e0-125">Nur die Nachkommastellen beibehalten wird sichergestellt, dass das Ergebnis immer im Intervall [0, 1].</span><span class="sxs-lookup"><span data-stu-id="fa8e0-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="fa8e0-126">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="fa8e0-126">Original</span></span>|<span data-ttu-id="fa8e0-127">Skaliert</span><span class="sxs-lookup"><span data-stu-id="fa8e0-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="fa8e0-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="fa8e0-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="fa8e0-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="fa8e0-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="fa8e0-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="fa8e0-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="fa8e0-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="fa8e0-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="fa8e0-136">Skalieren von mehreren Farben</span><span class="sxs-lookup"><span data-stu-id="fa8e0-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="fa8e0-137">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="fa8e0-138">Dann wird der Code die Rot-, Grün- und blauen-Komponenten der einzelnen Pixel in der Abbildung skaliert.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="fa8e0-139">Die roten Komponenten werden so skaliert, um 25 Prozent, die grüne Komponenten werden 35 Prozent herunterskaliert und die blaue Komponenten werden so skaliert, um 50 Prozent.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="fa8e0-140">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die skalierten Bild auf der rechten Seite an:</span><span class="sxs-lookup"><span data-stu-id="fa8e0-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot, in dem die ursprünglichen und skalierten Farben verglichen.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="fa8e0-142">Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach die roten, grünen und blauen Skalierung.</span><span class="sxs-lookup"><span data-stu-id="fa8e0-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="fa8e0-143">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="fa8e0-143">Original</span></span>|<span data-ttu-id="fa8e0-144">Skaliert</span><span class="sxs-lookup"><span data-stu-id="fa8e0-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="fa8e0-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="fa8e0-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="fa8e0-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="fa8e0-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="fa8e0-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="fa8e0-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="fa8e0-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="fa8e0-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="fa8e0-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa8e0-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa8e0-153">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="fa8e0-154">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa8e0-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="fa8e0-155">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="fa8e0-155">Recoloring Images</span></span>](recoloring-images.md)
