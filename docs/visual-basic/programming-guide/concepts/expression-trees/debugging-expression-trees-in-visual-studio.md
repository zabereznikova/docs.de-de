---
title: Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196030"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="fc411-102">Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc411-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="fc411-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="fc411-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="fc411-104">Um einen schnellen Überblick über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView` Eigenschaft, die Ausdrucksbaumstrukturen darstellt [mit einer besonderen Syntax](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="fc411-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="fc411-105">(Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)</span><span class="sxs-lookup"><span data-stu-id="fc411-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView der Ausdrucksbaumstruktur im Visual Studio-Debugger](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="fc411-107">Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.</span><span class="sxs-lookup"><span data-stu-id="fc411-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Text-Schnellansicht für Ergebnisse von „DebugView“](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="fc411-109">Alternativ können Sie installieren und verwenden [eine benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen, z.B.:</span><span class="sxs-lookup"><span data-stu-id="fc411-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

* <span data-ttu-id="fc411-110">Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:</span><span class="sxs-lookup"><span data-stu-id="fc411-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Schnellansicht für lesbare Ausdrücke](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="fc411-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), stellt eine grafische Ansicht von der Ausdrucksbaumstruktur, die Eigenschaften und verknüpften Objekte und kann die Ausdrucksbaumstruktur, die mithilfe von Visual Basic-Code gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="fc411-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="fc411-114">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="fc411-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="fc411-115">Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc411-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="fc411-116">Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc411-116">A list of available visualizers is displayed.:</span></span> 

      ![Öffnen von Schnellansichten über Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="fc411-118">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="fc411-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fc411-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc411-119">See also</span></span>

- [<span data-ttu-id="fc411-120">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc411-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="fc411-121">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc411-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="fc411-122">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="fc411-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="fc411-123">`DebugView` Die Syntax</span><span class="sxs-lookup"><span data-stu-id="fc411-123">`DebugView` syntax</span></span>](debugview-syntax.md)
