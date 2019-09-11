---
title: 'Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855879"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell

In diesem Beispiel <xref:System.Windows.Media.Media3D.Material> wird gezeigt, wie <xref:System.Windows.Media.DrawingBrush> ein als auf ein 3D-Modell angewendetes verwendet wird.

Im folgenden Code wird ein <xref:System.Windows.Media.DrawingGroup> als Inhalt <xref:System.Windows.Media.DrawingBrush>eines definiert.  Der <xref:System.Windows.Media.DrawingBrush> wird <xref:System.Windows.Media.Media3D.DiffuseMaterial> als-Eigenschaft des festgelegt, der auf eine 3D-Ebene angewendet wird. <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>

> [!NOTE]
> Es ist häufig wünschenswert, komplexe Objekte und Werte wie die nachfolgende Zeichnung als Ressourcen zu definieren, die wieder verwendet werden können, und den Code zu vereinfachen. Weitere Informationen finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Beispiel

Der folgende Code zeigt das gesamte Beispiel.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../advanced/xaml-resources.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
