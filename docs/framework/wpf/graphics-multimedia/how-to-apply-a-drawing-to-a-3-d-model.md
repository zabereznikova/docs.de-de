---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 07811f8c0326827ed90484ce12632589b2f6fc82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611240"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell
Dieses Beispiel zeigt, wie Sie mit einer <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> angewendet werden, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.  
  
 Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.  Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als die <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> angewendet werden, um eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Ebene.  
  
 **Hinweis**: Es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen. Finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) für Weitere Informationen.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
