---
title: 'Vorgehensweise: Erstellen eines Shapes mit einer StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: fd191e4cfdfa33c144389d4871a9641e9c811ed3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108601"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Vorgehensweise: Erstellen eines Shapes mit einer StreamGeometry
<xref:System.Windows.Media.StreamGeometry> stellt einfache Alternative zu <xref:System.Windows.Media.PathGeometry> zum Erstellen geometrischer Formen. Verwenden einer <xref:System.Windows.Media.StreamGeometry> Wenn Sie eine komplexe Geometrie beschreiben müssen jedoch nicht den Mehraufwand für die Unterstützung von Datenbindung, Animation oder Änderung möchten. Beispielsweise aufgrund ihrer Effizienz der <xref:System.Windows.Media.StreamGeometry> Klasse ist eine gute Wahl zum Beschreiben von Adornern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Attributsyntax, finden Sie unter den [Pfadmarkupsyntax](path-markup-syntax.md) Seite.  
  
## <a name="example"></a>Beispiel  
 Im nächsten Beispiel wird eine <xref:System.Windows.Media.StreamGeometry> ein Dreieck im Code definiert. Zunächst das Beispiel erstellt eine <xref:System.Windows.Media.StreamGeometry>, erhält dann eine <xref:System.Windows.Media.StreamGeometryContext> und wird verwendet, um das Dreieck zu beschreiben.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Im nächste Beispiel erstellt eine Methode, verwendet eine <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.StreamGeometryContext> eine geometrische Form, die basierend auf den angegebenen Parametern definiert.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [Übersicht über Geometrien](geometry-overview.md)
