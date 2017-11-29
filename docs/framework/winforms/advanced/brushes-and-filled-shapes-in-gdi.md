---
title: "Pinsel und gefüllte Formen in GDI+"
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
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01d7359499c858ad7c4f1da2fa24f18e801bb324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="fdd4d-102">Pinsel und gefüllte Formen in GDI+</span><span class="sxs-lookup"><span data-stu-id="fdd4d-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="fdd4d-103">Eine geschlossene Form, z. B. ein Rechteck oder eine Ellipse besteht aus einer Gliederung und dem inneren.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="fdd4d-104">Die Kontur mit einem Stift gezeichnet, und das innere mit einem Pinsel gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fdd4d-105">bietet mehrere für die Innenflächen geschlossene Formen füllen: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, und <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-105"> provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="fdd4d-106">Alle diese Klassen erben von der <xref:System.Drawing.Brush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="fdd4d-107">Die folgende Abbildung zeigt ein Rechteck mit eines Pinsels in Volltonfarbe gefüllt und eine Ellipse, die mit einem Schraffurpinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="fdd4d-108">![Gefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-108">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="fdd4d-109">Einfarbig Pinsel</span><span class="sxs-lookup"><span data-stu-id="fdd4d-109">Solid Brushes</span></span>  
 <span data-ttu-id="fdd4d-110">Um eine geschlossene Form zu füllen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse und ein <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="fdd4d-111">Die Instanz von der <xref:System.Drawing.Graphics> Klasse enthält Methoden, wie z. B. <xref:System.Drawing.Graphics.FillRectangle%2A> und <xref:System.Drawing.Graphics.FillEllipse%2A>, und die <xref:System.Drawing.Brush> speichert Attribute für die Füllung, z. B. Farbe und Muster.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="fdd4d-112">Die <xref:System.Drawing.Brush> als eines der Argumente an die Füllmethode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="fdd4d-113">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die mit einer Volltonfarbe Rot füllen.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="fdd4d-114">Im vorherigen Beispiel ist der Pinsel, der vom Typ <xref:System.Drawing.SolidBrush>, erbt die <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="fdd4d-115">Schraffurpinsel</span><span class="sxs-lookup"><span data-stu-id="fdd4d-115">Hatch Brushes</span></span>  
 <span data-ttu-id="fdd4d-116">Wenn Sie eine Form mit einem Schraffurpinsel ausfüllen, geben Sie eine Vordergrundfarbe, eine Hintergrundfarbe und ein Schraffurart.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="fdd4d-117">Die Vordergrundfarbe ist die Farbe der Schraffur.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fdd4d-118">enthält mehr als 50 Schraffur Stile; sind die drei Stile in der folgenden Abbildung dargestellten <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, und <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-118"> provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="fdd4d-119">![Gefüllte Formen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-119">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="fdd4d-120">Strukturpinsel</span><span class="sxs-lookup"><span data-stu-id="fdd4d-120">Texture Brushes</span></span>  
 <span data-ttu-id="fdd4d-121">Mit einem Texturpinsel können Sie eine Form mit einem Muster, die in einer Bitmap gespeichert ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="fdd4d-122">Nehmen wir beispielsweise an, das folgende Bild befindet sich in einer Datenträgerdatei mit dem Namen `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="fdd4d-123">![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-123">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="fdd4d-124">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die durch die Wiederholung des Bilds in gespeicherten gefüllt `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="fdd4d-125">Die folgende Abbildung zeigt das ausgefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="fdd4d-126">![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-126">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="fdd4d-127">Farbverlaufspinsel</span><span class="sxs-lookup"><span data-stu-id="fdd4d-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fdd4d-128">bietet zwei Arten von Farbverlaufspinsel: linear und Pfad.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-128"> provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="fdd4d-129">Sie können einen linearen Farbverlaufspinsel verwenden, eine Form Farbe gefüllt, die Änderungen schrittweise, während Sie über die Form verschieben, horizontal, vertikal oder diagonal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="fdd4d-130">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ellipse, die mit einem horizontalen Farbverlaufspinsel zu füllen, die von Blau in Grün ändern, wie Sie vom linken Rand der Ellipse, die an den rechten Rand verschieben.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="fdd4d-131">Die folgende Abbildung zeigt das ausgefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="fdd4d-132">![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-132">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="fdd4d-133">Pfadfarbverlaufs kann konfiguriert werden, um Farbe zu ändern, wie Sie von der Mitte einer Form auf den Rand verschieben.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="fdd4d-134">![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-134">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="fdd4d-135">Pfad Farbverlaufspinsel sind sehr flexibel.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="fdd4d-136">Die Farbverlaufspinsel verwendet, um das Dreieck in der folgenden Abbildung Änderungen allmählich von Rot in der Mitte auf jedem der drei verschiedenen Farben an den Scheitelpunkten zu füllen.</span><span class="sxs-lookup"><span data-stu-id="fdd4d-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="fdd4d-137">![Gefüllt Form](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="fdd4d-137">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd4d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdd4d-138">See Also</span></span>  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [<span data-ttu-id="fdd4d-139">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="fdd4d-139">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="fdd4d-140">Gewusst wie: Zeichnen eines ausgefüllten Rechtecks in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdd4d-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [<span data-ttu-id="fdd4d-141">Gewusst wie: Zeichnen einer ausgefüllten Ellipse in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdd4d-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
