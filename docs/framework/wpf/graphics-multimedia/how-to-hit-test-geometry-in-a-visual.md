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
ms.openlocfilehash: 87b626e575d889447ef061d1ed62ef28efe5dfeb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227339"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt
Dieses Beispiel zeigt, wie Sie einen Treffertest für ein visuelles Objekt durchführen, das von einem oder mehreren besteht <xref:System.Windows.Media.Geometry> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Abrufen der <xref:System.Windows.Media.DrawingGroup> aus einem visuellen Objekt, das verwendet die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode. Ein Treffertest erfolgt klicken Sie dann auf den gerenderten Inhalt der einzelnen Zeichnungen in der <xref:System.Windows.Media.DrawingGroup> um zu bestimmen, welche Geometrie getroffen wurde.  
  
> [!NOTE]
>  In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um zu bestimmen, ob ein Punkt innerhalb des gerenderten Inhalts eines visuellen Objekts liegt.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Die <xref:System.Windows.Media.Geometry.FillContains%2A> Methode ist eine überladene Methode, die Ihnen ermöglicht, den ein Treffertest mithilfe eines angegebenen <xref:System.Windows.Point> oder <xref:System.Windows.Media.Geometry>. Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen. Sie möchten in diesem Fall rufen <xref:System.Windows.Media.Geometry.StrokeContains%2A> zusätzlich zu <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Sie bieten auch eine <xref:System.Windows.Media.ToleranceType> , die im Rahmen der Bezier vereinfachen verwendet wird.  
  
> [!NOTE]
>  Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden. Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.  
  
## <a name="see-also"></a>Siehe auch

- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Treffertest mit Geometrie als Parameter](how-to-hit-test-using-geometry-as-a-parameter.md)
