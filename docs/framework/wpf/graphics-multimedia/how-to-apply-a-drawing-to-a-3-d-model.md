---
title: 'Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112179"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell

In diesem Beispiel wird <xref:System.Windows.Media.DrawingBrush> gezeigt, wie ein als <xref:System.Windows.Media.Media3D.Material> auf ein 3D-Modell angewendetwird wird.

Der folgende Code <xref:System.Windows.Media.DrawingGroup> definiert a als <xref:System.Windows.Media.DrawingBrush>Inhalt einer .  Der <xref:System.Windows.Media.DrawingBrush> wird als <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> Eigenschaft <xref:System.Windows.Media.Media3D.DiffuseMaterial> der auf eine 3D-Ebene angewendeten Ebene festgelegt.

> [!NOTE]
> Es ist oft wünschenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die wiederverwendet werden können und Den Code vereinfachen können. Weitere Informationen finden Sie unter [XAML-Ressourcen.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Beispiel

Der folgende Code zeigt das gesamte Beispiel.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Weitere Informationen

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
