---
title: 'Gewusst wie: Erstellen eines komplexen Grid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9dfb913407622f3cbd9a067a94cc6400b501e2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="82619-102">Gewusst wie: Erstellen eines komplexen Grid</span><span class="sxs-lookup"><span data-stu-id="82619-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="82619-103">Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.Grid> Layout erstellt wird, der einen Monatskalender ähnelt.</span><span class="sxs-lookup"><span data-stu-id="82619-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82619-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82619-104">Example</span></span>  
 <span data-ttu-id="82619-105">Im folgende Beispiel definiert acht Zeilen und acht Spalten mithilfe der <xref:System.Windows.Controls.RowDefinition> und <xref:System.Windows.Controls.ColumnDefinition> Klassen.</span><span class="sxs-lookup"><span data-stu-id="82619-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="82619-106">Er verwendet die <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> angefügten Eigenschaften zusammen mit <xref:System.Windows.Shapes.Rectangle> Elemente, die den Hintergrund der einzelnen Spalten und Zeilen ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="82619-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="82619-107">Dieser Entwurf ist möglich, da mehr als ein Element vorhanden, in jeder Zelle in sein kann einer <xref:System.Windows.Controls.Grid>, ein grundlegender Unterschied zwischen <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="82619-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="82619-108">Im Beispiel wird die vertikale Farbverläufe <xref:System.Windows.Shapes.Shape.Fill%2A> die Zeilen und Spalten, um die visuelle Darstellung und die Lesbarkeit des Kalenders zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="82619-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="82619-109">Formatiert <xref:System.Windows.Controls.TextBlock> Elemente darstellen, die Datumsangaben und die Tage der Woche.</span><span class="sxs-lookup"><span data-stu-id="82619-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="82619-110"><xref:System.Windows.Controls.TextBlock>Elemente werden absolut positioniert Zellen mithilfe der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft und die Eigenschaften für die Ausrichtung, die in das Format für die Anwendung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="82619-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="82619-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82619-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="82619-112">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="82619-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="82619-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="82619-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="82619-114">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="82619-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
