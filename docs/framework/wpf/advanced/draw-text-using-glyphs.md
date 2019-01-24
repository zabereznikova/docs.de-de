---
title: Zeichnen von Text mit Symbolen
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 7c7c4946d2c5cc2aa9001cf119b969dd375a1050
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680243"
---
# <a name="draw-text-using-glyphs"></a>Zeichnen von Text mit Symbolen
In diesem Thema wird erläutert, wie Sie mit der Low-Level <xref:System.Windows.Documents.Glyphs> Objekt zum Anzeigen von Text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen, wie Eigenschaften für definiert eine <xref:System.Windows.Documents.Glyphs> im-Objekt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Die <xref:System.Windows.Documents.Glyphs> Objekt darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner C:\WINDOWS\Fonts auf dem lokalen Computer installiert sind.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 In diesem Beispiel wird gezeigt, wie andere Eigenschaften des definiert <xref:System.Windows.Documents.Glyphs> Objekte im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch
- [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
