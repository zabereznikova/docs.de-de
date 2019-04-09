---
title: 'Vorgehensweise: Transformieren der Skalierung eines 3D-Modells'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165081"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>Vorgehensweise: Transformieren der Skalierung eines 3D-Modells
Dieses Beispiel zeigt, wie Sie ein 3D-Objekt zu skalieren. Um ein 3D-Objekt skalieren zu können, verwendet eine <xref:System.Windows.Media.Media3D.ScaleTransform3D>. Die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> Eigenschaften Größe des Elements geändert, um den Faktor, die Sie angeben. Z. B. eine <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> Wert von 1,5 wird ein Objekt auf 150 Prozent der ursprünglichen Breite gestreckt. Ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> Wert von 0,5 verringert sich die Höhe eines Objekts, aufgerufen werden, um 50 Prozent. Der folgende Code zeigt die Verwendung einer <xref:System.Windows.Media.Media3D.ScaleTransform3D> als Transformation für einen <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren von 3D-Übersetzungen](how-to-animate-3-d-translations.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
