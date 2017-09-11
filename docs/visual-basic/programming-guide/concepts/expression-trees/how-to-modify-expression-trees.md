---
title: "Gewusst wie: Ändern von Ausdrucksbaumstrukturen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2f0d383cbac639212519177fb1825875682f6233
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="ed27a-102">Gewusst wie: Ändern von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed27a-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="ed27a-103">In diesem Thema wird gezeigt, wie eine Ausdrucksbaumstruktur ändern.</span><span class="sxs-lookup"><span data-stu-id="ed27a-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="ed27a-104">Ausdrucksbaumstrukturen sind unveränderlich, was bedeutet, dass sie nicht direkt geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="ed27a-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="ed27a-105">Um eine Ausdrucksbaumstruktur ändern möchten, müssen Sie eine Kopie einer vorhandenen Ausdrucksbaumstruktur zu erstellen und die erforderlichen Änderungen vorzunehmen, wenn Sie die Kopie erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed27a-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="ed27a-106">Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>Klasse, um eine vorhandene Ausdrucksbaumstruktur zu durchlaufen und jeden Knoten zu kopieren.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="ed27a-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="ed27a-107">So ändern Sie eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="ed27a-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="ed27a-108">Erstellen Sie ein neues **Konsolenanwendung** Projekt.</span><span class="sxs-lookup"><span data-stu-id="ed27a-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="ed27a-109">Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.</span><span class="sxs-lookup"><span data-stu-id="ed27a-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="ed27a-110">Hinzufügen der `AndAlsoModifier` Klasse zu Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="ed27a-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="ed27a-111">Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und wird spezialisiert, um Ausdrücke zu ändern, die bedingte darstellen `AND` Operations.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="ed27a-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="ed27a-112">Es ändert diese Operationen von einem bedingten `AND` , eine bedingte `OR`.</span><span class="sxs-lookup"><span data-stu-id="ed27a-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="ed27a-113">Die Klasse überschreibt Sie dazu die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>Methode des Basistyps, da bedingte `AND` -Ausdrücke als binäre Ausdrücke dargestellt werden.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A></span><span class="sxs-lookup"><span data-stu-id="ed27a-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="ed27a-114">In der `VisitBinary` -Methode, wenn der Ausdruck, der an sie übergeben wird, eine bedingte darstellt `AND` Vorgang, der Code erstellt einen neuen Ausdruck, der die bedingte enthält `OR` anstelle des bedingten Operators `AND` Operator.</span><span class="sxs-lookup"><span data-stu-id="ed27a-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="ed27a-115">Wenn der Ausdruck, der an `VisitBinary` keine bedingte darstellt `AND` Vorgang, der-Methode verzögert Implementierung der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="ed27a-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="ed27a-116">Die Methoden der Basisklasse erstellt Knoten, die auch die Ausdrucksbaumstrukturen, die übergeben werden, aber die Knoten haben ihre Sub-Strukturen, die mit der Ausdrucksbaumstrukturen, die ersetzt erzeugt rekursiv vom Besucher.</span><span class="sxs-lookup"><span data-stu-id="ed27a-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="ed27a-117">Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.</span><span class="sxs-lookup"><span data-stu-id="ed27a-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="ed27a-118">Fügen Sie Code in der `Main` -Methode in der Datei "Module1.vb", um eine Ausdrucksbaumstruktur zu erstellen und es an die Methode übergeben, die sie ändern.</span><span class="sxs-lookup"><span data-stu-id="ed27a-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     <span data-ttu-id="ed27a-119">Der Code erstellt einen Ausdruck, der eine bedingte enthält `AND` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="ed27a-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="ed27a-120">Er erstellt dann eine Instanz der `AndAlsoModifier` -Klasse und den Ausdruck, der `Modify` Methode dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="ed27a-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="ed27a-121">Sowohl das Original als auch die geänderte Ausdrucksbaumstruktur werden ausgegeben, um die Änderung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ed27a-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="ed27a-122">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="ed27a-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed27a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed27a-123">See Also</span></span>  
 <span data-ttu-id="ed27a-124">[Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="ed27a-124">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
<span data-ttu-id="ed27a-125"> [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span><span class="sxs-lookup"><span data-stu-id="ed27a-125"> [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
