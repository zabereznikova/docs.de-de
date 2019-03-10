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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703366"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="db004-102">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="db004-102">Using Fonts and Text</span></span>
<span data-ttu-id="db004-103">Es gibt mehrere Klassen von angebotenen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="db004-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="db004-104">Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> -Klasse verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A> Methoden, die Ihnen ermöglichen, verschiedene Funktionen des Texts an, wie Standort, umschließendes Rechteck, Schriftart und Format anzugeben.</span><span class="sxs-lookup"><span data-stu-id="db004-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="db004-105">Darüber hinaus können Sie zeichnen und messen Sie Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mit der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A> und <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> Methoden bereitgestellt werden, indem die `TextRenderer` Klasse.</span><span class="sxs-lookup"><span data-stu-id="db004-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="db004-106">Die [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Methoden auch ermöglichen es Ihnen an der Position, Schriftart und Format.</span><span class="sxs-lookup"><span data-stu-id="db004-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="db004-107">Wählen Sie entweder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Rendern von Text; allerdings [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet im Allgemeinen besser, Leistung und genauere Text messen.</span><span class="sxs-lookup"><span data-stu-id="db004-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="db004-108">Andere Klassen, die zum Rendern von Text beitragen sind `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, und `TextFormatFlags`.</span><span class="sxs-lookup"><span data-stu-id="db004-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db004-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="db004-109">In This Section</span></span>  
 [<span data-ttu-id="db004-110">Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="db004-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="db004-111">Veranschaulicht das Erstellen `Font` und `FontFamily` Objekte.</span><span class="sxs-lookup"><span data-stu-id="db004-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="db004-112">Vorgehensweise: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="db004-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="db004-113">Beschreibt die zum Zeichnen von Text in einem bestimmten Speicherort mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db004-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="db004-114">Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="db004-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="db004-115">Erläutert das Zeichnen von Text in einem Rechteck mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db004-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="db004-116">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="db004-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="db004-117">Veranschaulicht, wie [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text.</span><span class="sxs-lookup"><span data-stu-id="db004-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="db004-118">Vorgehensweise: Ausrichten von gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="db004-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="db004-119">Veranschaulicht das Formatieren von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Text.</span><span class="sxs-lookup"><span data-stu-id="db004-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="db004-120">Vorgehensweise: Erstellen von vertikalem Text</span><span class="sxs-lookup"><span data-stu-id="db004-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="db004-121">Beschreibt, wie Sie vertikal ausgerichteten Text mit zeichnen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db004-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="db004-122">Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="db004-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="db004-123">Veranschaulicht das Zeichnen von Text mit Tabstopps mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db004-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="db004-124">Vorgehensweise: Auflisten installierter Schriftarten</span><span class="sxs-lookup"><span data-stu-id="db004-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="db004-125">Es wird erläutert, wie die Namen der installierten Schriftarten aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="db004-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="db004-126">Vorgehensweise: Erstellen einer privaten Schriftartenauflistung</span><span class="sxs-lookup"><span data-stu-id="db004-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="db004-127">Beschreibt das Erstellen einer <xref:System.Drawing.Text.PrivateFontCollection> Objekt.</span><span class="sxs-lookup"><span data-stu-id="db004-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="db004-128">Vorgehensweise: Abrufen von Schriftarteigenschaften</span><span class="sxs-lookup"><span data-stu-id="db004-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="db004-129">Zeigt, wie zum Abrufen von Schriftarteigenschaften wie z. B. Zellaufstieg (Versalhöhe) und die Unterlänge.</span><span class="sxs-lookup"><span data-stu-id="db004-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="db004-130">Vorgehensweise: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="db004-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="db004-131">Erläutert, wie Antialiasing beim Zeichnen von Text.</span><span class="sxs-lookup"><span data-stu-id="db004-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="db004-132">Referenz</span><span class="sxs-lookup"><span data-stu-id="db004-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="db004-133">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="db004-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="db004-134">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="db004-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="db004-135">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="db004-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="db004-136">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="db004-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="db004-137">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="db004-137">Describes this class and contains links to all of its members.</span></span>
