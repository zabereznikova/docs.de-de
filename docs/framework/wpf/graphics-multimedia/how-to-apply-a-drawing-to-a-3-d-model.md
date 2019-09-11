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
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="21c82-102">Vorgehensweise: Anwenden einer Zeichnung auf ein 3D-Modell</span><span class="sxs-lookup"><span data-stu-id="21c82-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="21c82-103">In diesem Beispiel <xref:System.Windows.Media.Media3D.Material> wird gezeigt, wie <xref:System.Windows.Media.DrawingBrush> ein als auf ein 3D-Modell angewendetes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="21c82-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="21c82-104">Im folgenden Code wird ein <xref:System.Windows.Media.DrawingGroup> als Inhalt <xref:System.Windows.Media.DrawingBrush>eines definiert.</span><span class="sxs-lookup"><span data-stu-id="21c82-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="21c82-105">Der <xref:System.Windows.Media.DrawingBrush> wird <xref:System.Windows.Media.Media3D.DiffuseMaterial> als-Eigenschaft des festgelegt, der auf eine 3D-Ebene angewendet wird. <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A></span><span class="sxs-lookup"><span data-stu-id="21c82-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="21c82-106">Es ist häufig wünschenswert, komplexe Objekte und Werte wie die nachfolgende Zeichnung als Ressourcen zu definieren, die wieder verwendet werden können, und den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="21c82-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="21c82-107">Weitere Informationen finden Sie unter [XAML-Ressourcen](../advanced/xaml-resources.md) .</span><span class="sxs-lookup"><span data-stu-id="21c82-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="21c82-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21c82-108">Example</span></span>

<span data-ttu-id="21c82-109">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="21c82-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="21c82-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21c82-110">See also</span></span>

- [<span data-ttu-id="21c82-111">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="21c82-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="21c82-112">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="21c82-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="21c82-113">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="21c82-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="21c82-114">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="21c82-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
