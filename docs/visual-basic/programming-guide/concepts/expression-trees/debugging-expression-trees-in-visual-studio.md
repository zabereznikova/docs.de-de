---
title: Debuggen von Ausdrucksbäumen in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 2c4b1fec389a8ee168b890339ce11af596581cbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378799"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="ce10c-102">Debuggen von Ausdrucks Baumstrukturen in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce10c-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="ce10c-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="ce10c-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="ce10c-104">Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt.</span><span class="sxs-lookup"><span data-stu-id="ce10c-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="ce10c-105">(Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)</span><span class="sxs-lookup"><span data-stu-id="ce10c-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Screenshot der Debug-Ansicht der Ausdrucks Baumstruktur.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="ce10c-107">Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.</span><span class="sxs-lookup"><span data-stu-id="ce10c-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Screenshot der Text Schnellansicht, die auf die Ergebnisse von DebugView angewendet wird.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="ce10c-109">Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="ce10c-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="ce10c-110">Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code, der ein Design zugewiesen werden kann, und mit verschiedenen Renderingoptionen gerendert:</span><span class="sxs-lookup"><span data-stu-id="ce10c-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Screenshot der Schnellansicht für lesbare Ausdrücke.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="ce10c-112">[Ausdrucks Baum](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) Struktur-Schnellansicht ([mit-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), stellt eine grafische Ansicht der Ausdrucks Baumstruktur, der zugehörigen Eigenschaften und verknüpften Objekte bereit. und können die Ausdrucks Baumstruktur mithilfe Visual Basic Codes Rendering:</span><span class="sxs-lookup"><span data-stu-id="ce10c-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Screenshot der expressionto String-Schnellansicht.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="ce10c-114">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="ce10c-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="ce10c-115">Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ce10c-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="ce10c-116">Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce10c-116">A list of available visualizers is displayed.:</span></span>

    ![Screenshot der Benutzer, die Visualisierungen aus Visual Studio öffnen](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="ce10c-118">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="ce10c-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce10c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce10c-119">See also</span></span>

- [<span data-ttu-id="ce10c-120">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce10c-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="ce10c-121">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce10c-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="ce10c-122">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="ce10c-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="ce10c-123">`DebugView`-Syntax</span><span class="sxs-lookup"><span data-stu-id="ce10c-123">`DebugView` syntax</span></span>](debugview-syntax.md)
