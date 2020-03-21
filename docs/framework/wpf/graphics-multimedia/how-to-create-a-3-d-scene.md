---
title: 'Gewusst wie: Erstellen einer 3D-Szene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112101"
---
# <a name="how-to-create-a-3d-scene"></a>Gewusst wie: Erstellen einer 3D-Szene
In diesem Beispiel wird gezeigt, wie Sie ein 3D-Objekt erstellen, das wie ein flaches Blatt Papier aussieht, das gedreht wurde. Zum <xref:System.Windows.Controls.Viewport3D> Erstellen dieser einfachen 3D-Szene werden a zusammen mit den folgenden Komponenten verwendet:  
  
- Eine Kamera wird <xref:System.Windows.Media.Media3D.PerspectiveCamera>mit einer erstellt. Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.  
  
- Ein Netz wird erstellt, um die Form des 3D-Objekts (Blatt Papier) mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft von <xref:System.Windows.Media.Media3D.GeometryModel3D>anzugeben.  
  
- Es wird ein Material angegeben, das auf der Oberfläche des Objekts (linearer Gradient in diesem Beispiel) mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft von <xref:System.Windows.Media.Media3D.GeometryModel3D>angezeigt wird.  
  
- Es wird ein Licht erzeugt, <xref:System.Windows.Media.Media3D.DirectionalLight>das mit dem auf das Objekt scheint.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie eine 3D-Szene in XAML erstellen.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie dieselbe 3D-Szene im Verfahrenscode erstellen.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [3D-Grafikübersicht](3-d-graphics-overview.md)
