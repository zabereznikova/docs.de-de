---
title: 'Vorgehensweise: Verwenden einer Farbmatrix zum Transformieren einer Farbe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 66ddd85d4f841edf9cabf338fbb66a8e2dda491a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075163"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="c36cf-102">Vorgehensweise: Verwenden einer Farbmatrix zum Transformieren einer Farbe</span><span class="sxs-lookup"><span data-stu-id="c36cf-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="c36cf-103">Stellt die <xref:System.Drawing.Image> und <xref:System.Drawing.Bitmap> Klassen zum Speichern und Bearbeiten von Bildern.</span><span class="sxs-lookup"><span data-stu-id="c36cf-103">provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <xref:System.Drawing.Image> <span data-ttu-id="c36cf-104">und <xref:System.Drawing.Bitmap> Objekte speichern die Farbe jedes Pixels als 32-Bit-Zahl: jeweils 8 Bit für Rot, Grün, Blau und Alpha.</span><span class="sxs-lookup"><span data-stu-id="c36cf-104">and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="c36cf-105">Jede der vier Komponenten ist es sich um eine Zahl zwischen 0 und 255, wobei 0 für keine Intensität und 255, die vollständigen Intensität darstellt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="c36cf-106">Die alpha-Komponente gibt die Transparenz der Farbe an: 0 vollständig transparent ist, und 255 vollständig deckend ist.</span><span class="sxs-lookup"><span data-stu-id="c36cf-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="c36cf-107">Ein Vektor Farbe ist ein 4-Tupel der Form (Rot, Grün, Blau, Alpha).</span><span class="sxs-lookup"><span data-stu-id="c36cf-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="c36cf-108">Beispielsweise steht der Color-Vektor (0, 255, 0, 255) eine nicht transparente Farbe, die ohne Rot oder Blau, jedoch mit vollständigen Intensität.</span><span class="sxs-lookup"><span data-stu-id="c36cf-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="c36cf-109">Eine andere Konvention für die Darstellung von Farben verwendet die Zahl 1 für vollständigen Intensität.</span><span class="sxs-lookup"><span data-stu-id="c36cf-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="c36cf-110">Verwenden diese Konvention, würde die Farbe, die im vorherigen Absatz beschriebene um den Vektor (0, 1, 0, 1) dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c36cf-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="c36cf-111">die Konvention von 1 als vollständigen Intensität bei verwendet Farbe Transformationen wird.</span><span class="sxs-lookup"><span data-stu-id="c36cf-111">uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="c36cf-112">Sie können Farbe Vektoren vorhersagestunden wird die Farbe Vektoren mit einer 4 × 4-Matrix lineare Transformationen (Drehung, Skalierung und ähnliches) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="c36cf-113">Eine 4 x 4-Matrix können Sie jedoch eine Übersetzung (nicht lineare) ausführen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="c36cf-114">Wenn Sie eine dummy fünfte Koordinate (z. B. die Nummer 1) aller die Vektoren Farbe hinzufügen, können Sie eine 5 x 5-Matrix, um eine beliebige Kombination von linearen Transformationen und Konvertierungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c36cf-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="c36cf-115">Eine Transformation, bestehend aus eine lineare Umformung gefolgt von einer Übersetzung wird eine affine Transformation aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c36cf-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="c36cf-116">Nehmen wir beispielsweise an, dass Sie mit der Farbe ("0.2", "0.0", "0,4", "1.0") beginnen und die folgenden Transformationen anwenden möchten:</span><span class="sxs-lookup"><span data-stu-id="c36cf-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1.  <span data-ttu-id="c36cf-117">Verdoppelung des Rotanteils</span><span class="sxs-lookup"><span data-stu-id="c36cf-117">Double the red component</span></span>  
  
2.  <span data-ttu-id="c36cf-118">Die Komponenten roten, grünen und blauen 0,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c36cf-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="c36cf-119">Die folgende Matrixmultiplikation führt die beiden Transformationen in entsprechender Reihenfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="c36cf-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="c36cf-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="c36cf-121">Die Elemente einer Farbmatrix werden von Zeilen- und klicken Sie dann (die nullbasierte) indiziert.</span><span class="sxs-lookup"><span data-stu-id="c36cf-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="c36cf-122">Beispielsweise ist der Eintrag in der fünften Zeile und dritten Spalte der Matrix M durch M [4] [2] gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c36cf-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="c36cf-123">Die 5 x 5-Identitätsmatrix (in der folgenden Abbildung dargestellt) verfügt über 1 s, auf der diagonalen und 0, die alle anderen Elemente.</span><span class="sxs-lookup"><span data-stu-id="c36cf-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="c36cf-124">Wenn Sie einen Vektor Farbe durch die Identitätsmatrix multiplizieren, ändert sich der Vektor Farbe nicht.</span><span class="sxs-lookup"><span data-stu-id="c36cf-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="c36cf-125">Eine einfache Möglichkeit, bilden die Matrix eine Farbe-Transformation ist mit die Identitätsmatrix beginnen, und stellen eine kleine Änderung, die die gewünschte Transformation erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="c36cf-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="c36cf-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="c36cf-127">Eine ausführlichere Erläuterung von Matrizen und Transformationen, finden Sie unter [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="c36cf-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c36cf-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c36cf-128">Example</span></span>  
 <span data-ttu-id="c36cf-129">Im folgenden Beispiel wird ein Bild an, die alle eine Farbe ("0.2", "0.0", "0,4", "1.0") und wendet die Transformation, die in den vorherigen Absätzen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c36cf-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="c36cf-130">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die transformierten auf der rechten Seite an.</span><span class="sxs-lookup"><span data-stu-id="c36cf-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="c36cf-131">![Farben](./media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="c36cf-131">![Colors](./media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="c36cf-132">Der Code im folgenden Beispiel verwendet die folgenden Schritte aus, um die über erneutes Einfärben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c36cf-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1.  <span data-ttu-id="c36cf-133">Initialisiert eine <xref:System.Drawing.Imaging.ColorMatrix> Objekt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2.  <span data-ttu-id="c36cf-134">Erstellen einer <xref:System.Drawing.Imaging.ImageAttributes> Objekt, und übergeben die <xref:System.Drawing.Imaging.ColorMatrix> -Objekt an die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> -Methode der der <xref:System.Drawing.Imaging.ImageAttributes> Objekt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3.  <span data-ttu-id="c36cf-135">Übergeben der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="c36cf-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c36cf-136">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c36cf-136">Compiling the Code</span></span>  
 <span data-ttu-id="c36cf-137">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c36cf-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36cf-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c36cf-138">See also</span></span>

- [<span data-ttu-id="c36cf-139">Neueinfärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="c36cf-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="c36cf-140">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="c36cf-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
