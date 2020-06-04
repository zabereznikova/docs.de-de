---
title: 'Vorgehensweise: Ändern von Ausdrucksbaumstrukturen'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 1f052120a2e7e12f5a985adce3ae193afec0e9af
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410991"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>How to: Modify Expression Trees (Visual Basic) (Vorgehensweise: Bearbeiten von Audrucksbaumstrukturen (Visual Basic))

In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können. Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden. Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen. Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.

## <a name="to-modify-an-expression-tree"></a>So ändern Sie Ausdrucksbaumstrukturen

1. Erstellen Sie ein neues **Konsolenanwendungsprojekt**.

2. Fügen Sie `Imports` der Datei eine-Anweisung für den- `System.Linq.Expressions` Namespace hinzu.

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

4. Fügen Sie `Imports` der Datei eine-Anweisung für den- `System.Linq.Expressions` Namespace hinzu.

5. Fügen Sie der- `Main` Methode in der Module1. vb-Datei Code hinzu, um eine Ausdrucks Baumstruktur zu erstellen und an die Methode zu übergeben, die Sie ändert.

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

## <a name="see-also"></a>Weitere Informationen

- [How to: Execute Expression Trees (Visual Basic) (Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic))](how-to-execute-expression-trees.md)
- [Ausdrucksbaumstrukturen (Visual Basic)](index.md)
