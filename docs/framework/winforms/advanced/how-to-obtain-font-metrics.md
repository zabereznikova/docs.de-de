---
title: 'Vorgehensweise: Abrufen von Schriftarteigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 75177b609f14d335aa57aba77d647827f50a8692
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881854"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="aaf37-102">Vorgehensweise: Abrufen von Schriftarteigenschaften</span><span class="sxs-lookup"><span data-stu-id="aaf37-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="aaf37-103">Die <xref:System.Drawing.FontFamily> Klasse stellt die folgenden Methoden, die verschiedene Metriken für eine bestimmte Produktfamilie / "Style" abrufen:</span><span class="sxs-lookup"><span data-stu-id="aaf37-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="aaf37-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="aaf37-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="aaf37-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="aaf37-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="aaf37-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="aaf37-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="aaf37-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="aaf37-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="aaf37-108">Die Zahlen, die von diesen Methoden zurückgegeben werden, sodass sie unabhängig von Größe und Einheiten eines bestimmten sind in Schriftentwurfseinheiten <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aaf37-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="aaf37-109">Die folgende Abbildung zeigt die verschiedenen Metriken:</span><span class="sxs-lookup"><span data-stu-id="aaf37-109">The following illustration shows the various metrics:</span></span>
  
 ![Abbildung der Schriftarteigenschaften: Versalhöhe gradientenverfahren und Zeilenabstand.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="aaf37-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aaf37-111">Example</span></span>  
 <span data-ttu-id="aaf37-112">Das folgende Beispiel zeigt die Metriken für den Schriftschnitt der Schriftart Arial-Familie.</span><span class="sxs-lookup"><span data-stu-id="aaf37-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="aaf37-113">Der Code erstellt außerdem eine <xref:System.Drawing.Font> Objekt (basierend auf der Arial-Kategorie), mit der Größe von 16 Pixel und zeigt die Metriken (in Pixel) für die jeweilige <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aaf37-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="aaf37-114">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes:</span><span class="sxs-lookup"><span data-stu-id="aaf37-114">The following illustration shows the output of the example code:</span></span>
  
 ![Ausgabe von Beispiel der Schriftart Arial Metriken.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="aaf37-116">Beachten Sie die ersten beiden Zeilen der Ausgabe in der vorherigen Abbildung.</span><span class="sxs-lookup"><span data-stu-id="aaf37-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="aaf37-117">Die <xref:System.Drawing.Font> -Objekt zurückgibt, eine Größe von 16, und die <xref:System.Drawing.FontFamily> Objekt eine Geviertgröße von 2.048 zurück.</span><span class="sxs-lookup"><span data-stu-id="aaf37-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="aaf37-118">Diese beiden Zahlen (16 und 2.048) sind der Schlüssel zum Konvertieren zwischen Schriftentwurfseinheiten und die Einheiten (in diesem Fall Pixel), der die <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aaf37-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="aaf37-119">Beispielsweise können Sie die Versalhöhe aus Entwurfseinheiten an Pixeln wie folgt konvertieren:</span><span class="sxs-lookup"><span data-stu-id="aaf37-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![Formel, die mit die Konvertierung von Entwurfseinheiten in Pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="aaf37-121">Der folgende Code Text wird vertikal positioniert, durch Festlegen der <xref:System.Drawing.PointF.Y%2A> Datenmember einer <xref:System.Drawing.PointF> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aaf37-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="aaf37-122">Die y-Koordinate wird erhöht, `font.Height` für jede neue Zeile des Texts.</span><span class="sxs-lookup"><span data-stu-id="aaf37-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="aaf37-123">Die <xref:System.Drawing.Font.Height%2A> Eigenschaft eine <xref:System.Drawing.Font> Objekts gibt den Zeilenabstand (in Pixel) für die jeweilige <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="aaf37-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="aaf37-124">In diesem Beispiel wird die Anzahl von zurückgegebenen <xref:System.Drawing.Font.Height%2A> ist 19.</span><span class="sxs-lookup"><span data-stu-id="aaf37-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="aaf37-125">Beachten Sie, dass dies die Anzahl (in eine ganze Zahl aufgerundet) abgerufen, indem Sie die Metrik Zeilenabstand in Pixel konvertiert identisch ist.</span><span class="sxs-lookup"><span data-stu-id="aaf37-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="aaf37-126">Beachten Sie, dass die Gevierthöhe (auch als Größe oder die Em-Größe) nicht die Summe der Versalhöhe und die Unterlänge ist.</span><span class="sxs-lookup"><span data-stu-id="aaf37-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="aaf37-127">Die Summe der Versalhöhe und die Unterlänge wird die Zellenhöhe aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aaf37-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="aaf37-128">Die Zellenhöhe minus der internen vorangestellten ist die Gevierthöhe gleich.</span><span class="sxs-lookup"><span data-stu-id="aaf37-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="aaf37-129">Die Zellenhöhe sowie der externe Abstand ist gleich den Zeilenabstand.</span><span class="sxs-lookup"><span data-stu-id="aaf37-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aaf37-130">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="aaf37-130">Compiling the Code</span></span>  
 <span data-ttu-id="aaf37-131">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="aaf37-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf37-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaf37-132">See also</span></span>

- [<span data-ttu-id="aaf37-133">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aaf37-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="aaf37-134">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="aaf37-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
