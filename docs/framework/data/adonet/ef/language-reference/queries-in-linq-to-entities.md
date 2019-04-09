---
title: Abfragen in LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 0e005939c8168606c7f58467f11115666cf1ef24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124740"
---
# <a name="queries-in-linq-to-entities"></a>Abfragen in LINQ to Entities
Eine Abfrage ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in der Regel in einer speziellen Abfragesprache, wie SQL für relationale Datenbanken oder XQuery für XML, geschrieben. Deshalb mussten Entwickler bisher für jeden abzufragenden Datenquellentyp oder Datenformattyp eine neue Abfragesprache lernen. Language-Integrated Query (LINQ) bietet ein einfacheres, konsistenteres Modell zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer LINQ-Abfrage arbeiten Sie immer mit Programmierobjekten.  
  
 Eine LINQ-Abfrageoperation besteht aus drei Aktionen: Abrufen der Datenquelle(n), Erstellen der Abfrage und Ausführen der Abfrage.  
  
 Datenquellen, die die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die generische <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren, können durch LINQ abgefragt werden. Instanzen der generischen <xref:System.Data.Objects.ObjectQuery%601> Klasse, die implementiert die generische <xref:System.Linq.IQueryable%601> Schnittstelle, dienen als Datenquelle für [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] Abfragen. Die generische Klasse <xref:System.Data.Objects.ObjectQuery%601> stellt eine Abfrage dar, die eine Auflistung von null oder mehr typisierten Entitätsobjekten zurückgibt. Ferner können Sie, dass den Compiler den Typ einer Entität ableiten, mit dem C#-Schlüsselwort `var` (Dim in Visual Basic).  
  
 In der Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. In LINQ wird eine Abfrage in einer Variablen gespeichert. Wenn die Abfrage eine Sequenz von Werten zurückgibt, muss die Abfragevariable selbst ein abfragbarer Typ sein. Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen. Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
## <a name="query-syntax"></a>Abfragesyntax  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] Abfragen können in zwei verschiedenen Syntaxarten verfasst werden: Abfrageausdrucksyntax und mit der methodenbasierten Abfragesyntax. Die Abfrageausdruckssyntax ist neu in c# 3.0 und Visual Basic 9.0, und es besteht aus einer Reihe von Klauseln, die in einer deklarativen Syntax ähnlich wie Transact-SQL oder XQuery geschrieben. Beachten Sie jedoch, dass die [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]-Common Language Runtime (CLR) die Abfrageausdruckssyntax selbst nicht lesen kann. Daher werden die Abfrageausdrücke beim Kompilieren in etwas übersetzt, was die CLR versteht: Methodenaufrufe. Diese Methoden werden als bezeichnet die *Standardabfrageoperatoren*. Als Entwickler können Sie entscheiden, ob Sie die Methoden mittels Methodensyntax direkt aufrufen möchten oder ob dafür die Abfragesyntax verwendet werden soll. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Abfrageausdruckssyntax  
 Abfrageausdrücke sind eine deklarative Abfragesyntax. Mit dieser Syntax kann ein Entwickler Abfragen in einer allgemeinen Programmiersprache in einem Format ähnlich dem von Transact-SQL schreiben. Die Abfrageausdruckssyntax ermöglicht die Ausführung komplexer Filter-, Sortier- und Gruppiervorgänge mit minimalem Codeeinsatz. Weitere Informationen [Grundlegende Abfrageoperationen (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Beispiele, die veranschaulichen, wie die Abfrageausdrucksyntax verwendet wird, finden Sie in den folgenden Themen:  
  
-   [Beispiele für die Abfrageausdruckssyntax: Projection](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Filtern](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Sortieren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Aggregatoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Partitionierung](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Joinoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Elementoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Gruppieren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Navigieren in Beziehungen](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Methodenbasierte Abfragesyntax  
 Eine weitere Möglichkeit [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen zu erstellen, besteht im Verwenden von methodenbasierten Abfragen. Die mit der methodenbasierten Abfragesyntax ist eine Sequenz von Aufrufen der direkten Methode zu LINQ-Standardabfrageoperator-Methoden, Lambda-Ausdrücke als Parameter übergeben. Weitere Informationen finden Sie unter [Lambdaausdrücke](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Beispiele, die veranschaulichen, wie die methodenbasierte Syntax verwendet wird, finden Sie in den folgenden Themen:  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Projection](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Filtern](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Sortieren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Aggregatoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Partitionierung](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Umwandeln](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Gruppieren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Erste Schritte mit LINQ in C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Erste Schritte mit LINQ in Visual Basic](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Entity Framework-Zusammenführungsoptionen und kompilierte Abfragen.](https://go.microsoft.com/fwlink/?LinkId=199591)
