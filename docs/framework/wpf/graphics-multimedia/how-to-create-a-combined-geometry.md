---
title: 'Vorgehensweise: Erstellen von kombinierten Geometrien'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910089"
---
# <a name="how-to-create-a-combined-geometry"></a>Vorgehensweise: Erstellen von kombinierten Geometrien
Dieses Beispiel zeigt, wie Geometrien kombiniert werden. Zum Kombinieren zweier Geometrien verwenden eine <xref:System.Windows.Media.CombinedGeometry> Objekt. Legen Sie seine <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> Eigenschaften mit die beiden Geometrien zu kombinieren, und legen Sie die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> Eigenschaft, die bestimmt, wie die Geometrien kombiniert werden sollen, zu `Union`, `Intersect`, `Exclude`, oder `Xor`.  
  
 Um eine zusammengesetzte Geometrie aus mindestens zwei Geometrien erstellen, verwenden Sie eine <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel eine <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit einem Kombinationsmodus `Exclude`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Ergebnisse des Exclude-Kombinationsmodus](./media/mil-task-combined-geometry-exclude.PNG "Mil_task_combined_geometry_exclude")  
Ausschließen von kombinierten Geometrien  
  
 Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Intersect`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Ergebnisse des Intersect-Kombinationsmodus](./media/mil-task-combined-geometry-intersect.PNG "Mil_task_combined_geometry_intersect")  
Schneiden von kombinierten Geometrien  
  
 Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Union`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union-Kombinationsmodus](./media/mil-task-combined-geometry-union.PNG "Mil_task_combined_geometry_union")  
Union von kombinierten Geometrien  
  
 Im folgenden Markup ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, wobei der Kombinationsmodus von `Xor`.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, aber deren Mittelpunkte von 50 definiert.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor-Kombinationsmodus](./media/mil-task-combined-geometry-xor.PNG "Mil_task_combined_geometry_xor")  
Xor von kombinierten Geometrien
