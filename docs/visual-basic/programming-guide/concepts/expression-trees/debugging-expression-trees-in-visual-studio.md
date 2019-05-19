---
title: Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879836"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="dafd9-102">Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dafd9-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="dafd9-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="dafd9-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="dafd9-104">Um einen schnellen Überblick über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView` Eigenschaft, die Ausdrucksbaumstrukturen, die mit einer besonderen Syntax beschrieben darstellt [unten](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="dafd9-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="dafd9-105">(Beachten Sie, dass `DebugView` ist nur im Debugmodus verfügbar.)</span><span class="sxs-lookup"><span data-stu-id="dafd9-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView Ausdrucksbaumstruktur in Visual Studio-debugger](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="dafd9-107">Da `DebugView` ist eine Zeichenfolge, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) zum Anzeigen über mehrere Zeilen auswählen **Text-Schnellansicht** aus das Lupensymbol neben der `DebugView` Etikett.</span><span class="sxs-lookup"><span data-stu-id="dafd9-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Text-Schnellansicht auf Ergebnisse von "DebugView" angewendet](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="dafd9-109">Alternativ können Sie installieren und verwenden [eine benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen:</span><span class="sxs-lookup"><span data-stu-id="dafd9-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="dafd9-110">[Lesbare Ausdrücke](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), verfügbar unter der [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), rendert die Ausdrucksstruktur als C# Code:</span><span class="sxs-lookup"><span data-stu-id="dafd9-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Lesbare Ausdrücke-Schnellansicht](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="dafd9-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), stellt eine grafische Ansicht von der Ausdrucksbaumstruktur, die Eigenschaften und verknüpften Objekte und kann die Ausdrucksbaumstruktur, die mithilfe von Visual Basic-Code gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="dafd9-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="dafd9-114">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="dafd9-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="dafd9-115">Klicken Sie auf das Lupensymbol neben der Ausdrucksbaumstruktur in **DataTips**, **sehen Sie sich** Fenster die **"Auto"** Fenster oder der **"lokal"** Fenster.</span><span class="sxs-lookup"><span data-stu-id="dafd9-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="dafd9-116">Eine Liste der verfügbaren Schnellansichten wird angezeigt.:</span><span class="sxs-lookup"><span data-stu-id="dafd9-116">A list of available visualizers is displayed.:</span></span> 

      ![Öffnen von Schnellansichten aus Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="dafd9-118">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="dafd9-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="dafd9-119">`DebugView` Die Syntax</span><span class="sxs-lookup"><span data-stu-id="dafd9-119">`DebugView` syntax</span></span> 

<span data-ttu-id="dafd9-120">Jeder Ausdruckstyp wird in der Schnellansicht angezeigt, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dafd9-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="dafd9-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="dafd9-121">ParameterExpressions</span></span>

<span data-ttu-id="dafd9-122">Namen von <xref:System.Linq.Expressions.ParameterExpression>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="dafd9-123">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="dafd9-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="dafd9-125">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="dafd9-126">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="dafd9-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="dafd9-127">ConstantExpressions</span></span>
 <span data-ttu-id="dafd9-128">Für <xref:System.Linq.Expressions.ConstantExpression>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="dafd9-130">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-130">`DebugView` property</span></span>

    <span data-ttu-id="dafd9-131">10</span><span class="sxs-lookup"><span data-stu-id="dafd9-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="dafd9-132">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-132">`DebugView` property</span></span>

    <span data-ttu-id="dafd9-133">10D</span><span class="sxs-lookup"><span data-stu-id="dafd9-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="dafd9-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="dafd9-134">BlockExpression</span></span>

<span data-ttu-id="dafd9-135">Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in der `DebugInfo`-Eigenschaft in spitzen Klammern (\< und >) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="dafd9-136">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="dafd9-138">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="dafd9-139">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="dafd9-140">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="dafd9-140">LambdaExpression</span></span>

<span data-ttu-id="dafd9-141"><xref:System.Linq.Expressions.LambdaExpression>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="dafd9-142">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="dafd9-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="dafd9-144">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="dafd9-145">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="dafd9-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="dafd9-146">LabelExpression</span></span>

<span data-ttu-id="dafd9-147">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="dafd9-148">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="dafd9-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="dafd9-149">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="dafd9-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="dafd9-150">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="dafd9-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="dafd9-152">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-152">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="dafd9-153">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="dafd9-154">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="dafd9-154">Checked Operators</span></span>

<span data-ttu-id="dafd9-155">Überprüften Operatoren wird in der Ansicht das Symbol "#" vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="dafd9-156">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dafd9-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="dafd9-157">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dafd9-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="dafd9-158">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="dafd9-159">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dafd9-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="dafd9-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dafd9-160">See also</span></span>

- [<span data-ttu-id="dafd9-161">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dafd9-161">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="dafd9-162">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dafd9-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="dafd9-163">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="dafd9-163">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
