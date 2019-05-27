---
title: Debuggen von Ausdrucksbäumen in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877143"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="55a2a-102">Debuggen von Ausdrucksbäumen in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="55a2a-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="55a2a-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="55a2a-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="55a2a-104">Sie können die `DebugView`-Eigenschaft verwenden, um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten. Hierbei werden Ausdrucksbaumstrukturen mit einer speziellen Syntax dargestellt, die [weiter unten](#debugview-syntax) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="55a2a-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="55a2a-105">(Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)</span><span class="sxs-lookup"><span data-stu-id="55a2a-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView der Ausdrucksbaumstruktur im Visual Studio-Debugger](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="55a2a-107">Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.</span><span class="sxs-lookup"><span data-stu-id="55a2a-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Text-Schnellansicht für Ergebnisse von „DebugView“](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="55a2a-109">Alternativ können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden:</span><span class="sxs-lookup"><span data-stu-id="55a2a-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="55a2a-110">Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:</span><span class="sxs-lookup"><span data-stu-id="55a2a-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Schnellansicht für lesbare Ausdrücke](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="55a2a-112">Bei der [Schnellansicht für lesbare Ausdrücke](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) wird eine grafische Ansicht der Ausdrucksbaumstruktur, der zugehörigen Eigenschaften und der verwandten Objekte bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="55a2a-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="55a2a-114">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="55a2a-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="55a2a-115">Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="55a2a-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="55a2a-116">Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="55a2a-116">A list of available visualizers is displayed.:</span></span> 

      ![Öffnen von Schnellansichten über Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="55a2a-118">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="55a2a-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="55a2a-119">`DebugView`-Syntax</span><span class="sxs-lookup"><span data-stu-id="55a2a-119">`DebugView` syntax</span></span> 

<span data-ttu-id="55a2a-120">Jeder Ausdruckstyp wird über die `DebugView`-Eigenschaft angezeigt, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55a2a-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="55a2a-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="55a2a-121">ParameterExpressions</span></span>  
 <span data-ttu-id="55a2a-122">Namen von <xref:System.Linq.Expressions.ParameterExpression>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="55a2a-123">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="55a2a-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="55a2a-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-124">Examples</span></span>  
  
|<span data-ttu-id="55a2a-125">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-125">Expression</span></span>|<span data-ttu-id="55a2a-126">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="55a2a-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="55a2a-127">ConstantExpressions</span></span>  
 <span data-ttu-id="55a2a-128">Für <xref:System.Linq.Expressions.ConstantExpression>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="55a2a-129">Für numerische Typen, die über Standardsuffixe als C#-Literale verfügen, wird das Suffix zum Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="55a2a-130">Die folgende Tabelle zeigt die verschiedenen numerischen Typen und ihre zugeordneten Suffixe.</span><span class="sxs-lookup"><span data-stu-id="55a2a-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="55a2a-131">Typ</span><span class="sxs-lookup"><span data-stu-id="55a2a-131">Type</span></span>|<span data-ttu-id="55a2a-132">Suffix</span><span class="sxs-lookup"><span data-stu-id="55a2a-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="55a2a-133">U</span><span class="sxs-lookup"><span data-stu-id="55a2a-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="55a2a-134">L</span><span class="sxs-lookup"><span data-stu-id="55a2a-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="55a2a-135">UL</span><span class="sxs-lookup"><span data-stu-id="55a2a-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="55a2a-136">D</span><span class="sxs-lookup"><span data-stu-id="55a2a-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="55a2a-137">F</span><span class="sxs-lookup"><span data-stu-id="55a2a-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="55a2a-138">M</span><span class="sxs-lookup"><span data-stu-id="55a2a-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="55a2a-139">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-139">Examples</span></span>  
  
|<span data-ttu-id="55a2a-140">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-140">Expression</span></span>|<span data-ttu-id="55a2a-141">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="55a2a-142">10</span><span class="sxs-lookup"><span data-stu-id="55a2a-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="55a2a-143">10D</span><span class="sxs-lookup"><span data-stu-id="55a2a-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="55a2a-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="55a2a-144">BlockExpression</span></span>  
 <span data-ttu-id="55a2a-145">Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in der `DebugInfo`-Eigenschaft in spitzen Klammern (\< und >) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="55a2a-146">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="55a2a-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-147">Examples</span></span>  
  
|<span data-ttu-id="55a2a-148">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-148">Expression</span></span>|<span data-ttu-id="55a2a-149">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="55a2a-150">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="55a2a-150">LambdaExpression</span></span>  
 <span data-ttu-id="55a2a-151"><xref:System.Linq.Expressions.LambdaExpression>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="55a2a-152">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="55a2a-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="55a2a-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-153">Examples</span></span>  
  
|<span data-ttu-id="55a2a-154">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-154">Expression</span></span>|<span data-ttu-id="55a2a-155">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="55a2a-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="55a2a-156">LabelExpression</span></span>  
 <span data-ttu-id="55a2a-157">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="55a2a-158">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="55a2a-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="55a2a-159">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="55a2a-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="55a2a-160">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="55a2a-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="55a2a-161">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-161">Examples</span></span>  
  
|<span data-ttu-id="55a2a-162">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-162">Expression</span></span>|<span data-ttu-id="55a2a-163">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="55a2a-164">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="55a2a-164">Checked Operators</span></span>  
 <span data-ttu-id="55a2a-165">Überprüften Operatoren wird in der Ansicht das Symbol "#" vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="55a2a-166">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55a2a-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="55a2a-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55a2a-167">Examples</span></span>  
  
|<span data-ttu-id="55a2a-168">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55a2a-168">Expression</span></span>|<span data-ttu-id="55a2a-169">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55a2a-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="55a2a-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55a2a-170">See also</span></span>

- [<span data-ttu-id="55a2a-171">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="55a2a-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="55a2a-172">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="55a2a-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="55a2a-173">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="55a2a-173">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
