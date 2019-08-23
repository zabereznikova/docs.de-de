---
title: 'Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923381"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt
Dieses Beispiel zeigt, wie Sie einen Treffer Test für ein visuelles Objekt ausführen, das aus einem oder mehreren <xref:System.Windows.Media.Geometry> -Objekten besteht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der <xref:System.Windows.Media.DrawingGroup> aus einem visuellen Objekt abgerufen wird, <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> das die-Methode verwendet. Ein Treffer Test wird dann für den gerenderten Inhalt jeder Zeichnung in der <xref:System.Windows.Media.DrawingGroup> ausgeführt, um zu bestimmen, welche Geometrie getroffen wurde.  
  
> [!NOTE]
> In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> -Methode, um zu bestimmen, ob ein Punkt den gerenderten Inhalt eines visuellen Elements überschneidet.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Bei <xref:System.Windows.Media.Geometry.FillContains%2A> der-Methode handelt es sich um eine überladene Methode, die es <xref:System.Windows.Point> Ihnen <xref:System.Windows.Media.Geometry>ermöglicht, mithilfe eines angegebenen-oder- Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen. In diesem Fall möchten Sie möglicherweise zusätzlich zu <xref:System.Windows.Media.Geometry.StrokeContains%2A> <xref:System.Windows.Media.Geometry.FillContains%2A>aufgerufen werden.  
  
 Sie können auch eine <xref:System.Windows.Media.ToleranceType> bereitstellen, die für die Zwecke der Bezier-Vereinfachung verwendet wird.  
  
> [!NOTE]
> Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden. Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.  
  
## <a name="see-also"></a>Siehe auch

- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Treffertest mit Geometrie als Parameter](how-to-hit-test-using-geometry-as-a-parameter.md)
