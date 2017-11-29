---
title: 'Gewusst wie: Transformieren der Skalierung eines 3D-Modells'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d94086f38169ee31cbee29e034359d573462ffca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>Gewusst wie: Transformieren der Skalierung eines 3D-Modells
In diesem Beispiel wird gezeigt, wie ein 3D-Objekt skaliert wird. Wenn ein 3D-Objekt skaliert werden sollen, verwenden Sie eine <xref:System.Windows.Media.Media3D.ScaleTransform3D>. Die <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> Eigenschaften Größe des Elements geändert, durch den Faktor, die Sie angeben. Angenommen, ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> Wert von 1,5 gestreckt wird, ein Objekt auf 150 Prozent der ursprünglichen Breite. Ein <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> Wert von 0,5 verkleinert die Höhe eines Objekts um 50 Prozent. Der folgende Code zeigt die Verwendung einer <xref:System.Windows.Media.Media3D.ScaleTransform3D> als Transformation für ein <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das vollständige Beispiel.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Animieren von 3D-Übersetzungen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)  
 [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
