---
title: 'Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="f4f09-102">Gewusst wie: Positionieren der untergeordneten Elemente eines Rasters</span><span class="sxs-lookup"><span data-stu-id="f4f09-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="f4f09-103">In diesem Beispiel wird gezeigt, wie auf die Get- und set-Methoden, die auf definiert <xref:System.Windows.Controls.Grid> um untergeordnete Elemente zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="f4f09-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4f09-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4f09-104">Example</span></span>  
 <span data-ttu-id="f4f09-105">Das folgende Beispiel definiert ein übergeordnetes Element <xref:System.Windows.Controls.Grid> Element (`grid1`), besitzt drei Spalten und drei Zeilen.</span><span class="sxs-lookup"><span data-stu-id="f4f09-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="f4f09-106">Ein untergeordnetes Element <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) hinzugefügt wird, um die <xref:System.Windows.Controls.Grid> Spalte Position 0 (null), Zeile Position 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f4f09-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="f4f09-107"><xref:System.Windows.Controls.Button>Elemente darstellen, Methoden, die aufgerufen werden können, um die Position der <xref:System.Windows.Shapes.Rectangle> Element innerhalb der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="f4f09-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="f4f09-108">Wenn ein Benutzer eine Schaltfläche klickt, wird die entsprechende Methode aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f4f09-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f4f09-109">Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Auslösen von Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="f4f09-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="f4f09-110">Das Beispiel schreibt diese Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die in Beziehung mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="f4f09-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f4f09-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4f09-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="f4f09-112">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="f4f09-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
