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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: efbd8c19947c45b3ba15ce7b574000d56526ef45
ms.lasthandoff: 03/13/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debuggen von Ausdrucksbaumstrukturen in Visual Studio (Visual Basic)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen analysieren, beim Debuggen Ihrer Anwendung. Um einen schnellen Überblick über die Struktur der Ausdruck zu erhalten, können Sie die `DebugView` -Eigenschaft, die nur im Debugmodus verfügbar ist. Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).  
  
 Um den Inhalt von Ausdrucksbaumstrukturen, besser darstellen, die `DebugView` -Eigenschaft verwendet Visual Studio-Schnellansichten. Weitere Informationen finden Sie unter [erstellen Sie benutzerdefinierte Schnellansichten](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1.  Klicken Sie auf das Lupensymbol, das neben der `DebugView` -Eigenschaft einer Ausdrucksbaumstruktur in **DataTips**, **Überwachen** Fenster der **Auto** Fenster oder **lokal** Fenster.  
  
     Eine Liste von Schnellansichten wird angezeigt.  
  
2.  Klicken Sie auf die gewünschte Schnellansicht.  
  
 Jeder Ausdruckstyp wird in der Schnellansicht angezeigt, wie in den folgenden Abschnitten beschrieben.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression>Namen von Variable werden mit dem Symbol "$" am Anfang angezeigt.</xref:System.Linq.Expressions.ParameterExpression>  
  
 Wenn ein Parameter nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `$var1` oder `$var2`.  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `$var1`  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 Für <xref:System.Linq.Expressions.ConstantExpression>Objekte, die ganzzahlige Werte, Zeichenfolgen, darstellen und `null`, wird der Wert der Konstante angezeigt.</xref:System.Linq.Expressions.ConstantExpression>  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     `DebugView`-Eigenschaft  
  
     10  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     `DebugView`-Eigenschaft  
  
     10D  
  
## <a name="blockexpression"></a>BlockExpression  
 Wenn der Typ des einem <xref:System.Linq.Expressions.BlockExpression>Objekt unterscheidet sich von dem Typ des letzten Ausdrucks im Block wird der Typ angezeigt, der `DebugInfo` Eigenschaft in spitzen Klammern (\< und >).</xref:System.Linq.Expressions.BlockExpression> Andernfalls den Typ des der <xref:System.Linq.Expressions.BlockExpression>Objekt wird nicht angezeigt.</xref:System.Linq.Expressions.BlockExpression>  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a>LambdaExpression.  
 <xref:System.Linq.Expressions.LambdaExpression>Objekte werden zusammen mit ihren Delegattypen angezeigt.</xref:System.Linq.Expressions.LambdaExpression>  
  
 Wenn ein Lambda-Ausdruck nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `#Lambda1` oder `#Lambda2`.  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a>LabelExpression  
 Bei Angabe ein Standardwerts für das <xref:System.Linq.Expressions.LabelExpression>Objekt ist, wird dieser Wert wird angezeigt, bevor die <xref:System.Linq.Expressions.LabelTarget>Objekt.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression>  
  
 Die `.Label` -Token gibt den Anfang der Bezeichnung. Die `.LabelTarget` -Token gibt den Zielort des Ziels zu springen.  
  
 Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihm einen automatisch generierten Name, z. B. `#Label1` oder `#Label2`.  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     `DebugView`-Eigenschaft  
  
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
  
     `DebugView`-Eigenschaft  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a>Checked-Operatoren  
 Checked-Operatoren werden mit dem Symbol "#" vor dem Operator angezeigt. Der überprüfte Additionsoperator wird z. B. angezeigt, als `#+`.  
  
### <a name="examples"></a>Beispiele  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     `DebugView`-Eigenschaft  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Debuggen in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [Erstellen Sie benutzerdefinierte Schnellansichten](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)
