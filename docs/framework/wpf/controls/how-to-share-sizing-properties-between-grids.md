---
title: "Gewusst wie: Freigeben von Größeneigenschaften zwischen Grids"
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
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="606a4-102">Gewusst wie: Freigeben von Größeneigenschaften zwischen Grids</span><span class="sxs-lookup"><span data-stu-id="606a4-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="606a4-103">In diesem Beispiel wird gezeigt, wie die größenanpassung Datengröße aller Spalten gemeinsam nutzen und zwischen Zeilen <xref:System.Windows.Controls.Grid> Elemente, um konsistente Größe zu halten.</span><span class="sxs-lookup"><span data-stu-id="606a4-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="606a4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="606a4-104">Example</span></span>  
 <span data-ttu-id="606a4-105">Im folgende Beispiel führt zwei <xref:System.Windows.Controls.Grid> Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="606a4-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="606a4-106">Die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> -Eigenschaft des <xref:System.Windows.Controls.Grid> wird auf das übergeordnete Element definiert <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="606a4-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="606a4-107">Im Beispiel ändert den Wert der Eigenschaft mithilfe von zwei <xref:System.Windows.Controls.Button> Elemente; jedes Element stellt eine boolesche Eigenschaft Werte.</span><span class="sxs-lookup"><span data-stu-id="606a4-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="606a4-108">Wenn der <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Eigenschaftswert festgelegt ist, um `true`, jedes Spalten- oder Mitglied einer <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> gemeinsam Informationen zur Größe, unabhängig von den Inhalt einer Zeile oder Spalte.</span><span class="sxs-lookup"><span data-stu-id="606a4-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="606a4-109">...</span><span class="sxs-lookup"><span data-stu-id="606a4-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="606a4-110">Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="606a4-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="606a4-111">Das Beispiel schreibt die Ergebnisse dieser Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die in Beziehung mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="606a4-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="606a4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="606a4-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [<span data-ttu-id="606a4-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="606a4-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
