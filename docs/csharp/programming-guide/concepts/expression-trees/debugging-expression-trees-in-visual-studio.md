---
title: Debuggen von Ausdrucksbäumen in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 43091d11dfc1fae3e6f047f35b61e992c5aaf50b
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70104907"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="d1ead-102">Debuggen von Ausdrucksbäumen in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="d1ead-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="d1ead-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="d1ead-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="d1ead-104">Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1ead-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="d1ead-105">(Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)</span><span class="sxs-lookup"><span data-stu-id="d1ead-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView der Ausdrucksbaumstruktur im Visual Studio-Debugger](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="d1ead-107">Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.</span><span class="sxs-lookup"><span data-stu-id="d1ead-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Text-Schnellansicht für Ergebnisse von „DebugView“](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="d1ead-109">Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="d1ead-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="d1ead-110">Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:</span><span class="sxs-lookup"><span data-stu-id="d1ead-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Schnellansicht für lesbare Ausdrücke](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

- <span data-ttu-id="d1ead-112">Bei der [Schnellansicht für lesbare Ausdrücke](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) wird eine grafische Ansicht der Ausdrucksbaumstruktur, der zugehörigen Eigenschaften und der verwandten Objekte bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="d1ead-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="d1ead-114">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="d1ead-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="d1ead-115">Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d1ead-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="d1ead-116">Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d1ead-116">A list of available visualizers is displayed.:</span></span> 

      ![Öffnen von Schnellansichten über Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="d1ead-118">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="d1ead-118">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ead-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1ead-119">See also</span></span>

- [<span data-ttu-id="d1ead-120">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="d1ead-120">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="d1ead-121">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d1ead-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="d1ead-122">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="d1ead-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="d1ead-123">`DebugView`-Syntax</span><span class="sxs-lookup"><span data-stu-id="d1ead-123">`DebugView` syntax</span></span>](debugview-syntax.md)
