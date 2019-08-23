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
ms.openlocfilehash: 9e40a9656bd1d89203b167860ef6951d5e30377c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918400"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Einführung in das "GlyphRun"-Objekt und das "Glyphs"-Element
In diesem Thema werden <xref:System.Windows.Media.GlyphRun> das-Objekt <xref:System.Windows.Documents.Glyphs> und das-Element beschrieben.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Einführung in GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet erweiterte Unterstützung für Text, einschließlich Markup auf Symbolebene mit direktem <xref:System.Windows.Documents.Glyphs> Zugriff auf für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.  
  
1. Bildschirmanzeige von Dokumenten mit festem Format  
  
2. Druckszenarios  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte  
  
    - Microsoft XPS-Dokumentwriter.  
  
    - Vorherige Druckertreiber, Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen an das feste Format  
  
    - Druckerspooler-Format  
  
3. Dokument Darstellung mit festem Format, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>und <xref:System.Windows.Media.GlyphRun> sind für Dokument Präsentations-und Druck Szenarien mit festem Format konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet mehrere-Elemente für allgemeines Layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und Szenarios <xref:System.Windows.Controls.Label> wie <xref:System.Windows.Controls.TextBlock>und. Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Das GlyphRun-Objekt  
 Das <xref:System.Windows.Media.GlyphRun> -Objekt stellt eine Sequenz von Symbolen aus einer einzelnen Schriftart einer einzelnen Schriftart mit einer einzelnen Größe und einem einzelnen Renderingstil dar.  
  
 <xref:System.Windows.Media.GlyphRun>schließt Schriftart Details wie <xref:System.Windows.Documents.Glyphs.Indices%2A> Symbole und einzelne Symbol Positionen ein. Sie enthält außerdem die ursprünglichen [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Code Punkte, aus denen der Testlauf generiert wurde, die Zuordnung von Zeichen zu Glyphe-Puffer Offset-Informationen und die Flags pro Zeichen und pro Glyphe.  
  
 <xref:System.Windows.Media.GlyphRun>weist eine entsprechende <xref:System.Windows.FrameworkElement>allgemeine, <xref:System.Windows.Documents.Glyphs>auf. <xref:System.Windows.Documents.Glyphs>kann in der-Elementstruktur und im Markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zum darstellen <xref:System.Windows.Media.GlyphRun> der Ausgabe verwendet werden.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Das Glyphs-Element  
 Das <xref:System.Windows.Documents.Glyphs> -Element stellt die Ausgabe <xref:System.Windows.Media.GlyphRun> eines in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dar. Die folgende Markup Syntax wird verwendet, um das <xref:System.Windows.Documents.Glyphs> -Element zu beschreiben.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Die folgenden Eigenschaftendefinitionen entsprechen den ersten vier Attributen im Beispielmarkup.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Gibt einen Ressourcen Bezeichner an: Datei Name [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], Web oder Ressourcen Verweis in der Datei "Application. exe" oder "Container".|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Gibt den Schriftgrad in Zeichenoberflächeneinheiten an (Der Standardwert ist .96 Zoll)|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Gibt Flags für Fett-und Kursivdruck an|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Gibt die bidirektionale Layoutebene an. Gerade Werte und Nullwerte implizieren Layout von links nach rechts; ungerade Werte implizieren Layout von rechts nach links.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Indices-Eigenschaft  
 Die <xref:System.Windows.Documents.Glyphs.Indices%2A> -Eigenschaft ist eine Zeichenfolge von Glyphe-Spezifikationen. Wenn ein Symbol ein einzelnes Cluster bildet, wird der Spezifikation auf des ersten Symbols im Cluster die Spezifikation vorangestellt, wie viele Symbole und wie viele Codepunkte sich kombinieren, um das Cluster zu bilden. Die <xref:System.Windows.Documents.Glyphs.Indices%2A> -Eigenschaft sammelt die folgenden Eigenschaften in einer Zeichenfolge.  
  
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
  
 ![Diagramm der Symbol-Maßangaben](./media/glyph-example.png "Glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Symbol-Markup  
 Im folgenden Codebeispiel wird gezeigt, wie verschiedene Eigenschaften des <xref:System.Windows.Documents.Glyphs> -Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]verwendet werden.  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
- [Text](optimizing-performance-text.md)
