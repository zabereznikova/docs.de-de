---
title: 'Gewusst wie: Erstellen einer 3D-Szene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: e3c2ea803961ca57606f8ea8bec21d50a38dbe1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-3-d-scene"></a>Gewusst wie: Erstellen einer 3D-Szene
Dieses Beispiel zeigt, wie ein 3D-Objekt erstellt, der eine flache Blatt Papier ähnelt dem gedreht wurde. Ein <xref:System.Windows.Controls.Viewport3D> zusammen mit den folgenden Komponenten werden zum Erstellen dieser einfachen 3D-Szene verwendet:  
  
-   Eine Kamera erstellt, wobei eine <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.  
  
-   Ein Netz wird erstellt, um die Form der Verwendung von 3D-Objekt (Blatt Papier) angeben der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Ein Material wird angegeben, um auf der Oberfläche des Objekts (in diesem Beispiel ein linearer Farbverlauf) mit angezeigt werden die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Eine helle wird erstellt, um auf das Objekt mit verwendet <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie zum Erstellen einer 3D-Szene in XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die gleiche 3D-Szene in prozeduralem Code zu erstellen.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
