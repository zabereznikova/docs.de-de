---
title: 'Vorgehensweise: Erstellen eines linearen Farbverlaufs'
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
ms.openlocfilehash: d9ceb10eb5990742271c8d952d9293807c21677a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696294"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="ad6b1-102">Vorgehensweise: Erstellen eines linearen Farbverlaufs</span><span class="sxs-lookup"><span data-stu-id="ad6b1-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ad6b1-103">bietet horizontale, vertikale und diagonale lineare Farbverläufe.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="ad6b1-104">Standardmäßig ändert sich die Farbe in einem linearen Farbverlauf einheitlich.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="ad6b1-105">Allerdings können Sie einen linearen Farbverlauf anpassen, um die Farbe auf nicht einheitliche Weise zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="ad6b1-106">Im folgenden Beispiel wird eine Zeile, einer Ellipse und ein Rechteck mit einem horizontalen linearen Farbverlaufspinsel.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="ad6b1-107">Die <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor empfängt vier Argumente: zwei Punkte und zwei Farben aus.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="ad6b1-108">Der erste Punkt (0, 10) bezieht sich auf die erste Farbe (Rot), und der zweite Punkt ("200", "10") bezieht sich auf die zweite Farbe (Blau).</span><span class="sxs-lookup"><span data-stu-id="ad6b1-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="ad6b1-109">Erwartungsgemäß, die Linie gezeichnet werden (0, 10), ("200", "10") ändert sich allmählich von Rot zu Blau.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="ad6b1-110">Die Werte 10 in die Punkte (50, 10) und (200, 10) sind nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="ad6b1-111">Wichtig ist, dass die beiden Punkte derselben zweite Koordinate haben – verbindenden Linie ist horizontal.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="ad6b1-112">Die Ellipse und des Rechtecks ändert sich auch allmählich von Rot zu Blau im Laufe der der horizontalen Koordinate von 0 bis 200.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="ad6b1-113">Die folgende Abbildung zeigt die Zeile, das die Ellipse und das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="ad6b1-114">Beachten Sie, dass der Farbverlauf wird wiederholt, wie die horizontale Koordinate 200 überschreitet.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="ad6b1-115">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="ad6b1-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="ad6b1-116">Verwenden Sie horizontale lineare Farbverläufe</span><span class="sxs-lookup"><span data-stu-id="ad6b1-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="ad6b1-117">Übergeben Sie das nicht transparente Rot und Blau als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="ad6b1-118">Im vorherigen Beispiel Ändern der Farbkomponenten linear wie die Umstellung von einer horizontalen Koordinate 0 auf eine horizontale Koordinate von 200.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="ad6b1-119">Beispielsweise müssen ein Punkt, dessen erste Koordinate in der Mitte zwischen 0 und 200 wird, eine blaue Komponente, die in der Mitte zwischen 0 und 255 ist.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ad6b1-120">ermöglicht Ihnen, wie eine Farbe aus einer Kante eines Farbverlaufs in den anderen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="ad6b1-121">Nehmen wir an, dass einen Pinsel mit Farbverlauf zu erstellen, der von Schwarz ändert sich in Rot gemäß der folgenden Tabelle werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="ad6b1-122">Horizontale Koordinate</span><span class="sxs-lookup"><span data-stu-id="ad6b1-122">Horizontal coordinate</span></span>|<span data-ttu-id="ad6b1-123">RGB-Komponenten</span><span class="sxs-lookup"><span data-stu-id="ad6b1-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="ad6b1-124">0</span><span class="sxs-lookup"><span data-stu-id="ad6b1-124">0</span></span>|<span data-ttu-id="ad6b1-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ad6b1-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="ad6b1-126">40</span><span class="sxs-lookup"><span data-stu-id="ad6b1-126">40</span></span>|<span data-ttu-id="ad6b1-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ad6b1-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="ad6b1-128">200</span><span class="sxs-lookup"><span data-stu-id="ad6b1-128">200</span></span>|<span data-ttu-id="ad6b1-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ad6b1-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="ad6b1-130">Beachten Sie, dass der Rotanteil auf halbe Intensität ist, wenn die horizontale Koordinate nur 20 Prozent der die Möglichkeit von 0 bis 200 ist.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="ad6b1-131">Im folgenden Beispiel wird die <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> Eigenschaft eine <xref:System.Drawing.Drawing2D.LinearGradientBrush> Objekt, das drei relative Intensitäten mit drei relativen Positionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="ad6b1-132">Wie in der obigen Tabelle wird die relative Intensität von 0,5 eine relative Position von 0,2 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="ad6b1-133">Der Code füllt einer Ellipse und ein Rechteck mit dem Pinsel mit Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="ad6b1-134">Die folgende Abbildung zeigt das resultierende Ellipse und das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="ad6b1-135">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="ad6b1-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="ad6b1-136">Lineare Farbverläufe anpassen</span><span class="sxs-lookup"><span data-stu-id="ad6b1-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="ad6b1-137">Übergeben Sie die deckend Schwarz und Rot als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="ad6b1-138">Die Farbverläufe in den vorherigen Beispielen wurden horizontale; d. h. ändert die Farbe allmählich während des Verschiebens auf einer horizontalen Linie im.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="ad6b1-139">Sie können auch die vertikale und diagonale Farbverläufe definieren.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="ad6b1-140">Das folgende Beispiel übergibt die Punkte ("0", "0") und (200, 100), um eine <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="ad6b1-141">Die Farbe Blau zugeordnet ist (0, 0), und die Farbe Grün zugeordnet ist (200, 100).</span><span class="sxs-lookup"><span data-stu-id="ad6b1-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="ad6b1-142">Eine Zeile (mit Stiftbreite 10) und eine Ellipse sind mit Pinsels mit linearem Farbverlauf gefüllt.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="ad6b1-143">Die folgende Abbildung zeigt die Zeile und der Ellipse.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="ad6b1-144">Beachten Sie, dass die Farbe in der Ellipse ändert sich allmählich entlang einer auf die Linie wird parallel zu der Zeile durchläuft (0, 0) und (200, 100).</span><span class="sxs-lookup"><span data-stu-id="ad6b1-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="ad6b1-145">![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="ad6b1-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="ad6b1-146">Zum Erstellen der diagonaler linearer Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="ad6b1-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="ad6b1-147">Übergeben Sie das nicht transparente Blau und Grün als die dritte und vierte Argument.</span><span class="sxs-lookup"><span data-stu-id="ad6b1-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ad6b1-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad6b1-148">See also</span></span>
- [<span data-ttu-id="ad6b1-149">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="ad6b1-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="ad6b1-150">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad6b1-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
