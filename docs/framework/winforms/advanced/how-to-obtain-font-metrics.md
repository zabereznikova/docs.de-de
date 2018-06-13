---
title: 'Gewusst wie: Abrufen von Schriftarteigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 3cc5ee303efe6c703a61eef6c7448979b487f6bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524208"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="f7a1b-102">Gewusst wie: Abrufen von Schriftarteigenschaften</span><span class="sxs-lookup"><span data-stu-id="f7a1b-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="f7a1b-103">Die <xref:System.Drawing.FontFamily> Klasse bietet die folgenden Methoden, die verschiedene Metriken für eine bestimmte Produktfamilie/Formatvorlage Kombination abrufen:</span><span class="sxs-lookup"><span data-stu-id="f7a1b-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="f7a1b-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="f7a1b-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="f7a1b-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="f7a1b-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="f7a1b-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="f7a1b-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="f7a1b-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="f7a1b-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="f7a1b-108">Von diesen Methoden zurückgegebenen Zahlen sind in Schriftentwurfseinheiten, sodass sie unabhängig von der Größe und die Einheiten eines bestimmten werden <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="f7a1b-109">Die folgende Abbildung zeigt die verschiedenen Metriken.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="f7a1b-110">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="f7a1b-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7a1b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7a1b-111">Example</span></span>  
 <span data-ttu-id="f7a1b-112">Das folgende Beispiel zeigt die Metriken für den Schriftschnitt der Schriftart Arial-Produktfamilie.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="f7a1b-113">Der Code erstellt zudem eine <xref:System.Drawing.Font> Objekt (basierend auf der Arial-Kategorie), mit der Größe von 16 Pixel und zeigt die Metriken (in Pixel) für diesen bestimmten <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="f7a1b-114">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="f7a1b-115">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="f7a1b-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="f7a1b-116">Beachten Sie die ersten beiden Zeilen der Ausgabe in der vorherigen Abbildung aus.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="f7a1b-117">Die <xref:System.Drawing.Font> Objekt zurückgibt, eine Größe von 16, und die <xref:System.Drawing.FontFamily> Objekt eine Geviertgröße von 2.048 zurück.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="f7a1b-118">Diese beiden Zahlen (16 und 2.048) sind der Schlüssel für die Konvertierung zwischen Schriftentwurfseinheiten und die Einheiten (in diesem Fall Pixel) von der <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="f7a1b-119">Beispielsweise können Sie den Anstieg von Entwurfseinheiten in Pixel wie folgt konvertieren:</span><span class="sxs-lookup"><span data-stu-id="f7a1b-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="f7a1b-120">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="f7a1b-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="f7a1b-121">Der folgende Code positioniert Text vertikal durch Festlegen der <xref:System.Drawing.PointF.Y%2A> Datenmember einer <xref:System.Drawing.PointF> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="f7a1b-122">Die y-Koordinate gestiegen `font.Height` für jede neue Zeile des Texts.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="f7a1b-123">Die <xref:System.Drawing.Font.Height%2A> Eigenschaft von einem <xref:System.Drawing.Font> Objekt gibt den Zeilenabstand (in Pixel) für diesen bestimmten <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="f7a1b-124">In diesem Beispiel wird die Anzahl von zurückgegebenen <xref:System.Drawing.Font.Height%2A> ist 19.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="f7a1b-125">Beachten Sie, dass dies die Anzahl (in eine ganze Zahl aufgerundet) erhalten, indem die Zeilenabstand Metrik in Pixel konvertiert identisch ist.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="f7a1b-126">Beachten Sie, dass die Gevierthöhe (so genannte Größe oder Em Größe) nicht die Summe der Versalhöhe und Unterlänge ist.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="f7a1b-127">Die Summe der Versalhöhe und Unterlänge wird die Zellenhöhe aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="f7a1b-128">Die Zellenhöhe minus der internen vorangestellten ist die Gevierthöhe gleich.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="f7a1b-129">Die Zellenhöhe plus der externen vorangestellten entspricht den Zeilenabstand.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f7a1b-130">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f7a1b-130">Compiling the Code</span></span>  
 <span data-ttu-id="f7a1b-131">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="f7a1b-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a1b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7a1b-132">See Also</span></span>  
 [<span data-ttu-id="f7a1b-133">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7a1b-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="f7a1b-134">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="f7a1b-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
