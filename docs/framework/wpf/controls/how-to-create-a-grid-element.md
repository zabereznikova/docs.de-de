---
title: 'Gewusst wie: Erstellen eines Elements von Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: 9fc70b8f15c4ecb4844c9c2ff4f7eeab94e7b906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551165"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="76bdc-102">Gewusst wie: Erstellen eines Elements von Grid</span><span class="sxs-lookup"><span data-stu-id="76bdc-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="76bdc-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76bdc-103">Example</span></span>  
 <span data-ttu-id="76bdc-104">Im folgende Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.Controls.Grid> entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code.</span><span class="sxs-lookup"><span data-stu-id="76bdc-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="76bdc-105">In diesem Beispiel verwendet drei <xref:System.Windows.Controls.ColumnDefinition> Objekte und drei <xref:System.Windows.Controls.RowDefinition> Objekte, um ein Raster erstellen, das neun Zellen, z. B. in einem Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="76bdc-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="76bdc-106">Jede Zelle enthält eine <xref:System.Windows.Controls.TextBlock> Element, das Daten sowie die oberste Zeile darstellt, enthält eine <xref:System.Windows.Controls.TextBlock> mit der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="76bdc-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="76bdc-107">Zum Anzeigen der Grenzen jeder Zelle der <xref:System.Windows.Controls.Grid.ShowGridLines%2A> -Eigenschaft aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="76bdc-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="76bdc-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76bdc-108">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="76bdc-109">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="76bdc-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
