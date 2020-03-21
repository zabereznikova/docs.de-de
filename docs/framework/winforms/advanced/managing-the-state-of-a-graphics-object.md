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
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182453"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="83759-102">Verwalten des Zustands eines Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="83759-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="83759-103">Die <xref:System.Drawing.Graphics> Klasse ist das Herzstück von GDI+.</span><span class="sxs-lookup"><span data-stu-id="83759-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="83759-104">Um etwas zu zeichnen, erhalten Sie <xref:System.Drawing.Graphics> ein Objekt, <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>legen <xref:System.Drawing.Graphics.DrawString%2A>seine Eigenschaften fest und rufen seine Methoden , , und dergleichen auf.</span><span class="sxs-lookup"><span data-stu-id="83759-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="83759-105">Im folgenden Beispiel <xref:System.Drawing.Graphics.DrawRectangle%2A> wird <xref:System.Drawing.Graphics> die Methode eines Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="83759-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="83759-106">Das erste Argument, <xref:System.Drawing.Graphics.DrawRectangle%2A> das <xref:System.Drawing.Pen> an die Methode übergeben wird, ist ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="83759-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="83759-107">Grafikzustand</span><span class="sxs-lookup"><span data-stu-id="83759-107">Graphics State</span></span>  
 <span data-ttu-id="83759-108">Ein <xref:System.Drawing.Graphics> Objekt stellt mehr als nur <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A>Zeichenmethoden bereit, z. B. und .</span><span class="sxs-lookup"><span data-stu-id="83759-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="83759-109">Ein <xref:System.Drawing.Graphics> Objekt behält auch den Grafikstatus bei, der in die folgenden Kategorien unterteilt werden kann:</span><span class="sxs-lookup"><span data-stu-id="83759-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="83759-110">Qualitätseinstellungen</span><span class="sxs-lookup"><span data-stu-id="83759-110">Quality settings</span></span>  
  
- <span data-ttu-id="83759-111">Transformationen</span><span class="sxs-lookup"><span data-stu-id="83759-111">Transformations</span></span>  
  
- <span data-ttu-id="83759-112">Clipping-Bereich</span><span class="sxs-lookup"><span data-stu-id="83759-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="83759-113">Qualitätseinstellungen</span><span class="sxs-lookup"><span data-stu-id="83759-113">Quality Settings</span></span>  
 <span data-ttu-id="83759-114">Ein <xref:System.Drawing.Graphics> Objekt verfügt über mehrere Eigenschaften, die die Qualität der gezeichneten Elemente beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="83759-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="83759-115">Sie können die <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft beispielsweise so festlegen, dass der Typ der Antialiasing (falls vorhanden) angegeben wird, die auf Text angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="83759-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="83759-116">Andere Eigenschaften, die <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.CompositingMode%2A>die <xref:System.Drawing.Graphics.CompositingQuality%2A>Qualität <xref:System.Drawing.Graphics.InterpolationMode%2A>beeinflussen, sind , , und .</span><span class="sxs-lookup"><span data-stu-id="83759-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="83759-117">Im folgenden Beispiel werden zwei Ellipsen gezeichnet, <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> eine mit dem Glättungsmodus und eine mit dem <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>Aufglättungsmodus:</span><span class="sxs-lookup"><span data-stu-id="83759-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="83759-118">Transformationen</span><span class="sxs-lookup"><span data-stu-id="83759-118">Transformations</span></span>  
 <span data-ttu-id="83759-119">Ein <xref:System.Drawing.Graphics> Objekt verwaltet zwei Transformationen (Welt und Seite), die <xref:System.Drawing.Graphics> auf alle von diesem Objekt gezeichneten Elemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="83759-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="83759-120">Jede affine Transformation kann in der Welttransformation gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="83759-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="83759-121">Zu den feinen Transformationen gehören Skalierung, Drehen, Reflektieren, Verzerren und Übersetzen.</span><span class="sxs-lookup"><span data-stu-id="83759-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="83759-122">Die Seitentransformation kann zum Skalieren und zum Ändern von Einheiten (z. B. Pixel in Zoll) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83759-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="83759-123">Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="83759-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="83759-124">Im folgenden Beispiel werden die Welt- <xref:System.Drawing.Graphics> und Seitentransformationen eines Objekts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83759-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="83759-125">Die Welttransformation ist auf eine 30-Grad-Rotation eingestellt.</span><span class="sxs-lookup"><span data-stu-id="83759-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="83759-126">Die Seitentransformation ist so eingestellt, dass <xref:System.Drawing.Graphics.DrawEllipse%2A> die an die Zweite übergebenen Koordinaten als Millimeter anstelle von Pixeln behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="83759-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="83759-127">Der Code führt zwei <xref:System.Drawing.Graphics.DrawEllipse%2A> identische Aufrufe der Methode aus.</span><span class="sxs-lookup"><span data-stu-id="83759-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="83759-128">Die Welttransformation wird auf <xref:System.Drawing.Graphics.DrawEllipse%2A> den ersten Aufruf angewendet, und beide Transformationen <xref:System.Drawing.Graphics.DrawEllipse%2A> (Welt und Seite) werden auf den zweiten Aufruf angewendet.</span><span class="sxs-lookup"><span data-stu-id="83759-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="83759-129">Die folgende Abbildung zeigt die beiden Ellipsen.</span><span class="sxs-lookup"><span data-stu-id="83759-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="83759-130">Beachten Sie, dass es bei der 30-Grad-Drehung um den Ursprung des Koordinatensystems (obere linke Ecke des Clientbereichs) und nicht um die Mittelpunkte der Ellipsen geht.</span><span class="sxs-lookup"><span data-stu-id="83759-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="83759-131">Beachten Sie auch, dass die Stiftbreite von 1 1 Pixel für die erste Ellipse und 1 Millimeter für die zweite Ellipse bedeutet.</span><span class="sxs-lookup"><span data-stu-id="83759-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Abbildung, die zwei Ellipsen zeigt: Drehung und Stiftbreite.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="83759-133">Clipping-Region</span><span class="sxs-lookup"><span data-stu-id="83759-133">Clipping Region</span></span>  
 <span data-ttu-id="83759-134">Ein <xref:System.Drawing.Graphics> Objekt verwaltet einen Zuschneidebereich, der <xref:System.Drawing.Graphics> für alle von diesem Objekt gezeichneten Elemente gilt.</span><span class="sxs-lookup"><span data-stu-id="83759-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="83759-135">Sie können den Clipping-Bereich <xref:System.Drawing.Graphics.SetClip%2A> festlegen, indem Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="83759-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="83759-136">Im folgenden Beispiel wird ein plusförmiger Bereich erstellt, indem die Vereinigung von zwei Rechtecken gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="83759-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="83759-137">Dieser Bereich wird als Clipping-Bereich eines <xref:System.Drawing.Graphics> Objekts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83759-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="83759-138">Anschließend zeichnet der Code zwei Zeilen, die auf das Innere des Clipping-Bereichs beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="83759-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="83759-139">Die folgende Abbildung zeigt die abgeschnittenen Linien:</span><span class="sxs-lookup"><span data-stu-id="83759-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Diagramm, das den begrenzten Clipbereich anzeigt.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="83759-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83759-141">See also</span></span>

- [<span data-ttu-id="83759-142">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83759-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="83759-143">Verwenden geschachtelter Grafikcontainer</span><span class="sxs-lookup"><span data-stu-id="83759-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
