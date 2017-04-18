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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fb4e818eed7d6547e091c914d40b3ce87af59512
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Gewusst wie: Ändern von Ausdrucksbaumstrukturen (Visual Basic)
In diesem Thema wird gezeigt, wie eine Ausdrucksbaumstruktur ändern. Ausdrucksbaumstrukturen sind unveränderlich, was bedeutet, dass sie nicht direkt geändert werden können. Um eine Ausdrucksbaumstruktur ändern möchten, müssen Sie eine Kopie einer vorhandenen Ausdrucksbaumstruktur zu erstellen und die erforderlichen Änderungen vorzunehmen, wenn Sie die Kopie erstellen. Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>Klasse, um eine vorhandene Ausdrucksbaumstruktur zu durchlaufen und jeden Knoten zu kopieren.</xref:System.Linq.Expressions.ExpressionVisitor>  
  
### <a name="to-modify-an-expression-tree"></a>So ändern Sie eine Ausdrucksbaumstruktur  
  
1.  Erstellen Sie ein neues **Konsolenanwendung** Projekt.  
  
2.  Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.  
  
3.  Hinzufügen der `AndAlsoModifier` Klasse zu Ihrem Projekt.  
  
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
  
     Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und wird spezialisiert, um Ausdrücke zu ändern, die bedingte darstellen `AND` Operations.</xref:System.Linq.Expressions.ExpressionVisitor> Es ändert diese Operationen von einem bedingten `AND` , eine bedingte `OR`. Die Klasse überschreibt Sie dazu die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>Methode des Basistyps, da bedingte `AND` -Ausdrücke als binäre Ausdrücke dargestellt werden.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> In der `VisitBinary` -Methode, wenn der Ausdruck, der an sie übergeben wird, eine bedingte darstellt `AND` Vorgang, der Code erstellt einen neuen Ausdruck, der die bedingte enthält `OR` anstelle des bedingten Operators `AND` Operator. Wenn der Ausdruck, der an `VisitBinary` keine bedingte darstellt `AND` Vorgang, der-Methode verzögert Implementierung der Basisklasse. Die Methoden der Basisklasse erstellt Knoten, die auch die Ausdrucksbaumstrukturen, die übergeben werden, aber die Knoten haben ihre Sub-Strukturen, die mit der Ausdrucksbaumstrukturen, die ersetzt erzeugt rekursiv vom Besucher.  
  
4.  Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.  
  
5.  Fügen Sie Code in der `Main` -Methode in der Datei "Module1.vb", um eine Ausdrucksbaumstruktur zu erstellen und es an die Methode übergeben, die sie ändern.  
  
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
  
     Der Code erstellt einen Ausdruck, der eine bedingte enthält `AND` Vorgang. Er erstellt dann eine Instanz der `AndAlsoModifier` -Klasse und den Ausdruck, der `Modify` Methode dieser Klasse. Sowohl das Original als auch die geänderte Ausdrucksbaumstruktur werden ausgegeben, um die Änderung anzuzeigen.  
  
6.  Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
