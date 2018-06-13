---
title: 'Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 54819f62b262227017e12b2066a0747107b68900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560366"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry
<xref:System.Windows.Media.StreamGeometry> Lightweight-Alternative zu <xref:System.Windows.Media.PathGeometry> für das geometrische Formen erstellen. Verwenden einer <xref:System.Windows.Media.StreamGeometry> müssen Sie eine komplexe Geometrie beschreiben, aber nicht möchten, den Aufwand für die Unterstützung von datenbindungen, Animationen und Änderungen. Mögliche Ursachen: die Effizienz der <xref:System.Windows.Media.StreamGeometry> Klasse ist eine gute Wahl zum Beschreiben von Adornern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Attributsyntax, finden Sie unter der [Markup Pfadsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Seite.  
  
## <a name="example"></a>Beispiel  
 Im nächste Beispiel wird eine <xref:System.Windows.Media.StreamGeometry> ein Dreiecks im Code definiert. Im Beispiel wird zuerst erstellt ein <xref:System.Windows.Media.StreamGeometry>, dann abgerufen eine <xref:System.Windows.Media.StreamGeometryContext> und verwendet, um das Dreieck zu beschreiben.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Im nächste Beispiel erstellt eine Methode, verwendet eine <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.StreamGeometryContext> eine geometrische Form, die basierend auf den angegebenen Parametern definiert.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
