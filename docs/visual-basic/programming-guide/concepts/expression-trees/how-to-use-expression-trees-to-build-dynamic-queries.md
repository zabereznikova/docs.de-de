---
title: 'Gewusst wie: Verwenden von Ausdrucksbaumstrukturen zum Erstellen dynamischer Abfragen'
ms.date: 07/20/2015
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: 616aa3eba1e07a92983bb5d2048a9dbae936e77c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346053"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>Gewusst wie: Verwenden von Ausdrucks Baumstrukturen zum Erstellen dynamischer Abfragen (Visual Basic)

Ausdrucksbaumstrukturen werden in LINQ dazu verwendet, strukturierte Abfragen für Datenquellen zu repräsentieren, die <xref:System.Linq.IQueryable%601> implementieren. Der LINQ-Anbieter implementiert z.B. die <xref:System.Linq.IQueryable%601>-Schnittstelle, um relationale Datenspeicher abzufragen. Der Visual Basic Compiler kompiliert Abfragen, die auf solche Datenquellen abzielen, in den Code, der zur Laufzeit eine Ausdrucks Baumstruktur erstellt. Anschließend kann der Abfrageanbieter die Datenstruktur der Ausdrucksbaumstruktur durchlaufen und in eine für die Datenquelle geeignete Abfragesprache übersetzen.

Ausdrucksbaumstrukturen werden in LINQ außerdem dazu verwendet, Lambdaausdrücke zu repräsentieren, die Variablen den Typs <xref:System.Linq.Expressions.Expression%601> zugewiesen sind.

In diesem Thema wird erläutert, wie Sie Ausdrucksbaumstrukturen verwenden können, um dynamische LINQ-Abfragen zu erstellen. Dynamische Abfragen sind nützlich, wenn die Eigenschaften einer Abfrage zur Kompilierzeit nicht bekannt sind. Beispielsweise kann eine Anwendung über eine Benutzeroberfläche verfügen, in der der Endbenutzer ein oder mehrere Prädikate zum Filtern der Daten angeben kann. Damit LINQ für Abfragen verwendet werden kann, muss solch eine Anwendung Ausdrucksbaumstrukturen benutzen, um die LINQ-Abfrage zur Laufzeit zu erstellen.

## <a name="example"></a>Beispiel

In folgendem Beispiel erfahren Sie, wie Sie Ausdrucksbaumstrukturen zur Konstruktion einer Abfrage anhand einer `IQueryable`-Datenquelle verwenden und diese anschließend ausführen können. Im Code wird eine Ausdrucksbaumstruktur erstellt, welche die folgende Abfrage darstellt:

`companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`

Die Factorymethoden im <xref:System.Linq.Expressions>-Namespace werden zum Erstellen von Ausdrucksbaumstrukturen verwendet, die Ausdrücke repräsentieren, aus denen die Abfrage besteht. Die Ausdrücke, die Aufrufe an die Methoden des Standardabfrageoperators repräsentieren, verweisen auf die <xref:System.Linq.Queryable>-Implementierung dieser Methoden. Die letzte Verzeichnisstruktur wird an die <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>-Implementierung des Anbieters der `IQueryable`-Datenquelle übergeben, um eine ausführbare Abfrage des Typs `IQueryable` zu erstellen. Sie erhalten die Ergebnisse via Zugriff auf die Auflistung der Abfrageergebnisse.

```vb
' Add an Imports statement for System.Linq.Expressions.

Dim companies =
    {"Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",
     "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",
     "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",
     "Blue Yonder Airlines", "Trey Research", "The Phone Company",
     "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee"}

' The IQueryable data to query.
Dim queryableData As IQueryable(Of String) = companies.AsQueryable()

' Compose the expression tree that represents the parameter to the predicate.
Dim pe As ParameterExpression = Expression.Parameter(GetType(String), "company")

' ***** Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16) *****
' Create an expression tree that represents the expression: company.ToLower() = "coho winery".
Dim left As Expression = Expression.Call(pe, GetType(String).GetMethod("ToLower", System.Type.EmptyTypes))
Dim right As Expression = Expression.Constant("coho winery")
Dim e1 As Expression = Expression.Equal(left, right)

' Create an expression tree that represents the expression: company.Length > 16.
left = Expression.Property(pe, GetType(String).GetProperty("Length"))
right = Expression.Constant(16, GetType(Integer))
Dim e2 As Expression = Expression.GreaterThan(left, right)

' Combine the expressions to create an expression tree that represents the
' expression: company.ToLower() = "coho winery" OrElse company.Length > 16).
Dim predicateBody As Expression = Expression.OrElse(e1, e2)

' Create an expression tree that represents the expression:
' queryableData.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16)
Dim whereCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "Where",
        New Type() {queryableData.ElementType},
        queryableData.Expression,
        Expression.Lambda(Of Func(Of String, Boolean))(predicateBody, New ParameterExpression() {pe}))
' ***** End Where *****

' ***** OrderBy(Function(company) company) *****
' Create an expression tree that represents the expression:
' whereCallExpression.OrderBy(Function(company) company)
Dim orderByCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "OrderBy",
        New Type() {queryableData.ElementType, queryableData.ElementType},
        whereCallExpression,
        Expression.Lambda(Of Func(Of String, String))(pe, New ParameterExpression() {pe}))
' ***** End OrderBy *****

' Create an executable query from the expression tree.
Dim results As IQueryable(Of String) = queryableData.Provider.CreateQuery(Of String)(orderByCallExpression)

' Enumerate the results.
For Each company As String In results
    Console.WriteLine(company)
Next

' This code produces the following output:
'
' Blue Yonder Airlines
' City Power & Light
' Coho Winery
' Consolidated Messenger
' Graphic Design Institute
' Humongous Insurance
' Lucerne Publishing
' Northwind Traders
' The Phone Company
' Wide World Importers
```

In diesem Code wird in dem an die `Queryable.Where`-Methode übergebenen Prädikat eine feste Anzahl von Ausdrücken verwendet. Sie können allerdings eine Anwendung schreiben, die eine variable Zahl von Prädikatausdrücken miteinander vereint; diese Zahl ist von der Benutzereingabe abhängig. Sie können auch die Standardabfrageoperatoren variieren, die in der Abfrage aufgerufen werden; dies ist ebenfalls von der Benutzereingabe abhängig.

## <a name="compile-the-code"></a>Kompilieren des Codes

- Erstellen Sie ein neues **Konsolenanwendungsprojekt**.

- Binden Sie den System.Linq.Expressions-Namespace ein.

- Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in das `Main` `Sub` Prozedur ein.

## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Vorgehensweise: Ausführen von Ausdrucks Baumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
