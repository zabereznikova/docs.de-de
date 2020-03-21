---
title: 'Gewusst wie: Material auf die Vorder- und Rückseite eines 3D-Objekts anwenden'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112140"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>Gewusst wie: Material auf die Vorder- und Rückseite eines 3D-Objekts anwenden
Das folgende Beispiel zeigt, <xref:System.Windows.Media.Media3D.Material> wie Sie eine auf die Vorder- und Rückseite eines 3D-Objekts anwenden und das Objekt animieren, um beide Seiten des Objekts anzuzeigen. Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D> von a wird <xref:System.Windows.Media.Brush> verwendet, um ein Rot <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> auf die <xref:System.Windows.Media.Media3D.GeometryModel3D> Vorderseite des Objekts anzuwenden, und die Eigenschaft des wird verwendet, um ein Blau <xref:System.Windows.Media.Brush> auf die Rückseite des Objekts anzuwenden. Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Animieren von Materialeigenschaften in einer 3D-Szene](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Anwenden von Emissivmaterial auf ein 3D-Objekt](how-to-apply-emissive-material-to-a-3-d-object.md)
