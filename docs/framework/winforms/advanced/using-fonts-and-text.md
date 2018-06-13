---
title: Verwenden von Schriftarten und Text
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526262"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="120d1-102">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="120d1-102">Using Fonts and Text</span></span>
<span data-ttu-id="120d1-103">Es gibt mehrere Klassen von Angeboten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="120d1-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="120d1-104">Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> -Klasse verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A> Methoden, die Ihnen ermöglichen, verschiedene Funktionen des Texts, z. B. der Speicherort, umgebende Rechteck, Schriftart und Format anzugeben.</span><span class="sxs-lookup"><span data-stu-id="120d1-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="120d1-105">Darüber hinaus können Sie zeichnen und Messen von Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mithilfe der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A> und <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> Methoden bereitgestellt werden, indem die `TextRenderer` Klasse.</span><span class="sxs-lookup"><span data-stu-id="120d1-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="120d1-106">Die [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Methoden ermöglichen auch die Position, Schriftart und Format angeben.</span><span class="sxs-lookup"><span data-stu-id="120d1-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="120d1-107">Stehen Ihnen beide [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Textrendering; allerdings [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet im Allgemeinen besser, Leistung und genauere Text messen.</span><span class="sxs-lookup"><span data-stu-id="120d1-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="120d1-108">Schließen Sie andere Klassen, die zum Rendern von Text beitragen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, und `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="120d1-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="120d1-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="120d1-109">In This Section</span></span>  
 [<span data-ttu-id="120d1-110">Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="120d1-110">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="120d1-111">Zeigt, wie `Font` und `FontFamily` Objekte.</span><span class="sxs-lookup"><span data-stu-id="120d1-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="120d1-112">Gewusst wie: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="120d1-112">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="120d1-113">Beschreibt, wie Zeichnen von Text in einem bestimmten Speicherort mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d1-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="120d1-114">Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="120d1-114">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="120d1-115">Erläutert das Zeichnen von Text in einem Rechteck von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d1-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="120d1-116">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="120d1-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="120d1-117">Veranschaulicht, wie [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text.</span><span class="sxs-lookup"><span data-stu-id="120d1-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="120d1-118">Gewusst wie: Ausrichten von gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="120d1-118">How to: Align Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 <span data-ttu-id="120d1-119">Veranschaulicht das Formatieren von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Text.</span><span class="sxs-lookup"><span data-stu-id="120d1-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="120d1-120">Gewusst wie: Erstellen von vertikalem Text</span><span class="sxs-lookup"><span data-stu-id="120d1-120">How to: Create Vertical Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 <span data-ttu-id="120d1-121">Beschreibt das Zeichnen von Texts mit vertikal ausgerichteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d1-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="120d1-122">Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="120d1-122">How to: Set Tab Stops in Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="120d1-123">Veranschaulicht das Zeichnen von Text mit Tabstopps mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120d1-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="120d1-124">Gewusst wie: Auflisten installierter Schriftarten</span><span class="sxs-lookup"><span data-stu-id="120d1-124">How to: Enumerate Installed Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="120d1-125">Erläutert, wie die Namen der installierten Schriftarten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="120d1-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="120d1-126">Gewusst wie: Erstellen einer privaten Schriftartenauflistung</span><span class="sxs-lookup"><span data-stu-id="120d1-126">How to: Create a Private Font Collection</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="120d1-127">Enthält Informationen zum Erstellen einer <xref:System.Drawing.Text.PrivateFontCollection> Objekt.</span><span class="sxs-lookup"><span data-stu-id="120d1-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="120d1-128">Gewusst wie: Abrufen von Schriftarteigenschaften</span><span class="sxs-lookup"><span data-stu-id="120d1-128">How to: Obtain Font Metrics</span></span>](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 <span data-ttu-id="120d1-129">Veranschaulicht das Abrufen von Schriftarteigenschaften wie Versalhöhe und Unterlänge.</span><span class="sxs-lookup"><span data-stu-id="120d1-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="120d1-130">Gewusst wie: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="120d1-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="120d1-131">Erklärt, wie Antialiasing beim Zeichnen von Text.</span><span class="sxs-lookup"><span data-stu-id="120d1-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="120d1-132">Referenz</span><span class="sxs-lookup"><span data-stu-id="120d1-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="120d1-133">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="120d1-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="120d1-134">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="120d1-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="120d1-135">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="120d1-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="120d1-136">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="120d1-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="120d1-137">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="120d1-137">Describes this class and contains links to all of its members.</span></span>
