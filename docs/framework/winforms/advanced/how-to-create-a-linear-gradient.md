---
title: 'Gewusst wie: Erstellen eines linearen Farbverlaufs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: 9eeedf1ef92bdf6e5e2724eeca5060765b0778f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522459"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="daab9-102">Gewusst wie: Erstellen eines linearen Farbverlaufs</span><span class="sxs-lookup"><span data-stu-id="daab9-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="daab9-103"> bietet horizontale, vertikale und diagonale lineare Farbverläufe.</span><span class="sxs-lookup"><span data-stu-id="daab9-103"> provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="daab9-104">Standardmäßig ändert sich die Farbe in einem linearen Farbverlauf einheitlich.</span><span class="sxs-lookup"><span data-stu-id="daab9-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="daab9-105">Allerdings können Sie einen linearen Farbverlauf anpassen, sodass sich die Farbe auf nicht einheitliche Weise ändert.</span><span class="sxs-lookup"><span data-stu-id="daab9-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="daab9-106">Im folgenden Beispiel wird eine Zeile und einer Ellipse, die ein Rechteck mit einem horizontalen linearen Farbverlaufspinsel.</span><span class="sxs-lookup"><span data-stu-id="daab9-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="daab9-107">Die <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor empfängt vier Argumente: zwei Punkten und mit zwei Farben aus.</span><span class="sxs-lookup"><span data-stu-id="daab9-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="daab9-108">Der erste Punkt (0, 10) bezieht sich auf der ersten Farbe (Rot), und der zweite Punkt (200, 10) der zweiten Farbe (Blau) zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="daab9-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="daab9-109">Erwartungsgemäß, der Linie von (0, 10), (200, 10) ändert sich allmählich von Rot und Blau.</span><span class="sxs-lookup"><span data-stu-id="daab9-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="daab9-110">Die Werte 10 in den Punkten (50, 10) und (200, 10) sind nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="daab9-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="daab9-111">Wichtig ist, dass die beiden Punkte derselben zweite Koordinate haben – die verbindenden Zeile ist horizontal.</span><span class="sxs-lookup"><span data-stu-id="daab9-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="daab9-112">Ellipse und des Rechtecks ändert auch allmählich von Rot in Blau, da die horizontale Koordinate von 0 bis 200 wird.</span><span class="sxs-lookup"><span data-stu-id="daab9-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="daab9-113">Die folgende Abbildung zeigt die Zeile, das die Ellipse und das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="daab9-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="daab9-114">Beachten Sie, dass der Farbverlauf wird wiederholt als die horizontale Koordinate 200 hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="daab9-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="daab9-115">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="daab9-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="daab9-116">Verwenden Sie horizontale lineare Farbverläufe</span><span class="sxs-lookup"><span data-stu-id="daab9-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="daab9-117">Übergeben Sie die nicht transparenten Rot und Blau als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="daab9-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="daab9-118">Im vorherigen Beispiel Ändern der Farbkomponenten linear beim Wechseln von einer horizontale Koordinate von 0 bis zu einer horizontalen Koordinate 200.</span><span class="sxs-lookup"><span data-stu-id="daab9-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="daab9-119">Beispielsweise wird ein Punkt, dessen erste Koordinate in der Mitte zwischen 0 und 200 ist, eine blaue Komponente aufweisen, in der Mitte zwischen 0 und 255 ist.</span><span class="sxs-lookup"><span data-stu-id="daab9-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="daab9-120"> können Sie, wie eine Farbe aus einer Kante eines Farbverlaufs zum anderen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="daab9-120"> allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="daab9-121">Angenommen Sie, Sie möchten einen Pinsel mit Farbverlauf erstellen, der sich in Rot entsprechend der folgenden Tabelle aus Schwarz ändert.</span><span class="sxs-lookup"><span data-stu-id="daab9-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="daab9-122">Horizontale Koordinate</span><span class="sxs-lookup"><span data-stu-id="daab9-122">Horizontal coordinate</span></span>|<span data-ttu-id="daab9-123">RGB-Komponenten</span><span class="sxs-lookup"><span data-stu-id="daab9-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="daab9-124">0</span><span class="sxs-lookup"><span data-stu-id="daab9-124">0</span></span>|<span data-ttu-id="daab9-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="daab9-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="daab9-126">40</span><span class="sxs-lookup"><span data-stu-id="daab9-126">40</span></span>|<span data-ttu-id="daab9-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="daab9-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="daab9-128">300</span><span class="sxs-lookup"><span data-stu-id="daab9-128">200</span></span>|<span data-ttu-id="daab9-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="daab9-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="daab9-130">Beachten Sie, dass Rotanteils zur Hälfte Intensität ist, wird die horizontale Koordinate nur 20 Prozent der Möglichkeit von 0 bis 200.</span><span class="sxs-lookup"><span data-stu-id="daab9-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="daab9-131">Im folgenden Beispiel wird die <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> Eigenschaft von einem <xref:System.Drawing.Drawing2D.LinearGradientBrush> Objekt, das drei relative Intensitäten mit drei relativen Positionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="daab9-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="daab9-132">Wie in der obigen Tabelle ist eine relative Intensität von 0,5 eine relative Position von 0,2 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="daab9-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="daab9-133">Der Code füllt eine Ellipse und ein Rechteck mit dem Farbverlaufspinsel.</span><span class="sxs-lookup"><span data-stu-id="daab9-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="daab9-134">Die folgende Abbildung zeigt das resultierende Ellipse und das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="daab9-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="daab9-135">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="daab9-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="daab9-136">Lineare Farbverläufe anpassen</span><span class="sxs-lookup"><span data-stu-id="daab9-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="daab9-137">Übergeben Sie die deckend Schwarz und Rot als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="daab9-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="daab9-138">Die Farbverläufe in den vorherigen Beispielen wurden horizontale; d. h. ändert sich die Farbe graduell ab, wie Sie auf einer horizontalen Linie verschieben.</span><span class="sxs-lookup"><span data-stu-id="daab9-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="daab9-139">Sie können auch die vertikale und diagonale Farbverläufe definieren.</span><span class="sxs-lookup"><span data-stu-id="daab9-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="daab9-140">Das folgende Beispiel übergibt die Punkte (0, 0) und (200, 100), um eine <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="daab9-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="daab9-141">Die Farbe Blau zugeordnet ist (0, 0), und die Farbe Grün zugeordnet ist (200, 100).</span><span class="sxs-lookup"><span data-stu-id="daab9-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="daab9-142">Eine Linie (mit Stiftbreite 10) und einer Ellipse, die sind mit der linearen Farbverlaufspinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="daab9-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="daab9-143">Die folgende Abbildung zeigt die Zeile und die Ellipse.</span><span class="sxs-lookup"><span data-stu-id="daab9-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="daab9-144">Beachten Sie, dass die Farbe in der Ellipse wechselt allmählich entlang einer Linie wird parallel zu der Position übergeben (0, 0) und (200, 100).</span><span class="sxs-lookup"><span data-stu-id="daab9-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="daab9-145">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="daab9-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="daab9-146">So erstellen diagonaler, linearer Farbverläufe</span><span class="sxs-lookup"><span data-stu-id="daab9-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="daab9-147">Übergeben Sie die nicht transparenten Blau und Grün als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="daab9-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="daab9-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daab9-148">See Also</span></span>  
 [<span data-ttu-id="daab9-149">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="daab9-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [<span data-ttu-id="daab9-150">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="daab9-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
