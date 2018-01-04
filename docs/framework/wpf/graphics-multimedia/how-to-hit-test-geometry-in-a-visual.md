---
title: "Gewusst wie: Treffertest für eine Geometrie in einem visuellen Objekt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a990a43853e375c1c97f88dc6792932ad64c8d37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Gewusst wie: Treffertest für eine Geometrie in einem visuellen Objekt
In diesem Beispiel wird gezeigt, wie einen Treffertest für ein visuelles Objekt ausführen, der einem oder mehreren besteht <xref:System.Windows.Media.Geometry> Objekte.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Abrufen der <xref:System.Windows.Media.DrawingGroup> aus ein visuelles Objekt, das verwendet die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode. Ein Treffertest erfolgt klicken Sie dann auf den gerenderten Inhalt der einzelnen Zeichnen in die <xref:System.Windows.Media.DrawingGroup> um zu bestimmen, welche Geometrie geklickt wurde.  
  
> [!NOTE]
>  In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode, um zu bestimmen, ob ein Punkt mit den gerenderten Inhalt eines visuellen überschneidet.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Die <xref:System.Windows.Media.Geometry.FillContains%2A> Methode ist eine überladene Methode, die Ihnen ermöglicht, den ein Treffertest mithilfe eines angegebenen <xref:System.Windows.Point> oder <xref:System.Windows.Media.Geometry>. Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen. Sie möchten in diesem Fall rufen <xref:System.Windows.Media.Geometry.StrokeContains%2A> zusätzlich zu <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Sie können auch angeben einer <xref:System.Windows.Media.ToleranceType> , die im Rahmen der Bézier-reduzieren verwendet wird.  
  
> [!NOTE]
>  Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden. Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Treffertest mit Geometrie als Parameter](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
