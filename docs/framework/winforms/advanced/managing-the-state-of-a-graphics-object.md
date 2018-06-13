---
title: Verwalten des Zustands eines Graphics-Objekts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525118"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="020be-102">Verwalten des Zustands eines Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="020be-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="020be-103">Die <xref:System.Drawing.Graphics> Klasse ist der Kern von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="020be-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="020be-104">Zum Zeichnen, erhalten Sie eine <xref:System.Drawing.Graphics> Objekt, dessen Eigenschaften festlegen und ihre Methoden aufrufen <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, usw.).</span><span class="sxs-lookup"><span data-stu-id="020be-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="020be-105">Im folgenden Beispiel wird die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode von einem <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="020be-106">Das erste Argument zu übergeben, um die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode ist ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="020be-107">Grafikzustand</span><span class="sxs-lookup"><span data-stu-id="020be-107">Graphics State</span></span>  
 <span data-ttu-id="020be-108">Ein <xref:System.Drawing.Graphics> Objekt bietet mehr als zeichnen Methoden wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A> und <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="020be-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="020be-109">Ein <xref:System.Drawing.Graphics> Objekt verwaltet auch Grafikzustand, die in die folgenden Kategorien unterteilt werden können:</span><span class="sxs-lookup"><span data-stu-id="020be-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="020be-110">Quality-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="020be-110">Quality settings</span></span>  
  
-   <span data-ttu-id="020be-111">Transformationen</span><span class="sxs-lookup"><span data-stu-id="020be-111">Transformations</span></span>  
  
-   <span data-ttu-id="020be-112">Clippingbereichs</span><span class="sxs-lookup"><span data-stu-id="020be-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="020be-113">Quality-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="020be-113">Quality Settings</span></span>  
 <span data-ttu-id="020be-114">Ein <xref:System.Drawing.Graphics> Objekt verfügt über verschiedene Eigenschaften, die die Qualität der Elemente beeinflussen, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="020be-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="020be-115">Sie können z. B. Festlegen der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft, um den Typ des Antialiasing (sofern vorhanden) auf einen Text angewendete anzugeben.</span><span class="sxs-lookup"><span data-stu-id="020be-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="020be-116">Andere Eigenschaften, die Qualität beeinflussen, sind <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, und <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="020be-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="020be-117">Im folgende Beispiel werden zwei Ellipsen, eine mit das Glättungsmodus gezeichnet <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> und eine mit das Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="020be-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="020be-118">Transformationen</span><span class="sxs-lookup"><span data-stu-id="020be-118">Transformations</span></span>  
 <span data-ttu-id="020be-119">Ein <xref:System.Drawing.Graphics> -Objekt verwaltet zwei Transformationen (Seite und www), die für alle Elemente, die gezeichnet wird, angewendet werden <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="020be-120">Alle affinen Transformationen kann in der globalen Transformation gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="020be-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="020be-121">Affine Transformationen gehören Skalierung, drehen, spiegeln, neigen und übersetzen.</span><span class="sxs-lookup"><span data-stu-id="020be-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="020be-122">Die Seitentransformation kann für die Skalierung sowie zum Ändern der Einheiten (z. B. in Pixel in Zoll) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="020be-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="020be-123">Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="020be-123">For more information, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="020be-124">Im folgenden Beispiel wird die World Transformation und der Seitentransformation ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="020be-125">Die globale Transformation wird auf einen Drehwinkel von 30 Grad festgelegt.</span><span class="sxs-lookup"><span data-stu-id="020be-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="020be-126">Die Seitentransformation wird festgelegt, sodass die Koordinaten der zweiten übergeben <xref:System.Drawing.Graphics.DrawEllipse%2A> als Millimeter statt Pixel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="020be-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="020be-127">Der Code enthält zwei identische Aufrufe der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="020be-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="020be-128">Die globale Transformation wird angewendet, mit dem ersten <xref:System.Drawing.Graphics.DrawEllipse%2A> Aufruf, und beide Transformationen (Seite und www) gelten für die zweite <xref:System.Drawing.Graphics.DrawEllipse%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="020be-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="020be-129">Die folgende Abbildung zeigt zwei Ellipsen.</span><span class="sxs-lookup"><span data-stu-id="020be-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="020be-130">Beachten Sie, dass die Drehung von 30 Grad, über den Ursprung des Koordinatensystems (linke obere Ecke des Clientbereichs), nicht über die Ressourcen der Schaltfläche mit den Auslassungszeichen ist.</span><span class="sxs-lookup"><span data-stu-id="020be-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="020be-131">Beachten Sie außerdem, dass die Stiftbreite 1 für die zweite Ellipse 1 Pixel für die erste Ellipse und 1 Millimeter bedeutet.</span><span class="sxs-lookup"><span data-stu-id="020be-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 <span data-ttu-id="020be-132">![Ovale](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span><span class="sxs-lookup"><span data-stu-id="020be-132">![Ovals](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span></span>  
  
### <a name="clipping-region"></a><span data-ttu-id="020be-133">Clippingbereichs</span><span class="sxs-lookup"><span data-stu-id="020be-133">Clipping Region</span></span>  
 <span data-ttu-id="020be-134">Ein <xref:System.Drawing.Graphics> -Objekt verwaltet einen Ausschneidebereich, die für alle Elemente, die gezeichnet wird, gilt <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="020be-135">Sie können den Ausschneidebereich festlegen, durch Aufrufen der <xref:System.Drawing.Graphics.SetClip%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="020be-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="020be-136">Das folgende Beispiel erstellt eine Region Plus geformten durch, die die Vereinigung zweier Rechtecke bilden.</span><span class="sxs-lookup"><span data-stu-id="020be-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="020be-137">Diese Region wird als den Ausschneidebereich festgelegt, dass ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="020be-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="020be-138">Der Code zeichnet dann zwei Zeilen, die auf das Innere des Clippingbereichs beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="020be-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="020be-139">Die folgende Abbildung zeigt die Zeilen abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="020be-139">The following illustration shows the clipped lines.</span></span>  
  
 <span data-ttu-id="020be-140">![Clip-Bereich beschränkt](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span><span class="sxs-lookup"><span data-stu-id="020be-140">![Limited Clip Region](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020be-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="020be-141">See Also</span></span>  
 [<span data-ttu-id="020be-142">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="020be-142">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="020be-143">Verwenden geschachtelter Grafikcontainer</span><span class="sxs-lookup"><span data-stu-id="020be-143">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
