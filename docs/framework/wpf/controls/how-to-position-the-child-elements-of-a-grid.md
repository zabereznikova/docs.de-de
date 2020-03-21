---
title: 'Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186721"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="7b20f-102">Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters</span><span class="sxs-lookup"><span data-stu-id="7b20f-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="7b20f-103">In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Grid> get- und set-Methoden verwendet werden, die für die Positionierung untergeordneter Elemente definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7b20f-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b20f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b20f-104">Example</span></span>  
 <span data-ttu-id="7b20f-105">Im folgenden Beispiel wird <xref:System.Windows.Controls.Grid> ein`grid1`übergeordnetes Element ( ) definiert, das drei Spalten und drei Zeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="7b20f-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="7b20f-106">Ein <xref:System.Windows.Shapes.Rectangle> untergeordnetes`rect1`Element ( <xref:System.Windows.Controls.Grid> ) wird der Spaltenposition Null, Zeilenposition Null hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7b20f-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="7b20f-107"><xref:System.Windows.Controls.Button>Elemente stellen Methoden dar, die <xref:System.Windows.Shapes.Rectangle> aufgerufen werden <xref:System.Windows.Controls.Grid>können, um das Element innerhalb der neu zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="7b20f-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="7b20f-108">Wenn ein Benutzer auf eine Schaltfläche klickt, wird die zugehörige Methode aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7b20f-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="7b20f-109">Im folgenden CodeBehind-Beispiel werden die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Methoden behandelt, die von den Schaltflächenereignissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b20f-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="7b20f-110">Im Beispiel werden diese <xref:System.Windows.Controls.TextBlock> Methodenaufrufe an Elemente schrieben, die verwandte ab-Methoden verwenden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="7b20f-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="7b20f-111">Hier ist das fertige Ergebnis!</span><span class="sxs-lookup"><span data-stu-id="7b20f-111">Here is the finished result!</span></span>

 ![Ein Screenshot zeigt eine WPF-Benutzeroberfläche mit zwei Spalten, die rechte Seite hat ein 3 x 3 Raster und die linke hat Schaltflächen, um ein farbiges Rechteck zwischen den Spalten und Zeilen des Rasters zu verschieben](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="7b20f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b20f-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="7b20f-114">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="7b20f-114">Panels Overview</span></span>](panels-overview.md)
