---
title: Ändern von Ausdrucksbaumstrukturen (C#)
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: e921c594497d02f5eb16cc60294e947e83636d7a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969900"
---
# <a name="how-to-modify-expression-trees-c"></a>Ändern von Ausdrucksbaumstrukturen (C#)
In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können. Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden. Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen. Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.  
  
### <a name="to-modify-an-expression-tree"></a>So ändern Sie Ausdrucksbaumstrukturen  
  
1. Erstellen Sie ein neues **Konsolenanwendungsprojekt**.  
  
2. Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.  
  
3. Fügen Sie die `AndAlsoModifier`-Klasse in Ihr Projekt ein.  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und ist darauf spezialisiert, Ausdrücke zu verändern, die bedingte `AND`-Vorgänge darstellen. Es ändert diese Vorgänge von einem bedingten `AND` in ein bedingtes `OR`. Zu diesem Zweck setzt die Klasse die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>-Methode der Basisklasse außer Kraft, weil bedingte `AND`-Ausdrücke als binäre Ausdrücke dargestellt werden. Für die `VisitBinary`-Methode gilt Folgendes: Wenn der an die Methode übergebene Ausdruck eine bedingte `AND`-Operation darstellt, erstellt der Code einen neuen Ausdruck, der den bedingten Operator `OR` anstelle des bedingten Operators `AND` enthält. Wenn der an `VisitBinary` übergebene Ausdruck keinen bedingten `AND`-Vorgang darstellt, verzögert die Methode die Implementierung der Basisklasse. Die Basisklassenmethode erstellt Knoten, die den übergebenen Ausdrucksbaumstrukturen gleichen. In diesem Fall sind die Teilstrukturen der Knoten jedoch durch die Ausdrucksbaumstrukturen ersetzt, die vom Besucher rekursiv erstellt werden.  
  
4. Fügen Sie der Datei eine `using`-Anweisung für den `System.Linq.Expressions`-Namespace hinzu.  
  
5. Fügen Sie der `Main`-Methode in der Datei „Program.cs“ Code hinzu, um eine Ausdrucksbaumstruktur zu erstellen, und übergeben Sie diese Struktur an die Methode, die sie ändert.  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     Der Code erstellt einen Ausdruck, der einen bedingten `AND`-Vorgang enthält. Er erstellt anschließend eine Instanz der `AndAlsoModifier`-Klasse und übergibt den Ausdruck an die `Modify`-Methode dieser Klasse. Sowohl der ursprüngliche als auch der geänderte Ausdrucksbaum werden ausgegeben, um die Änderungen zu zeigen.  
  
6. Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
## <a name="see-also"></a>Siehe auch

- [Ausführen von Ausdrucksbaumstrukturen (C#)](./how-to-execute-expression-trees.md)
- [Ausdrucksbaumstrukturen (C#)](./index.md)
