---
title: Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 0e5ec2b89f015c7e061b59fea755eb368f1ac7a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341048"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="88183-102">Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element</span><span class="sxs-lookup"><span data-stu-id="88183-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="88183-103">In diesem Thema wird beschrieben, die <xref:System.Windows.Media.GlyphRun> Objekt und die <xref:System.Windows.Documents.Glyphs> Element.</span><span class="sxs-lookup"><span data-stu-id="88183-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="88183-104">Einführung in GlyphRun</span><span class="sxs-lookup"><span data-stu-id="88183-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="88183-105">bietet Unterstützung für erweiterten Text einschließlich Markup auf Symbolebene mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden, die abfangen und Text nach der Formatierung beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="88183-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="88183-106">Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.</span><span class="sxs-lookup"><span data-stu-id="88183-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="88183-107">Bildschirmanzeige von Dokumenten mit festem Format</span><span class="sxs-lookup"><span data-stu-id="88183-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="88183-108">Druckszenarios</span><span class="sxs-lookup"><span data-stu-id="88183-108">Print scenarios.</span></span>  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="88183-109">als Gerät Druckersprache.</span><span class="sxs-lookup"><span data-stu-id="88183-109">as a device printer language.</span></span>  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="88183-110">sein.</span><span class="sxs-lookup"><span data-stu-id="88183-110">.</span></span>  
  
    -   <span data-ttu-id="88183-111">Vorherige Druckertreiber, Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen an das feste Format</span><span class="sxs-lookup"><span data-stu-id="88183-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    -   <span data-ttu-id="88183-112">Druckerspooler-Format</span><span class="sxs-lookup"><span data-stu-id="88183-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="88183-113">Darstellung von Dokumenten mit festem Format, einschließlich Clients für vorherige Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und anderen Computergeräten</span><span class="sxs-lookup"><span data-stu-id="88183-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> <span data-ttu-id="88183-114">und <xref:System.Windows.Media.GlyphRun> sind für festem Format Dokumentpräsentation und Druckszenarios konzipiert.</span><span class="sxs-lookup"><span data-stu-id="88183-114">and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="88183-115">Stellt etliche Elemente für allgemeine Layout- und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien, z. B. <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="88183-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="88183-116">Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="88183-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="88183-117">Das GlyphRun-Objekt</span><span class="sxs-lookup"><span data-stu-id="88183-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="88183-118">Die <xref:System.Windows.Media.GlyphRun> -Objekt stellt eine Sequenz von Symbolen aus einer einzelnen Schriftart einer einzelnen Schriftfamilie mit einer einzelnen Größe und Renderingstil dar.</span><span class="sxs-lookup"><span data-stu-id="88183-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <xref:System.Windows.Media.GlyphRun> <span data-ttu-id="88183-119">enthält sowohl Schriftartdetails wie z. B. Glyphe <xref:System.Windows.Documents.Glyphs.Indices%2A> und einzelne Positionen.</span><span class="sxs-lookup"><span data-stu-id="88183-119">includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="88183-120">Es enthält auch die ursprünglichen [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Codepunkte von Informationen zur Zuordnung Zeichen-zu-Symbol sowie pro Zeichen und pro-Symbol-Flags der ausführungslauf generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="88183-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <xref:System.Windows.Media.GlyphRun> <span data-ttu-id="88183-121">verfügt über eine entsprechende allgemeine <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="88183-121">has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <xref:System.Windows.Documents.Glyphs> <span data-ttu-id="88183-122">kann verwendet werden, in der Elementstruktur und im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup zum darstellen <xref:System.Windows.Media.GlyphRun> Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="88183-122">can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="88183-123">Das Glyphs-Element</span><span class="sxs-lookup"><span data-stu-id="88183-123">The Glyphs Element</span></span>  
 <span data-ttu-id="88183-124">Die <xref:System.Windows.Documents.Glyphs> -Element stellt dar, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88183-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="88183-125">Die folgende Markupsyntax wird zum Beschreiben der <xref:System.Windows.Documents.Glyphs> Element.</span><span class="sxs-lookup"><span data-stu-id="88183-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="88183-126">Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.</span><span class="sxs-lookup"><span data-stu-id="88183-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="88183-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="88183-127">Property</span></span>|<span data-ttu-id="88183-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88183-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="88183-129">Gibt an, eine Ressourcen-ID: Dateiname, Web- [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], oder Ressourcenverweis in der Anwendung .exe oder Container.</span><span class="sxs-lookup"><span data-stu-id="88183-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="88183-130">Gibt den Schriftgrad in Zeichenoberflächeneinheiten an (Der Standardwert ist .96 Zoll)</span><span class="sxs-lookup"><span data-stu-id="88183-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="88183-131">Gibt Flags für Fett-und Kursivdruck an</span><span class="sxs-lookup"><span data-stu-id="88183-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="88183-132">Gibt die bidirektionale Layoutebene an.</span><span class="sxs-lookup"><span data-stu-id="88183-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="88183-133">Gerade Werte und Nullwerte implizieren Layout von links nach rechts; ungerade Werte implizieren Layout von rechts nach links.</span><span class="sxs-lookup"><span data-stu-id="88183-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="88183-134">Indices-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="88183-134">Indices property</span></span>  
 <span data-ttu-id="88183-135">Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft ist eine Zeichenfolge der Symbolspezifikationen.</span><span class="sxs-lookup"><span data-stu-id="88183-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="88183-136">Wenn ein Symbol ein einzelnes Cluster bildet, wird der Spezifikation auf des ersten Symbols im Cluster die Spezifikation vorangestellt, wie viele Symbole und wie viele Codepunkte sich kombinieren, um das Cluster zu bilden.</span><span class="sxs-lookup"><span data-stu-id="88183-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="88183-137">Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft, die in einer Zeichenfolge die folgenden Eigenschaften werden erfasst.</span><span class="sxs-lookup"><span data-stu-id="88183-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
