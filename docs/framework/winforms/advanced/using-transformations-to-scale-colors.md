---
title: Skalieren von Farben mithilfe von Transformationen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7515f34858ef6f4b0495ac6fc545ae498d45c7f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="3be7c-102">Skalieren von Farben mithilfe von Transformationen</span><span class="sxs-lookup"><span data-stu-id="3be7c-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="3be7c-103">Eine Skalierungstransformation multipliziert mindestens eines der vier Farbkomponenten durch eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="3be7c-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="3be7c-104">Die Farbe Matrix Einträge, die Skalierung darstellen, werden in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="3be7c-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="3be7c-105">Komponente skaliert werden</span><span class="sxs-lookup"><span data-stu-id="3be7c-105">Component to be scaled</span></span>|<span data-ttu-id="3be7c-106">Matrixeintrag</span><span class="sxs-lookup"><span data-stu-id="3be7c-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="3be7c-107">Rot</span><span class="sxs-lookup"><span data-stu-id="3be7c-107">Red</span></span>|<span data-ttu-id="3be7c-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="3be7c-108">[0][0]</span></span>|  
|<span data-ttu-id="3be7c-109">Grün</span><span class="sxs-lookup"><span data-stu-id="3be7c-109">Green</span></span>|<span data-ttu-id="3be7c-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="3be7c-110">[1][1]</span></span>|  
|<span data-ttu-id="3be7c-111">Blau</span><span class="sxs-lookup"><span data-stu-id="3be7c-111">Blue</span></span>|<span data-ttu-id="3be7c-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="3be7c-112">[2][2]</span></span>|  
|<span data-ttu-id="3be7c-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="3be7c-113">Alpha</span></span>|<span data-ttu-id="3be7c-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="3be7c-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="3be7c-115">Skalieren einer Farbe</span><span class="sxs-lookup"><span data-stu-id="3be7c-115">Scaling One Color</span></span>  
 <span data-ttu-id="3be7c-116">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="3be7c-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="3be7c-117">Klicken Sie dann skaliert der Code mit einem Faktor von 2 Blauanteils jedes Pixels in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="3be7c-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="3be7c-118">Das ursprüngliche Image wird zusammen mit den transformierten Bild gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3be7c-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="3be7c-119">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und der skalierten Bild auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="3be7c-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="3be7c-120">![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="3be7c-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="3be7c-121">Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach der blauen Skalierung.</span><span class="sxs-lookup"><span data-stu-id="3be7c-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="3be7c-122">Beachten Sie, dass die blaue Komponente in der vierten Farbleiste aus 0,8 an 0,6 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3be7c-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="3be7c-123">Grund hierfür ist, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] behält nur die Nachkommastellen des Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="3be7c-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="3be7c-124">Beispielsweise (: (2)(0.8) = 1.6, und der Bruchteil der 1.6 ist 0.6.</span><span class="sxs-lookup"><span data-stu-id="3be7c-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="3be7c-125">Nur die Nachkommastellen beibehalten wird sichergestellt, dass das Ergebnis immer im Intervall [0, 1].</span><span class="sxs-lookup"><span data-stu-id="3be7c-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="3be7c-126">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="3be7c-126">Original</span></span>|<span data-ttu-id="3be7c-127">Skaliert</span><span class="sxs-lookup"><span data-stu-id="3be7c-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="3be7c-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="3be7c-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="3be7c-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="3be7c-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="3be7c-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="3be7c-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="3be7c-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="3be7c-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="3be7c-136">Skalieren von mehreren Farben</span><span class="sxs-lookup"><span data-stu-id="3be7c-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="3be7c-137">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="3be7c-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="3be7c-138">Klicken Sie dann skaliert der Code der Rot-, Grün- und blauen-Komponenten jedes Pixels in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="3be7c-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="3be7c-139">Die roten Komponenten werden so skaliert, um 25 Prozent, die grünen Komponenten werden 35 Prozent runterskaliert und blauen Komponenten werden so skaliert, um 50 Prozent.</span><span class="sxs-lookup"><span data-stu-id="3be7c-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="3be7c-140">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und der skalierten Bild auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="3be7c-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="3be7c-141">![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="3be7c-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="3be7c-142">Die folgende Tabelle enthält die Vektoren Farbe für die vier Balken vor und nach die roten, grünen und blauen Skalierung.</span><span class="sxs-lookup"><span data-stu-id="3be7c-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="3be7c-143">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="3be7c-143">Original</span></span>|<span data-ttu-id="3be7c-144">Skaliert</span><span class="sxs-lookup"><span data-stu-id="3be7c-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="3be7c-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="3be7c-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="3be7c-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="3be7c-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="3be7c-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="3be7c-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="3be7c-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="3be7c-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="3be7c-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3be7c-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3be7c-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="3be7c-154">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3be7c-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="3be7c-155">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="3be7c-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
