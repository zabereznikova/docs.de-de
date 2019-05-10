---
title: 'Vorgehensweise: Erstellen einer 3D-Szene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: a431b78993d197dac99f0b6e365823acb295f0b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611639"
---
# <a name="how-to-create-a-3-d-scene"></a>Vorgehensweise: Erstellen einer 3D-Szene
Dieses Beispiel zeigt, wie Sie ein 3D-Objekt erstellen, der einem flachen Blatt Papier ähnelt dem gedreht wurde. Ein <xref:System.Windows.Controls.Viewport3D> zusammen mit den folgenden Komponenten verwendet, um diese einfache 3D-Szene zu erstellen:  
  
- Eine Kamera wurde mit einem <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Die Kamera gibt an, welcher Teil der 3D-Szene angezeigt werden kann.  
  
- Ein Mesh erstellt, um die Form eines 3D-Objekts (Blatt Papier) mit anzugeben der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
- Ein Material wird angegeben, um auf die Oberfläche des Objekts (in diesem Beispiel ein linearer Farbverlauf) mit angezeigt werden die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Eigenschaft <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
- Ein Licht wird erstellt, um auf das Objekt mit glänzen <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie eine 3D-Szene in XAML zu erstellen.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie die gleiche 3D-Szene in prozeduralem Code erstellt wird.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
