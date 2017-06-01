---
title: "Einf&#252;hrung in das &quot;GlyphRun&quot;-Objekt und das &quot;Glyphs&quot;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Typografie Glyphs-element"
  - "Glyphs-Elemente"
  - "GlyphRun-Objekt"
  - "Text, Symbole"
  - "Symbole [WPF]"
  - "Typografie GlyphRun-Objekt"
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Einf&#252;hrung in das &quot;GlyphRun&quot;-Objekt und das &quot;Glyphs&quot;-Element
In diesem Thema wird beschrieben, die <xref:System.Windows.Media.GlyphRun> Objekt und die <xref:System.Windows.Documents.Glyphs> Element.  
  
   
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Einführung in GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet Unterstützung für erweiterte Text einschließlich Glyph-Level-Markup mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden abfangen und Beibehalten von Text nach dem formatieren möchten. Diese Funktionen unterstützen für den anderen Text Rendern Anforderungen in jeder der folgenden Szenarien.  
  
1.  Anzeige von Dokumenten mit festem Format.  
  
2.  Drucken Sie Szenarien.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]als Gerät Druckersprache.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Zuvor installierte Druckertreiber, die Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] zu festen Format.  
  
    -   Druckserver-Format.  
  
3.  Dokument-Format Darstellung, einschließlich der Clients für frühere Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und andere Geräte.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> sind für die Darstellung von Dokumenten mit festem Format und Druckszenarios konzipiert.                      [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Stellt etliche Elemente für allgemeine Layout- und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien, z. B. <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zum Layout und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] finden Sie Beispielszenarien, die [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Das "GlyphRun"-Objekt  
 Die <xref:System.Windows.Media.GlyphRun> -Objekt stellt eine Sequenz von Symbolen aus einer einzelnen Schriftart einer einzelnen Schriftfamilie mit einer einzelnen Größe und mit einem einzelnen Rendering dar.  
  
 <xref:System.Windows.Media.GlyphRun> umfassen sowohl Schriftartdetails wie Symbol <xref:System.Windows.Documents.Glyphs.Indices%2A> und einzelne Symbolpositionen. Es enthält auch den ursprünglichen [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Codepunkte, die die Ausführung von Informationen zur Zuordnung Zeichen zu Symbolpufferoffset sowie Flags pro Zeichen und pro Symbol generiert wurde.  
  
 <xref:System.Windows.Media.GlyphRun> verfügt über eine entsprechende allgemeine <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.                  <xref:System.Windows.Documents.Glyphs> kann verwendet werden, in der Elementstruktur und in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup dargestellt <xref:System.Windows.Media.GlyphRun> Ausgabe.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Glyphs-Element  
 Die <xref:System.Windows.Documents.Glyphs> Element darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Die folgende Markupsyntax wird zum Beschreiben der <xref:System.Windows.Documents.Glyphs> Element.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Gibt einen Ressourcenbezeichner an: Dateiname, Web- [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], oder Ressourcenverweis in der Anwendung .exe oder den Container.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Gibt den Schriftgrad in Zeichenoberflächeneinheiten (Standard ist.96 Zoll).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Gibt Flags für fett-und Kursivdruck.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Gibt die bidirektionale Layout-Ebene. Gerade und Nullwerte links-nach-rechts-Layout; rechts-nach-links-Layout implizieren ungerade Werte.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Indices-Eigenschaft  
 Die <xref:System.Windows.Documents.Glyphs.Indices%2A> -Eigenschaft ist eine Zeichenfolge der Symbolspezifikationen. Wenn eine Sequenz von Symbolen einen einzelnen Cluster bildet, geht die Spezifikation des ersten Symbols im Cluster eine Spezifikation, wie viele Symbole und wie viele Codepunkte den Cluster bilden. Die <xref:System.Windows.Documents.Glyphs.Indices%2A> Eigenschaft, die in einer Zeichenfolge die folgenden Eigenschaften werden erfasst.  
  
-   Glyph-Indizes  
  
-   Breite der Schriftzeichen voraus  
  
-   Kombinieren von Vektoren Symbol  
  
-   Clusterzuordnung zwischen Codepunkten und Symbolen  
  
-   Symbol-flags  
  
 Jeder Symbolspezifikation weist folgende Form.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Symbol-Metriken  
 Jedes Symbol definiert Metriken, die angeben, wie sie mit anderen entspricht <xref:System.Windows.Documents.Glyphs>. In der folgenden Grafik wird der verschiedenen typografischen Eigenschaften von zwei unterschiedlichen Symbolen definiert.  
  
 ![Diagramm der Symbol-Maßangaben](../../../../docs/framework/wpf/advanced/media/glyph-example.png "Glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Glyphs-Markup  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie verschiedene Eigenschaften des verwenden die <xref:System.Windows.Documents.Glyphs> Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)