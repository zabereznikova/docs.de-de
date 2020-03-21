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
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element
In diesem <xref:System.Windows.Media.GlyphRun> Thema werden <xref:System.Windows.Documents.Glyphs> das Objekt und das Element beschrieben.  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a>Einführung in GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet erweiterte Textunterstützung, einschließlich Markup auf <xref:System.Windows.Documents.Glyphs> Glyphenebene mit direktem Zugriff für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.  
  
1. Bildschirmanzeige von Dokumenten mit festem Format  
  
2. Druckszenarios  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte  
  
    - Microsoft XPS Document Writer.  
  
    - Vorherige Druckertreiber, Ausgabe von Win32-Anwendungen in das feste Format.  
  
    - Druckerspooler-Format  
  
3. Dokumentdarstellung im Festformat, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>und <xref:System.Windows.Media.GlyphRun> sind für Dokumentpräsentations- und Druckszenarien im festformatigen Format konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet mehrere Elemente für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] allgemeines <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>Layout und Szenarien wie und . Weitere Informationen zu [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Layout und Szenarien finden Sie unter [Typografie in WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a>Das GlyphRun-Objekt  
 Das <xref:System.Windows.Media.GlyphRun> Objekt stellt eine Sequenz von Glyphen von einer einzelnen Fläche einer einzelnen Schriftart in einer einzelnen Größe und mit einem einzelnen Renderstil dar.  
  
 <xref:System.Windows.Media.GlyphRun>enthält sowohl Schriftartdetails <xref:System.Windows.Documents.Glyphs.Indices%2A> wie Glyphen- als auch einzelne Glyphenpositionen. Es enthält auch die ursprünglichen Unicode-Codepunkte, aus dem die Ausführung generiert wurde, Zeichen-zu-Glyph-Pufferoffset-Zuordnungsinformationen sowie Pro-Zeichen- und Pro-Glyph-Flags.  
  
 <xref:System.Windows.Media.GlyphRun>hat eine entsprechende <xref:System.Windows.FrameworkElement>High-Level , <xref:System.Windows.Documents.Glyphs>. <xref:System.Windows.Documents.Glyphs>kann in der Elementstruktur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und in <xref:System.Windows.Media.GlyphRun> Markup verwendet werden, um die Ausgabe darzustellen.  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a>Das Glyphs-Element  
 Das <xref:System.Windows.Documents.Glyphs> Element stellt die <xref:System.Windows.Media.GlyphRun> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Ausgabe einer in dar. Die folgende Markupsyntax wird <xref:System.Windows.Documents.Glyphs> verwendet, um das Element zu beschreiben.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Gibt einen Ressourcenbezeichner an: Dateiname, Web Uniform Resource Identifier (URI) oder Ressourcenverweis in der Anwendung .exe oder container.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Gibt den Schriftgrad in Zeichenoberflächeneinheiten an (Der Standardwert ist .96 Zoll)|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Gibt Flags für Fett-und Kursivdruck an|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Gibt die bidirektionale Layoutebene an. Gerade Werte und Nullwerte implizieren Layout von links nach rechts; ungerade Werte implizieren Layout von rechts nach links.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a>Indices-Eigenschaft  
 Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft ist eine Zeichenfolge mit Glyphenspezifikationen. Wenn ein Symbol ein einzelnes Cluster bildet, wird der Spezifikation auf des ersten Symbols im Cluster die Spezifikation vorangestellt, wie viele Symbole und wie viele Codepunkte sich kombinieren, um das Cluster zu bilden. Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft sammelt in einer Zeichenfolge die folgenden Eigenschaften.  
  
- Symbolindizes  
  
- Symboldikten  
  
- Kombinieren von Glyphen-Anlagevektors  
  
- Clusterzuordnung zwischen Codepunkten und Glyphen  
  
- Symbolflags  
  
 Jede Symbolspezifikation hat folgendes Format:  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a>Symbolmetriken  
 Jede Glyphe definiert Metriken, die angeben, <xref:System.Windows.Documents.Glyphs>wie sie an anderen ausgerichtet ist. Die folgende Abbildung definiert die verschiedenen typografischen Eigenschaften von zwei unterschiedlichen Symbolen.  
  
 ![Diagramm der Symbolmaßangaben](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a>Symbol-Markup  
 Das folgende Codebeispiel zeigt, wie <xref:System.Windows.Documents.Glyphs> verschiedene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Eigenschaften des Elements in verwendet werden.  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Text](optimizing-performance-text.md)
