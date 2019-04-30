---
title: 'Vorgehensweise: Erstellen einer GeometryDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904955"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="fce04-102">Vorgehensweise: Erstellen einer GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="fce04-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="fce04-103">In diesem Beispiel wird gezeigt, wie zum Erstellen und Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="fce04-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="fce04-104">Ein <xref:System.Windows.Media.GeometryDrawing> können Sie zum Erstellen einer Form mit einer Füllung und eine Übersicht über durch Zuordnen einer <xref:System.Windows.Media.Pen> und ein <xref:System.Windows.Media.Brush> mit einem <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="fce04-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="fce04-105">Die <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> beschreibt die Struktur, die <xref:System.Windows.Media.GeometryDrawing.Brush%2A> wird beschrieben, die Füllung der Form, und die <xref:System.Windows.Media.GeometryDrawing.Pen%2A> der Form beschreibt.</span><span class="sxs-lookup"><span data-stu-id="fce04-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce04-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fce04-106">Example</span></span>  
 <span data-ttu-id="fce04-107">Im folgenden Beispiel wird eine <xref:System.Windows.Media.GeometryDrawing> eine Form gerendert.</span><span class="sxs-lookup"><span data-stu-id="fce04-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="fce04-108">Die Form wird beschrieben, indem eine <xref:System.Windows.Media.GeometryGroup> und zwei <xref:System.Windows.Media.EllipseGeometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="fce04-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="fce04-109">Das Innere der Form gezeichnet wird eine <xref:System.Windows.Media.LinearGradientBrush> und seine Kontur gezeichnet wird, mit einem <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="fce04-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="fce04-110">Die <xref:System.Windows.Media.GeometryDrawing> nutzt eine <xref:System.Windows.Media.ImageDrawing> und <xref:System.Windows.Controls.Image> Element.</span><span class="sxs-lookup"><span data-stu-id="fce04-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="fce04-111">Die folgende Abbildung zeigt die resultierende <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="fce04-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="fce04-112">![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="fce04-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="fce04-113">Sie können mehrere Zeichnungsobjekte in einem einzigen zusammengesetzten Zeichnung mithilfe von kombinieren, um komplexere Zeichnungen erstellen zu können, eine <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="fce04-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce04-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fce04-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="fce04-115">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="fce04-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="fce04-116">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="fce04-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="fce04-117">Erstellen einer zusammengesetzten Zeichnung</span><span class="sxs-lookup"><span data-stu-id="fce04-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
