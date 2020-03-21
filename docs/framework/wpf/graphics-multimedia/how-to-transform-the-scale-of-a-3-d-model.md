---
title: 'Gewusst wie: Transformieren der Skalierung eines 3D-Modells'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111984"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>Gewusst wie: Transformieren der Skalierung eines 3D-Modells
In diesem Beispiel wird gezeigt, wie ein 3D-Objekt skaliert wird. Um ein 3D-Objekt <xref:System.Windows.Media.Media3D.ScaleTransform3D>zu skalieren, verwenden Sie eine . Die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> und Eigenschaften ändern die Größe des Elements um den angegebenen Faktor. Ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> Wert von 1,5 dehnt z. B. ein Objekt auf 150 Prozent seiner ursprünglichen Breite aus. Bei <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> einem Wert von 0,5 wird die Höhe eines Objekts um 50 Prozent verkleinert. Der folgende Code <xref:System.Windows.Media.Media3D.ScaleTransform3D> zeigt die Verwendung <xref:System.Windows.Media.Media3D.GeometryModel3D>einer als Transformation für eine .  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Animieren von 3D-Übersetzungen](how-to-animate-3-d-translations.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
