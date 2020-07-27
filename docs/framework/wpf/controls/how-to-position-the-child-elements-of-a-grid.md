---
title: 'Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters'
description: Erfahren Sie, wie Sie die Get-und Set-Methoden verwenden, die in einem Windows Presentation Foundation Raster definiert sind, um untergeordnete Elemente zu positionieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167399"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="580ec-103">Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters</span><span class="sxs-lookup"><span data-stu-id="580ec-103">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="580ec-104">Dieses Beispiel zeigt, wie Sie die Get-und Set-Methoden verwenden, die für zum Positionieren von untergeordneten Elementen definiert sind <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="580ec-104">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="580ec-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="580ec-105">Example</span></span>  
 <span data-ttu-id="580ec-106">Im folgenden Beispiel wird ein <xref:System.Windows.Controls.Grid> übergeordnetes Element ( `grid1` ) mit drei Spalten und drei Zeilen definiert.</span><span class="sxs-lookup"><span data-stu-id="580ec-106">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="580ec-107">Ein untergeordnetes <xref:System.Windows.Shapes.Rectangle> Element ( `rect1` ) wird der <xref:System.Windows.Controls.Grid> in der Spaltenposition 0 (null), Zeilen Position 0, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="580ec-107">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="580ec-108"><xref:System.Windows.Controls.Button>-Elemente stellen Methoden dar, die aufgerufen werden können, um das <xref:System.Windows.Shapes.Rectangle> Element in der neu zu positionieren <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="580ec-108"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="580ec-109">Wenn ein Benutzer auf eine Schaltfläche klickt, wird die zugehörige-Methode aktiviert.</span><span class="sxs-lookup"><span data-stu-id="580ec-109">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="580ec-110">Im folgenden Code Behind-Beispiel werden die Methoden behandelt, die von den Schaltflächen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignissen erhoben werden.</span><span class="sxs-lookup"><span data-stu-id="580ec-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="580ec-111">Im Beispiel werden diese Methodenaufrufe in- <xref:System.Windows.Controls.TextBlock> Elemente geschrieben, die Verwandte Get-Methoden verwenden, um die neuen Eigenschaftswerte als Zeichen folgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="580ec-111">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="580ec-112">Hier ist das fertige Ergebnis!</span><span class="sxs-lookup"><span data-stu-id="580ec-112">Here is the finished result!</span></span>

 ![ein Screenshot stellt eine WPF-Benutzeroberfläche mit zwei Spalten dar, die Rechte Seite verfügt über ein 3 x 3-Raster und die linke Schaltfläche, um ein farbiges Rechteck zwischen den Spalten und Zeilen des Rasters zu verschieben.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="580ec-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="580ec-114">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="580ec-115">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="580ec-115">Panels Overview</span></span>](panels-overview.md)
