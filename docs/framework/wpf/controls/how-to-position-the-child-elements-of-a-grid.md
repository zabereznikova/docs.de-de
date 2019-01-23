---
title: 'Vorgehensweise: Positionieren der untergeordneten Elemente eines Rasters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: a1b567356588d6798bae5d73d3d410882d087986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538673"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="64c31-102">Vorgehensweise: Positionieren der untergeordneten Elemente eines Rasters</span><span class="sxs-lookup"><span data-stu-id="64c31-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="64c31-103">Dieses Beispiel zeigt, wie Get und set-Methoden, die auf definiert sind <xref:System.Windows.Controls.Grid> zum Positionieren der untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="64c31-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64c31-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64c31-104">Example</span></span>  
 <span data-ttu-id="64c31-105">Das folgende Beispiel definiert ein übergeordnetes Element <xref:System.Windows.Controls.Grid> Element (`grid1`) über drei Spalten und drei Zeilen verfügt.</span><span class="sxs-lookup"><span data-stu-id="64c31-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="64c31-106">Ein untergeordnetes Element <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) hinzugefügt wird, um die <xref:System.Windows.Controls.Grid> an Position der Spalte 0 (null), Zeile Position 0 (null).</span><span class="sxs-lookup"><span data-stu-id="64c31-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="64c31-107"><xref:System.Windows.Controls.Button> Elemente darstellen, die Methoden, die aufgerufen werden können, um die Position der <xref:System.Windows.Shapes.Rectangle> Element innerhalb der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="64c31-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="64c31-108">Wenn ein Benutzer eine Schaltfläche klickt, wird die entsprechende Methode aktiviert.</span><span class="sxs-lookup"><span data-stu-id="64c31-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="64c31-109">Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Auslösen von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="64c31-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="64c31-110">Das Beispiel schreibt diese Methodenaufrufe in <xref:System.Windows.Controls.TextBlock> Elemente, die Verwendung im Zusammenhang mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="64c31-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="64c31-111">Hier ist das Endergebnis!</span><span class="sxs-lookup"><span data-stu-id="64c31-111">Here is the finished result!</span></span>
 
 ![ein Screenshot zeigt eine WPF-Benutzeroberfläche mit zwei Spalten, die rechte Seite ist eine 3 x 3-Raster und der linken Seite verfügt über die Schaltflächen, um ein farbiges Rechteck zwischen den Spalten und Zeilen des Rasters zu verschieben.](./media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="64c31-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64c31-113">See also</span></span>
- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="64c31-114">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="64c31-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
