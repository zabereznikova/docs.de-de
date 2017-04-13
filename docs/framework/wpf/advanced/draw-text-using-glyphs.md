---
title: "Zeichnen von Text mit Symbolen | Microsoft Docs"
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
  - "Zeichnen mit Glyphs-Objekten von Text"
  - "Glyphs-Objekten, Zeichnen von text"
  - "Typografie Glyphs-Objekte"
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Zeichnen von Text mit Symbolen
In diesem Thema erläutert, wie die Low-Level <xref:System.Windows.Documents.Glyphs> Objekt zum Anzeigen von Text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen, wie Eigenschaften für definiert eine <xref:System.Windows.Documents.Glyphs> -Objekt in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Die <xref:System.Windows.Documents.Glyphs> Objekt darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner C:\WINDOWS\Fonts auf dem lokalen Computer installiert sind.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Dieses Beispiel zeigt, wie andere Eigenschaften des <xref:System.Windows.Documents.Glyphs> Objekte im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)