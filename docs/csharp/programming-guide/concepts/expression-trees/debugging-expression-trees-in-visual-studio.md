---
title: Debuggen von Ausdrucksbäumen in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 95a01a98e771e04afd296428ed56e9518bad9ac2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330406"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="e78a2-102">Debuggen von Ausdrucksbäumen in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="e78a2-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="e78a2-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="e78a2-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="e78a2-104">Um einen schnellen Überblick über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die nur im Debugmodus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e78a2-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="e78a2-105">Weitere Informationen zum Debugging finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e78a2-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="e78a2-106">Die `DebugView`-Eigenschaft stellt den Inhalt von Ausdrucksbaumstrukturen mithilfe von Visual Studio-Schnellansichten übersichtlicher dar.</span><span class="sxs-lookup"><span data-stu-id="e78a2-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="e78a2-107">Weitere Informationen finden Sie unter [Create Custom Visualizers (Erstellen benutzerdefinierter Schnellansichten)](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="e78a2-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="e78a2-108">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="e78a2-108">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="e78a2-109">Klicken Sie auf das Lupensymbol, das in **DataTips** neben der `DebugView`-Eigenschaft einer Ausdrucksbaumstruktur, neben einem **Überwachungsfenster**, einem **Auto**- oder neben einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e78a2-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="e78a2-110">Eine Liste von Schnellansichten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-110">A list of visualizers is displayed.</span></span>  
  
2. <span data-ttu-id="e78a2-111">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="e78a2-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="e78a2-112">Jeder Ausdruckstyp wird in der Schnellansicht angezeigt, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e78a2-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="e78a2-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="e78a2-113">ParameterExpressions</span></span>  
 <span data-ttu-id="e78a2-114">Namen von <xref:System.Linq.Expressions.ParameterExpression>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="e78a2-115">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="e78a2-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e78a2-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-116">Examples</span></span>  
  
|<span data-ttu-id="e78a2-117">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-117">Expression</span></span>|<span data-ttu-id="e78a2-118">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="e78a2-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="e78a2-119">ConstantExpressions</span></span>  
 <span data-ttu-id="e78a2-120">Für <xref:System.Linq.Expressions.ConstantExpression>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="e78a2-121">Für numerische Typen, die über Standardsuffixe als C#-Literale verfügen, wird das Suffix zum Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="e78a2-122">Die folgende Tabelle zeigt die verschiedenen numerischen Typen und ihre zugeordneten Suffixe.</span><span class="sxs-lookup"><span data-stu-id="e78a2-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="e78a2-123">Typ</span><span class="sxs-lookup"><span data-stu-id="e78a2-123">Type</span></span>|<span data-ttu-id="e78a2-124">Suffix</span><span class="sxs-lookup"><span data-stu-id="e78a2-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="e78a2-125">U</span><span class="sxs-lookup"><span data-stu-id="e78a2-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="e78a2-126">L</span><span class="sxs-lookup"><span data-stu-id="e78a2-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="e78a2-127">UL</span><span class="sxs-lookup"><span data-stu-id="e78a2-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="e78a2-128">D</span><span class="sxs-lookup"><span data-stu-id="e78a2-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="e78a2-129">F</span><span class="sxs-lookup"><span data-stu-id="e78a2-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="e78a2-130">M</span><span class="sxs-lookup"><span data-stu-id="e78a2-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="e78a2-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-131">Examples</span></span>  
  
|<span data-ttu-id="e78a2-132">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-132">Expression</span></span>|<span data-ttu-id="e78a2-133">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="e78a2-134">10</span><span class="sxs-lookup"><span data-stu-id="e78a2-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="e78a2-135">10D</span><span class="sxs-lookup"><span data-stu-id="e78a2-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="e78a2-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="e78a2-136">BlockExpression</span></span>  
 <span data-ttu-id="e78a2-137">Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in der `DebugInfo`-Eigenschaft in spitzen Klammern (\< und >) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="e78a2-138">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e78a2-139">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-139">Examples</span></span>  
  
|<span data-ttu-id="e78a2-140">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-140">Expression</span></span>|<span data-ttu-id="e78a2-141">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="e78a2-142">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="e78a2-142">LambdaExpression</span></span>  
 <span data-ttu-id="e78a2-143"><xref:System.Linq.Expressions.LambdaExpression>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="e78a2-144">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="e78a2-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e78a2-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-145">Examples</span></span>  
  
|<span data-ttu-id="e78a2-146">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-146">Expression</span></span>|<span data-ttu-id="e78a2-147">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="e78a2-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="e78a2-148">LabelExpression</span></span>  
 <span data-ttu-id="e78a2-149">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="e78a2-150">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="e78a2-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="e78a2-151">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e78a2-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="e78a2-152">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="e78a2-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e78a2-153">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-153">Examples</span></span>  
  
|<span data-ttu-id="e78a2-154">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-154">Expression</span></span>|<span data-ttu-id="e78a2-155">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="e78a2-156">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e78a2-156">Checked Operators</span></span>  
 <span data-ttu-id="e78a2-157">Überprüften Operatoren wird in der Ansicht das Symbol "#" vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="e78a2-158">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78a2-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e78a2-159">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e78a2-159">Examples</span></span>  
  
|<span data-ttu-id="e78a2-160">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e78a2-160">Expression</span></span>|<span data-ttu-id="e78a2-161">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e78a2-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="e78a2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e78a2-162">See also</span></span>

- [<span data-ttu-id="e78a2-163">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="e78a2-163">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="e78a2-164">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e78a2-164">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="e78a2-165">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="e78a2-165">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
