---
title: 'Gewusst wie: Animieren von 3D-Übersetzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112257"
---
# <a name="how-to-animate-3d-translations"></a>Gewusst wie: Animieren von 3D-Übersetzungen
In diesem Thema wird veranschaulicht, wie Sie eine Übersetzungstransformationsgruppe für ein 3D-Modell animieren.  
  
 Der folgende Code zeigt <xref:System.Windows.Media.Media3D.TranslateTransform3D> die Anwendung <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> eines <xref:System.Windows.Media.Media3D.GeometryModel3D>Objekts auf die Eigenschaft einer .  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Die <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> Eigenschaft <xref:System.Windows.Media.Media3D.TranslateTransform3D> dieses Objekts wird mit dem folgenden Code animiert.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
