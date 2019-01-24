---
title: 'Vorgehensweise: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652032"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>Vorgehensweise: Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts
Das folgende Beispiel zeigt, wie Sie Anwenden einer <xref:System.Windows.Media.Media3D.Material> auf die Vorder- und Rückseite eines 3D-Objekts Objekt aus, und das Objekt zum Anzeigen von beiden Seiten des Objekts animieren. Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.GeometryModel3D> dient zum Anwenden von eines rotes <xref:System.Windows.Media.Brush> , die auf der Vorderseite des Objekts und die <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.GeometryModel3D> wird verwendet, um ein blaues anwenden <xref:System.Windows.Media.Brush> auf die Rückseite des Objekts. Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Animieren von Material-Eigenschaften in einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [Anwenden von Emissive Material auf ein 3D-Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
