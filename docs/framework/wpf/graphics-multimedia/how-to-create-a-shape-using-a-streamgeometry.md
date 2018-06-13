---
title: 'Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 54819f62b262227017e12b2066a0747107b68900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560366"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="6d344-102">Gewusst wie: Erstellen einer Form mithilfe von StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="6d344-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="6d344-103"><xref:System.Windows.Media.StreamGeometry> Lightweight-Alternative zu <xref:System.Windows.Media.PathGeometry> für das geometrische Formen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d344-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="6d344-104">Verwenden einer <xref:System.Windows.Media.StreamGeometry> müssen Sie eine komplexe Geometrie beschreiben, aber nicht möchten, den Aufwand für die Unterstützung von datenbindungen, Animationen und Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6d344-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="6d344-105">Mögliche Ursachen: die Effizienz der <xref:System.Windows.Media.StreamGeometry> Klasse ist eine gute Wahl zum Beschreiben von Adornern.</span><span class="sxs-lookup"><span data-stu-id="6d344-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d344-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d344-106">Example</span></span>  
 <span data-ttu-id="6d344-107">Im folgenden Beispiel wird die Attributsyntax eine dreieckige erstellen <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d344-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="6d344-108">Weitere Informationen zu <xref:System.Windows.Media.StreamGeometry> Attributsyntax, finden Sie unter der [Markup Pfadsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Seite.</span><span class="sxs-lookup"><span data-stu-id="6d344-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d344-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d344-109">Example</span></span>  
 <span data-ttu-id="6d344-110">Im nächste Beispiel wird eine <xref:System.Windows.Media.StreamGeometry> ein Dreiecks im Code definiert.</span><span class="sxs-lookup"><span data-stu-id="6d344-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="6d344-111">Im Beispiel wird zuerst erstellt ein <xref:System.Windows.Media.StreamGeometry>, dann abgerufen eine <xref:System.Windows.Media.StreamGeometryContext> und verwendet, um das Dreieck zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6d344-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="6d344-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d344-112">Example</span></span>  
 <span data-ttu-id="6d344-113">Im nächste Beispiel erstellt eine Methode, verwendet eine <xref:System.Windows.Media.StreamGeometry> und <xref:System.Windows.Media.StreamGeometryContext> eine geometrische Form, die basierend auf den angegebenen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="6d344-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6d344-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d344-114">See Also</span></span>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [<span data-ttu-id="6d344-115">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="6d344-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [<span data-ttu-id="6d344-116">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="6d344-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
