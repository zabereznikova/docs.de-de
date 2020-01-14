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
ms.openlocfilehash: 9af07d48877fee0e94f8e5fa2556c4361795df6a
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740360"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element
In diesem Thema werden das <xref:System.Windows.Media.GlyphRun>-Objekt und das <xref:System.Windows.Documents.Glyphs>-Element beschrieben.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Einführung in GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet erweiterte Textunterstützung einschließlich Markup auf Symbolebene mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.  
  
1. Bildschirmanzeige von Dokumenten mit festem Format  
  
2. Druckszenarios  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte  
  
    - Microsoft XPS-Dokumentwriter.  
  
    - Vorherige Druckertreiber, Ausgabe von Win32-Anwendungen im Fixed-Format.  
  
    - Druckerspooler-Format  
  
3. Dokument Darstellung mit festem Format, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> sind für Dokument Präsentations-und Druck Szenarien mit festem Format konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Elemente für allgemeine Layouts und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien wie <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Das GlyphRun-Objekt  
 Das <xref:System.Windows.Media.GlyphRun>-Objekt stellt eine Sequenz von Symbolen aus einer einzelnen Schriftart einer einzelnen Schriftart mit einer einzelnen Größe und einem einzelnen Renderingstil dar.  
  
 <xref:System.Windows.Media.GlyphRun> enthält sowohl Schriftart Details wie Symbol <xref:System.Windows.Documents.Glyphs.Indices%2A> als auch einzelne Symbol Positionen. Sie enthält außerdem die ursprünglichen Unicode-Code Punkte, aus denen der Testlauf generiert wurde, die Zuordnung von Zeichen zu Glyphe-Puffer Offsets und die Flags pro Zeichen und pro Glyphe.  
  
 <xref:System.Windows.Media.GlyphRun> verfügt über eine entsprechende allgemeine <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>. <xref:System.Windows.Documents.Glyphs> können in der-Elementstruktur und in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup verwendet werden, um <xref:System.Windows.Media.GlyphRun> Ausgabe darzustellen.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Das Glyphs-Element  
 Das <xref:System.Windows.Documents.Glyphs> Element stellt die Ausgabe eines <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dar. Die folgende Markup Syntax wird verwendet, um das <xref:System.Windows.Documents.Glyphs>-Element zu beschreiben.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.  
  
|Die Eigenschaften-|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Gibt einen Ressourcen Bezeichner an: Datei Name, Web-Uniform Resource Identifier (URI) oder Ressourcen Verweis in der Datei "Application. exe" oder "Container".|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Gibt den Schriftgrad in Zeichenoberflächeneinheiten an (Der Standardwert ist .96 Zoll)|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Gibt Flags für Fett-und Kursivdruck an|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Gibt die bidirektionale Layoutebene an. Gerade Werte und Nullwerte implizieren Layout von links nach rechts; ungerade Werte implizieren Layout von rechts nach links.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Indices-Eigenschaft  
 Die <xref:System.Windows.Documents.Glyphs.Indices%2A>-Eigenschaft ist eine Zeichenfolge mit Glyphe-Spezifikationen. Wenn ein Symbol ein einzelnes Cluster bildet, wird der Spezifikation auf des ersten Symbols im Cluster die Spezifikation vorangestellt, wie viele Symbole und wie viele Codepunkte sich kombinieren, um das Cluster zu bilden. Die <xref:System.Windows.Documents.Glyphs.Indices%2A>-Eigenschaft sammelt die folgenden Eigenschaften in einer Zeichenfolge.  
  
- Symbolindizes  
  
- Symboldikten  
  
- Kombinieren von Glyphen-Anlagevektors  
  
- Clusterzuordnung zwischen Codepunkten und Glyphen  
  
- Symbolflags  
  
 Jede Symbolspezifikation hat folgendes Format:  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Symbolmetriken  
 Jedes Symbol definiert Metriken, die angeben, wie Sie mit anderen <xref:System.Windows.Documents.Glyphs>ausgerichtet werden. Die folgende Abbildung definiert die verschiedenen typografischen Eigenschaften von zwei unterschiedlichen Symbolen.  
  
 ![Diagraph von Glyphe-Messungen](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Symbol-Markup  
 Im folgenden Codebeispiel wird gezeigt, wie verschiedene Eigenschaften des <xref:System.Windows.Documents.Glyphs>-Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwendet werden.  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Text](optimizing-performance-text.md)
