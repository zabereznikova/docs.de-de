---
title: 'Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7437f4c8279d80d7287565a28337a3cd647e239
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.DrawingBrush> als die <xref:System.Windows.Media.Media3D.Material> angewendet, um eine [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.  
  
 Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt von einem <xref:System.Windows.Media.DrawingBrush>.  Die <xref:System.Windows.Media.DrawingBrush> festgelegt ist, als der <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft der <xref:System.Windows.Media.Media3D.DiffuseMaterial> angewendet, um eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] Ebene.  
  
 **Hinweis:** es ist häufig wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden kann und Ihren Code vereinfachen. Finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) für Weitere Informationen.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das vollständige Beispiel.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
