---
title: Debuggen von Ausdrucksbaumstrukturen in Visual Studio (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84de749afad6abb748d0622561f8ee7cd399ed54
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="025d6-102">Debuggen von Ausdrucksbaumstrukturen in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="025d6-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="025d6-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen analysieren, beim Debuggen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="025d6-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="025d6-104">Um einen schnellen Überblick über die Struktur der Ausdruck zu erhalten, können Sie die `DebugView` -Eigenschaft, die nur im Debugmodus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="025d6-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="025d6-105">Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="025d6-105">For more information about debugging, see [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="025d6-106">Um den Inhalt von Ausdrucksbaumstrukturen, besser darstellen, die `DebugView` -Eigenschaft verwendet Visual Studio-Schnellansichten.</span><span class="sxs-lookup"><span data-stu-id="025d6-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="025d6-107">Weitere Informationen finden Sie unter [erstellen Sie benutzerdefinierte Schnellansichten](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="025d6-107">For more information, see [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="025d6-108">So öffnen eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="025d6-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="025d6-109">Klicken Sie auf das Lupensymbol, das neben der `DebugView` -Eigenschaft einer Ausdrucksbaumstruktur in **DataTips**, **Überwachen** Fenster der **Auto** Fenster oder **lokal** Fenster.</span><span class="sxs-lookup"><span data-stu-id="025d6-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="025d6-110">Eine Liste von Schnellansichten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="025d6-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="025d6-111">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="025d6-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="025d6-112">Jeder Ausdruckstyp wird in der Schnellansicht angezeigt, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="025d6-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="025d6-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="025d6-113">ParameterExpressions</span></span>  
 <span data-ttu-id="025d6-114"><xref:System.Linq.Expressions.ParameterExpression>Namen von Variable werden mit dem Symbol "$" am Anfang angezeigt.</xref:System.Linq.Expressions.ParameterExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="025d6-115">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="025d6-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="025d6-117">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="025d6-118">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="025d6-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="025d6-119">ConstantExpressions</span></span>  
 <span data-ttu-id="025d6-120">Für <xref:System.Linq.Expressions.ConstantExpression>Objekte, die ganzzahlige Werte, Zeichenfolgen, darstellen und `null`, wird der Wert der Konstante angezeigt.</xref:System.Linq.Expressions.ConstantExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="025d6-122">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="025d6-123">10</span><span class="sxs-lookup"><span data-stu-id="025d6-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="025d6-124">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="025d6-125">10D</span><span class="sxs-lookup"><span data-stu-id="025d6-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="025d6-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="025d6-126">BlockExpression</span></span>  
 <span data-ttu-id="025d6-127">Wenn der Typ des einem <xref:System.Linq.Expressions.BlockExpression>Objekt unterscheidet sich von dem Typ des letzten Ausdrucks im Block wird der Typ angezeigt, der `DebugInfo` Eigenschaft in spitzen Klammern (\< und >).</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="025d6-128">Andernfalls den Typ des der <xref:System.Linq.Expressions.BlockExpression>Objekt wird nicht angezeigt.</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="025d6-130">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="025d6-131">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="025d6-132">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="025d6-132">LambdaExpression</span></span>  
 <span data-ttu-id="025d6-133"><xref:System.Linq.Expressions.LambdaExpression>Objekte werden zusammen mit ihren Delegattypen angezeigt.</xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="025d6-134">Wenn ein Lambda-Ausdruck nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="025d6-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="025d6-136">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="025d6-137">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="025d6-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="025d6-138">LabelExpression</span></span>  
 <span data-ttu-id="025d6-139">Bei Angabe ein Standardwerts für das <xref:System.Linq.Expressions.LabelExpression>Objekt ist, wird dieser Wert wird angezeigt, bevor die <xref:System.Linq.Expressions.LabelTarget>Objekt.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression></span><span class="sxs-lookup"><span data-stu-id="025d6-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="025d6-140">Die `.Label` -Token gibt den Anfang der Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="025d6-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="025d6-141">Die `.LabelTarget` -Token gibt den Zielort des Ziels zu springen.</span><span class="sxs-lookup"><span data-stu-id="025d6-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="025d6-142">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `#Label1` oder `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="025d6-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="025d6-144">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-144">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     <span data-ttu-id="025d6-145">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="025d6-146">Checked-Operatoren</span><span class="sxs-lookup"><span data-stu-id="025d6-146">Checked Operators</span></span>  
 <span data-ttu-id="025d6-147">Checked-Operatoren werden mit dem Symbol "#" vor dem Operator angezeigt.</span><span class="sxs-lookup"><span data-stu-id="025d6-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="025d6-148">Der überprüfte Additionsoperator wird z. B. angezeigt, als `#+`.</span><span class="sxs-lookup"><span data-stu-id="025d6-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="025d6-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="025d6-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="025d6-150">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="025d6-151">`DebugView`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="025d6-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="025d6-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="025d6-152">See Also</span></span>  
 <span data-ttu-id="025d6-153">[Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="025d6-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="025d6-154"> [Debuggen in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="025d6-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="025d6-155"> [Erstellen Sie benutzerdefinierte Schnellansichten](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span><span class="sxs-lookup"><span data-stu-id="025d6-155"> [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
