---
title: Abfragen in LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 52f48fcacd6fbd92e4fd0531c5e1fa3577496941
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738480"
---
# <a name="queries-in-linq-to-entities"></a>Abfragen in LINQ to Entities
Eine Abfrage ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in der Regel in einer speziellen Abfragesprache, wie SQL für relationale Datenbanken oder XQuery für XML, geschrieben. Deshalb mussten Entwickler bisher für jeden abzufragenden Datenquellentyp oder Datenformattyp eine neue Abfragesprache lernen. Language-Integrated Query (LINQ) bietet ein einfacheres, konsistenteres Modell zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer LINQ-Abfrage arbeiten Sie immer mit Programmierobjekten.  
  
 Eine LINQ-Abfrageoperation besteht aus drei Aktionen: Abrufen der Datenquelle(n), Erstellen der Abfrage und Ausführen der Abfrage.  
  
 Datenquellen, die die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die generische <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren, können durch LINQ abgefragt werden. Instanzen der generischen <xref:System.Data.Objects.ObjectQuery%601>-Klasse, die die generische <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert, dienen als Datenquelle für LINQ to Entities Abfragen. Die generische Klasse <xref:System.Data.Objects.ObjectQuery%601> stellt eine Abfrage dar, die eine Auflistung von null oder mehr typisierten Entitätsobjekten zurückgibt. Sie können auch zulassen, dass der Compiler den Typ einer Entität mithilfe des C# Schlüssel Worts `var` (Dim in Visual Basic) ableiten kann.  
  
 In der Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. In LINQ wird eine Abfrage in einer Variablen gespeichert. Wenn die Abfrage eine Sequenz von Werten zurückgibt, muss die Abfragevariable selbst ein abfragbarer Typ sein. Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen. Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
## <a name="query-syntax"></a>Abfragesyntax  
 LINQ to Entities-Abfragen können in zwei verschiedenen Syntaxarten verfasst werden: in der Abfrageausdrucksyntax und in der methodenbasierten Abfragesyntax. Die Abfrage Ausdruckssyntax ist neu C# in 3,0 und Visual Basic 9,0 und besteht aus einer Reihe von Klauseln, die in einer deklarativen Syntax geschrieben sind, ähnlich wie Transact-SQL oder XQuery. Allerdings kann die .NET Framework Common Language Runtime (CLR) die Abfrage Ausdruckssyntax selbst nicht lesen. Daher werden die Abfrageausdrücke beim Kompilieren in etwas übersetzt, was die CLR versteht: Methodenaufrufe. Diese Methoden werden als *Standard Abfrage Operatoren*bezeichnet. Als Entwickler können Sie entscheiden, ob Sie die Methoden mittels Methodensyntax direkt aufrufen möchten oder ob dafür die Abfragesyntax verwendet werden soll. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Abfrageausdruckssyntax  
 Abfrageausdrücke sind eine deklarative Abfragesyntax. Mit dieser Syntax kann ein Entwickler Abfragen in einer allgemeinen Programmiersprache in einem Format ähnlich dem von Transact-SQL schreiben. Die Abfrageausdruckssyntax ermöglicht die Ausführung komplexer Filter-, Sortier- und Gruppiervorgänge mit minimalem Codeeinsatz. Weitere Informationen finden Sie unter [grundlegende Abfrage Vorgänge (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Beispiele, die veranschaulichen, wie die Abfrageausdrucksyntax verwendet wird, finden Sie in den folgenden Themen:  
  
- [Beispiele für die Abfrageausdruckssyntax: Projektion](query-expression-syntax-examples-projection.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Filtern](query-expression-syntax-examples-filtering.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Sortieren](query-expression-syntax-examples-ordering.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren](query-expression-syntax-examples-aggregate-operators.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Partitionierung](query-expression-syntax-examples-partitioning.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Joinoperatoren](query-expression-syntax-examples-join-operators.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Elementoperatoren](query-expression-syntax-examples-element-operators.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Gruppieren](query-expression-syntax-examples-grouping.md)  
  
- [Beispiele für die Abfrageausdruckssyntax: Navigieren in Beziehungen](query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Methodenbasierte Abfragesyntax  
 Eine weitere Möglichkeit zum Verfassen LINQ to Entities Abfragen ist die Verwendung von Methoden basierten Abfragen. Bei der Methoden basierten Abfrage Syntax handelt es sich um eine Abfolge direkter Methodenaufrufe an LINQ-Operator Methoden, wobei als Parameter Lambda-Ausdrücke übergeben werden. Weitere Informationen finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Beispiele, die veranschaulichen, wie die methodenbasierte Syntax verwendet wird, finden Sie in den folgenden Themen:  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Projektion](method-based-query-syntax-examples-projection.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Filtern](method-based-query-syntax-examples-filtering.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Sortieren](method-based-query-syntax-examples-ordering.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Aggregatoperatoren](method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Partitionierung](method-based-query-syntax-examples-partitioning.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Konvertierung](method-based-query-syntax-examples-conversion.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren](method-based-query-syntax-examples-join-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren](method-based-query-syntax-examples-element-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Gruppieren](method-based-query-syntax-examples-grouping.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen](method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Entities](linq-to-entities.md)
- [Erste Schritte mit LINQ in C#](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Entity Framework mergeoptionen und kompilierte Abfragen](https://go.microsoft.com/fwlink/?LinkId=199591)
