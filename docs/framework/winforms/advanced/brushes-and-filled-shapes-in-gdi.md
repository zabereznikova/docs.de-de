---
title: Pinsel und gefüllte Formen in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912231"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="6f8f5-102">Pinsel und gefüllte Formen in GDI+</span><span class="sxs-lookup"><span data-stu-id="6f8f5-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="6f8f5-103">Eine geschlossene Form, z. b. ein Rechteck oder eine Ellipse, besteht aus einem Umriss und einem inneren.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="6f8f5-104">Der Umriss wird mit einem Stift gezeichnet, und das Innere ist mit einem Pinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="6f8f5-105">GDI+ bietet verschiedene Pinsel Klassen zum Auffüllen des Inneren von geschlossenen Formen: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>und <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="6f8f5-106">Alle diese Klassen erben von der <xref:System.Drawing.Brush> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="6f8f5-107">Die folgende Abbildung zeigt ein Rechteck, das mit einem Pinsel gefüllt ist, und eine Ellipse mit einem Schraffurpinsel.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="6f8f5-108">![Gefüllte Formen](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="6f8f5-109">Vollpinsel</span><span class="sxs-lookup"><span data-stu-id="6f8f5-109">Solid Brushes</span></span>  
 <span data-ttu-id="6f8f5-110">Um eine geschlossene Form auszufüllen, benötigen Sie eine Instanz der <xref:System.Drawing.Graphics> -Klasse und eine <xref:System.Drawing.Brush>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="6f8f5-111">Die <xref:System.Drawing.Graphics> Instanz der <xref:System.Drawing.Graphics.FillRectangle%2A> -Klasse stellt Methoden bereit, wie z. b. <xref:System.Drawing.Brush> und <xref:System.Drawing.Graphics.FillEllipse%2A>, und speichert Attribute der Füllung, z. b. Farbe und Muster.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="6f8f5-112"><xref:System.Drawing.Brush> Wird als eines der Argumente an die Fill-Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="6f8f5-113">Im folgenden Codebeispiel wird gezeigt, wie eine Ellipse mit einer voll Tonfarbe gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="6f8f5-114">Im vorherigen Beispiel ist der Pinsel vom Typ <xref:System.Drawing.SolidBrush>, der von <xref:System.Drawing.Brush>erbt.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="6f8f5-115">Pinsel Schraffur</span><span class="sxs-lookup"><span data-stu-id="6f8f5-115">Hatch Brushes</span></span>  
 <span data-ttu-id="6f8f5-116">Wenn Sie eine Form mit einem Schraffurpinsel ausfüllen, geben Sie eine Vordergrundfarbe, eine Hintergrundfarbe und eine Schraffurart an.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="6f8f5-117">Die Vordergrundfarbe ist die Farbe der Schraffur.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="6f8f5-118">GDI+ bietet mehr als 50 Schraffurstile. die drei in der folgenden Abbildung gezeigten Stile sind <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>und <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="6f8f5-119">![Gefüllte Formen](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="6f8f5-120">Textur Pinsel</span><span class="sxs-lookup"><span data-stu-id="6f8f5-120">Texture Brushes</span></span>  
 <span data-ttu-id="6f8f5-121">Mit einem Textur Pinsel können Sie eine Form mit einem Muster ausfüllen, das in einer Bitmap gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="6f8f5-122">Angenommen, das folgende Bild ist in einer Datenträger Datei mit dem Namen `MyTexture.bmp`gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="6f8f5-123">![Gefüllte Form](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="6f8f5-124">Im folgenden Codebeispiel wird gezeigt, wie eine Ellipse ausgefüllt wird, indem das in `MyTexture.bmp`gespeicherte Bild wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="6f8f5-125">Die folgende Abbildung zeigt die gefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="6f8f5-126">![Gefüllte Form](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="6f8f5-127">Farbverlaufs Pinsel</span><span class="sxs-lookup"><span data-stu-id="6f8f5-127">Gradient Brushes</span></span>  
 <span data-ttu-id="6f8f5-128">GDI+ bietet zwei Arten von Farbverlaufs Pinsel: Linear und Path.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="6f8f5-129">Mit einem linearen Farbverlaufs Pinsel können Sie eine Form mit einer Farbe ausfüllen, die sich allmählich ändert, wenn Sie die Form horizontal, vertikal oder diagonal verschieben.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="6f8f5-130">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse mit einem horizontalen Farbverlaufs Pinsel ausgefüllt wird, der sich von blau in grün ändert, während Sie vom linken Rand der Ellipse zum rechten Rand wechseln.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="6f8f5-131">Die folgende Abbildung zeigt die gefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="6f8f5-132">![Gefüllte Form](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="6f8f5-133">Ein Pinsel mit dem Pfad Farbverlauf kann so konfiguriert werden, dass die Farbe geändert wird, wenn Sie von der Mitte einer Form zum Rand wechseln.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="6f8f5-134">![Gefüllte Form](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="6f8f5-135">Pfad Farbverlaufs Pinsel sind recht flexibel.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="6f8f5-136">Der Farbverlaufs Pinsel, der zum Ausfüllen des Dreiecks in der folgenden Abbildung verwendet wird, ändert sich allmählich von rot in der Mitte zu jeder der drei verschiedenen Farben in den Scheitel Punkten.</span><span class="sxs-lookup"><span data-stu-id="6f8f5-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="6f8f5-137">![Gefüllte Form](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="6f8f5-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8f5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f8f5-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="6f8f5-139">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="6f8f5-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="6f8f5-140">Vorgehensweise: Zeichnen eines ausgefüllten Rechtecks in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="6f8f5-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="6f8f5-141">Vorgehensweise: Zeichnen einer ausgefüllten Ellipse in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="6f8f5-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
