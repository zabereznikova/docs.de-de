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
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181962"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="7c229-102">Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element</span><span class="sxs-lookup"><span data-stu-id="7c229-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="7c229-103">In diesem <xref:System.Windows.Media.GlyphRun> Thema werden <xref:System.Windows.Documents.Glyphs> das Objekt und das Element beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c229-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="7c229-104">Einführung in GlyphRun</span><span class="sxs-lookup"><span data-stu-id="7c229-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="7c229-105">bietet erweiterte Textunterstützung, einschließlich Markup auf <xref:System.Windows.Documents.Glyphs> Glyphenebene mit direktem Zugriff für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="7c229-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="7c229-106">Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.</span><span class="sxs-lookup"><span data-stu-id="7c229-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="7c229-107">Bildschirmanzeige von Dokumenten mit festem Format</span><span class="sxs-lookup"><span data-stu-id="7c229-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="7c229-108">Druckszenarios</span><span class="sxs-lookup"><span data-stu-id="7c229-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="7c229-109">als Druckersprache für Geräte</span><span class="sxs-lookup"><span data-stu-id="7c229-109">as a device printer language.</span></span>  
  
    - <span data-ttu-id="7c229-110">Microsoft XPS Document Writer.</span><span class="sxs-lookup"><span data-stu-id="7c229-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="7c229-111">Vorherige Druckertreiber, Ausgabe von Win32-Anwendungen in das feste Format.</span><span class="sxs-lookup"><span data-stu-id="7c229-111">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="7c229-112">Druckerspooler-Format</span><span class="sxs-lookup"><span data-stu-id="7c229-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="7c229-113">Dokumentdarstellung im Festformat, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.</span><span class="sxs-lookup"><span data-stu-id="7c229-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c229-114"><xref:System.Windows.Documents.Glyphs>und <xref:System.Windows.Media.GlyphRun> sind für Dokumentpräsentations- und Druckszenarien im festformatigen Format konzipiert.</span><span class="sxs-lookup"><span data-stu-id="7c229-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="7c229-115">bietet mehrere Elemente für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] allgemeines <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>Layout und Szenarien wie und .</span><span class="sxs-lookup"><span data-stu-id="7c229-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="7c229-116">Weitere Informationen zu [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Layout und Szenarien finden Sie unter [Typografie in WPF](typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="7c229-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a><span data-ttu-id="7c229-117">Das GlyphRun-Objekt</span><span class="sxs-lookup"><span data-stu-id="7c229-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="7c229-118">Das <xref:System.Windows.Media.GlyphRun> Objekt stellt eine Sequenz von Glyphen von einer einzelnen Fläche einer einzelnen Schriftart in einer einzelnen Größe und mit einem einzelnen Renderstil dar.</span><span class="sxs-lookup"><span data-stu-id="7c229-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="7c229-119"><xref:System.Windows.Media.GlyphRun>enthält sowohl Schriftartdetails <xref:System.Windows.Documents.Glyphs.Indices%2A> wie Glyphen- als auch einzelne Glyphenpositionen.</span><span class="sxs-lookup"><span data-stu-id="7c229-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="7c229-120">Es enthält auch die ursprünglichen Unicode-Codepunkte, aus dem die Ausführung generiert wurde, Zeichen-zu-Glyph-Pufferoffset-Zuordnungsinformationen sowie Pro-Zeichen- und Pro-Glyph-Flags.</span><span class="sxs-lookup"><span data-stu-id="7c229-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="7c229-121"><xref:System.Windows.Media.GlyphRun>hat eine entsprechende <xref:System.Windows.FrameworkElement>High-Level , <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="7c229-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="7c229-122"><xref:System.Windows.Documents.Glyphs>kann in der Elementstruktur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und in <xref:System.Windows.Media.GlyphRun> Markup verwendet werden, um die Ausgabe darzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c229-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a><span data-ttu-id="7c229-123">Das Glyphs-Element</span><span class="sxs-lookup"><span data-stu-id="7c229-123">The Glyphs Element</span></span>  
 <span data-ttu-id="7c229-124">Das <xref:System.Windows.Documents.Glyphs> Element stellt die <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Ausgabe einer in dar.</span><span class="sxs-lookup"><span data-stu-id="7c229-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="7c229-125">Die folgende Markupsyntax wird <xref:System.Windows.Documents.Glyphs> verwendet, um das Element zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="7c229-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="7c229-126">Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.</span><span class="sxs-lookup"><span data-stu-id="7c229-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="7c229-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7c229-127">Property</span></span>|<span data-ttu-id="7c229-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c229-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="7c229-129">Gibt einen Ressourcenbezeichner an: Dateiname, Web Uniform Resource Identifier (URI) oder Ressourcenverweis in der Anwendung .exe oder container.</span><span class="sxs-lookup"><span data-stu-id="7c229-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="7c229-130">Gibt den Schriftgrad in Zeichenoberflächeneinheiten an (Der Standardwert ist .96 Zoll)</span><span class="sxs-lookup"><span data-stu-id="7c229-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="7c229-131">Gibt Flags für Fett-und Kursivdruck an</span><span class="sxs-lookup"><span data-stu-id="7c229-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="7c229-132">Gibt die bidirektionale Layoutebene an.</span><span class="sxs-lookup"><span data-stu-id="7c229-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="7c229-133">Gerade Werte und Nullwerte implizieren Layout von links nach rechts; ungerade Werte implizieren Layout von rechts nach links.</span><span class="sxs-lookup"><span data-stu-id="7c229-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a><span data-ttu-id="7c229-134">Indices-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7c229-134">Indices property</span></span>  
 <span data-ttu-id="7c229-135">Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft ist eine Zeichenfolge mit Glyphenspezifikationen.</span><span class="sxs-lookup"><span data-stu-id="7c229-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="7c229-136">Wenn ein Symbol ein einzelnes Cluster bildet, wird der Spezifikation auf des ersten Symbols im Cluster die Spezifikation vorangestellt, wie viele Symbole und wie viele Codepunkte sich kombinieren, um das Cluster zu bilden.</span><span class="sxs-lookup"><span data-stu-id="7c229-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="7c229-137">Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft sammelt in einer Zeichenfolge die folgenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7c229-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="7c229-138">Symbolindizes</span><span class="sxs-lookup"><span data-stu-id="7c229-138">Glyph indices</span></span>  
  
- <span data-ttu-id="7c229-139">Symboldikten</span><span class="sxs-lookup"><span data-stu-id="7c229-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="7c229-140">Kombinieren von Glyphen-Anlagevektors</span><span class="sxs-lookup"><span data-stu-id="7c229-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="7c229-141">Clusterzuordnung zwischen Codepunkten und Glyphen</span><span class="sxs-lookup"><span data-stu-id="7c229-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="7c229-142">Symbolflags</span><span class="sxs-lookup"><span data-stu-id="7c229-142">Glyph flags</span></span>  
  
 <span data-ttu-id="7c229-143">Jede Symbolspezifikation hat folgendes Format:</span><span class="sxs-lookup"><span data-stu-id="7c229-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a><span data-ttu-id="7c229-144">Symbolmetriken</span><span class="sxs-lookup"><span data-stu-id="7c229-144">Glyph Metrics</span></span>  
 <span data-ttu-id="7c229-145">Jede Glyphe definiert Metriken, die angeben, <xref:System.Windows.Documents.Glyphs>wie sie an anderen ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="7c229-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="7c229-146">Die folgende Abbildung definiert die verschiedenen typografischen Eigenschaften von zwei unterschiedlichen Symbolen.</span><span class="sxs-lookup"><span data-stu-id="7c229-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="7c229-147">![Diagramm der Symbolmaßangaben](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="7c229-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a><span data-ttu-id="7c229-148">Symbol-Markup</span><span class="sxs-lookup"><span data-stu-id="7c229-148">Glyphs Markup</span></span>  
 <span data-ttu-id="7c229-149">Das folgende Codebeispiel zeigt, wie <xref:System.Windows.Documents.Glyphs> verschiedene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Eigenschaften des Elements in verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c229-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c229-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c229-150">See also</span></span>

- [<span data-ttu-id="7c229-151">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="7c229-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="7c229-152">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="7c229-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7c229-153">Text</span><span class="sxs-lookup"><span data-stu-id="7c229-153">Text</span></span>](optimizing-performance-text.md)
