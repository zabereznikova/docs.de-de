---
title: 'Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459367"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell

In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.DrawingBrush> als <xref:System.Windows.Media.Media3D.Material> verwendet wird, das auf ein 3D-Modell angewendet wird.

Der folgende Code definiert eine <xref:System.Windows.Media.DrawingGroup> als Inhalt einer <xref:System.Windows.Media.DrawingBrush>.  Die <xref:System.Windows.Media.DrawingBrush> wird als <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>-Eigenschaft des <xref:System.Windows.Media.Media3D.DiffuseMaterial> festgelegt, das auf eine 3D-Ebene angewendet wird.

> [!NOTE]
> Es ist häufig wünschenswert, komplexe Objekte und Werte wie die nachfolgende Zeichnung als Ressourcen zu definieren, die wieder verwendet werden können, und den Code zu vereinfachen. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Beispiel

Der folgende Code zeigt das gesamte Beispiel.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
