---
title: 'Gewusst wie: Ändern von Ausdrucksbaumstrukturen'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 12ccad6df7d6c7d91ebc290163db362eae173209
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353745"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>How to: Modify Expression Trees (Visual Basic)

In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können. Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden. Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen. Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.

## <a name="to-modify-an-expression-tree"></a>So ändern Sie Ausdrucksbaumstrukturen

1. Erstellen Sie ein neues **Konsolenanwendungsprojekt**.

2. Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.

3. Fügen Sie die `AndAlsoModifier`-Klasse in Ihr Projekt ein.

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

    Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und ist darauf spezialisiert, Ausdrücke zu verändern, die bedingte `AND`-Vorgänge darstellen. Es ändert diese Vorgänge von einem bedingten `AND` in ein bedingtes `OR`. Zu diesem Zweck setzt die Klasse die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>-Methode der Basisklasse außer Kraft, weil bedingte `AND`-Ausdrücke als binäre Ausdrücke dargestellt werden. Für die `VisitBinary`-Methode gilt Folgendes: Wenn der an die Methode übergebene Ausdruck eine bedingte `AND`-Operation darstellt, erstellt der Code einen neuen Ausdruck, der den bedingten Operator `OR` anstelle des bedingten Operators `AND` enthält. Wenn der an `VisitBinary` übergebene Ausdruck keinen bedingten `AND`-Vorgang darstellt, verzögert die Methode die Implementierung der Basisklasse. Die Basisklassenmethode erstellt Knoten, die den übergebenen Ausdrucksbaumstrukturen gleichen. In diesem Fall sind die Teilstrukturen der Knoten jedoch durch die Ausdrucksbaumstrukturen ersetzt, die vom Besucher rekursiv erstellt werden.

4. Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.

5. Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.

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

    Der Code erstellt einen Ausdruck, der einen bedingten `AND`-Vorgang enthält. Er erstellt anschließend eine Instanz der `AndAlsoModifier`-Klasse und übergibt den Ausdruck an die `Modify`-Methode dieser Klasse. Sowohl der ursprüngliche als auch der geänderte Ausdrucksbaum werden ausgegeben, um die Änderungen zu zeigen.

6. Kompilieren Sie die Anwendung, und führen Sie sie aus.

## <a name="see-also"></a>Siehe auch

- [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
