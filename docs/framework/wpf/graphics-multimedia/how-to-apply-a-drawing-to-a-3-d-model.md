---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662811"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> auf ein 3D-Modell angewendet.  
  
 Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.  Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als die <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> auf eine 3-d-Ebene angewendet.  
  
 **Hinweis**: Es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen. Finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md) für Weitere Informationen.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../advanced/xaml-resources.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