-   <span data-ttu-id="88183-138">Symbolindizes</span><span class="sxs-lookup"><span data-stu-id="88183-138">Glyph indices</span></span>  
  
-   <span data-ttu-id="88183-139">Symboldikten</span><span class="sxs-lookup"><span data-stu-id="88183-139">Glyph advance widths</span></span>  
  
-   <span data-ttu-id="88183-140">Kombinieren von Glyphen-Anlagevektors</span><span class="sxs-lookup"><span data-stu-id="88183-140">Combining glyph attachment vectors</span></span>  
  
-   <span data-ttu-id="88183-141">Clusterzuordnung zwischen Codepunkten und Glyphen</span><span class="sxs-lookup"><span data-stu-id="88183-141">Cluster mapping from code points to glyphs</span></span>  
  
-   <span data-ttu-id="88183-142">Symbolflags</span><span class="sxs-lookup"><span data-stu-id="88183-142">Glyph flags</span></span>  
  
 <span data-ttu-id="88183-143">Jede Symbolspezifikation hat folgendes Format:</span><span class="sxs-lookup"><span data-stu-id="88183-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="88183-144">Symbolmetriken</span><span class="sxs-lookup"><span data-stu-id="88183-144">Glyph Metrics</span></span>  
 <span data-ttu-id="88183-145">Jedes Symbol definiert Metriken, die angeben, wie sie mit anderen entspricht <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="88183-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="88183-146">Die folgende Abbildung definiert die verschiedenen typografischen Eigenschaften von zwei unterschiedlichen Symbolen.</span><span class="sxs-lookup"><span data-stu-id="88183-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="88183-147">![Diagramm der Symbol-Maßangaben](./media/glyph-example.png "Glyph_example")</span><span class="sxs-lookup"><span data-stu-id="88183-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="88183-148">Symbol-Markup</span><span class="sxs-lookup"><span data-stu-id="88183-148">Glyphs Markup</span></span>  
 <span data-ttu-id="88183-149">Im folgenden Codebeispiel wird veranschaulicht, wie Sie verschiedene Eigenschaften des verwenden die <xref:System.Windows.Documents.Glyphs> Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88183-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="88183-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88183-150">See also</span></span>

- [<span data-ttu-id="88183-151">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="88183-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="88183-152">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="88183-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="88183-153">Text</span><span class="sxs-lookup"><span data-stu-id="88183-153">Text</span></span>](optimizing-performance-text.md)
