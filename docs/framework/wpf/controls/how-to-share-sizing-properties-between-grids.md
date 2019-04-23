---
title: 'Vorgehensweise: Freigeben von Größeneigenschaften zwischen Rastern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190339"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="6b5ed-102">Vorgehensweise: Freigeben von Größeneigenschaften zwischen Rastern</span><span class="sxs-lookup"><span data-stu-id="6b5ed-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="6b5ed-103">In diesem Beispiel wird gezeigt, wie zum Freigeben der Größenänderungsdaten von Spalten und Zeilen zwischen <xref:System.Windows.Controls.Grid> Elemente, um konsistente Größe beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b5ed-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b5ed-104">Example</span></span>  
 <span data-ttu-id="6b5ed-105">Im folgende Beispiel führt zwei <xref:System.Windows.Controls.Grid> -Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="6b5ed-106">Die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> angefügte Eigenschaft von <xref:System.Windows.Controls.Grid> wird auf dem übergeordneten Element definiert <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="6b5ed-107">Im Beispiel wird der Eigenschaftswert geändert, mithilfe von zwei <xref:System.Windows.Controls.Button> Elemente; jedes Element steht für eine der booleschen Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="6b5ed-108">Wenn die <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Eigenschaftswert wird festgelegt, um `true`, jedes Spalten- oder Mitglied einer <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> -Eigenschaft größenänderungsinformationen, unabhängig vom Inhalt einer Zeile oder Spalte.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="6b5ed-109">...</span><span class="sxs-lookup"><span data-stu-id="6b5ed-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="6b5ed-110">Im folgenden Code-Behind-Beispiel werden die Methoden behandelt, die die Schaltfläche mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="6b5ed-111">Das Beispiel schreibt die Ergebnisse dieser Methodenaufrufe <xref:System.Windows.Controls.TextBlock> Elemente, die Verwendung im Zusammenhang mit get-Methoden, um die neuen Eigenschaftswerte als Zeichenfolgen auszugeben.</span><span class="sxs-lookup"><span data-stu-id="6b5ed-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6b5ed-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b5ed-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="6b5ed-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="6b5ed-113">Panels Overview</span></span>](panels-overview.md)
