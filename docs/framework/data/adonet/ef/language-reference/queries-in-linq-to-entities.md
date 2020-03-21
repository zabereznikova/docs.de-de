---
title: Abfragen in LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 3144796dfb1a970152d8ae56424aa37592d5da09
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848781"
---
# <a name="queries-in-linq-to-entities"></a>Abfragen in LINQ to Entities
Eine Abfrage ist ein Ausdruck, der Daten von einer Datenquelle abruft. Abfragen werden in der Regel in einer speziellen Abfragesprache, wie SQL für relationale Datenbanken oder XQuery für XML, geschrieben. Deshalb mussten Entwickler bisher für jeden abzufragenden Datenquellentyp oder Datenformattyp eine neue Abfragesprache lernen. Language-Integrated Query (LINQ) bietet ein einfacheres, konsistenteres Modell zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten. In einer LINQ-Abfrage arbeiten Sie immer mit Programmierobjekten.  
  
 Eine LINQ-Abfrageoperation besteht aus drei Aktionen: Abrufen der Datenquelle(n), Erstellen der Abfrage und Ausführen der Abfrage.  
  
 Datenquellen, die die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die generische <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren, können durch LINQ abgefragt werden. Instanzen der <xref:System.Data.Objects.ObjectQuery%601> generischen Klasse, <xref:System.Linq.IQueryable%601> die die generische Schnittstelle implementiert, dienen als Datenquelle für LINQ to Entities-Abfragen. Die generische Klasse <xref:System.Data.Objects.ObjectQuery%601> stellt eine Abfrage dar, die eine Auflistung von null oder mehr typisierten Entitätsobjekten zurückgibt. Sie können den Compiler auch den Typ einer Entität ableiten lassen, indem Sie das Schlüsselwort `var` "C" (Dim in Visual Basic) verwenden.  
  
 In der Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen. In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden. In LINQ wird eine Abfrage in einer Variablen gespeichert. Wenn die Abfrage eine Sequenz von Werten zurückgibt, muss die Abfragevariable selbst ein abfragbarer Typ sein. Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen. Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
## <a name="query-syntax"></a>Abfragesyntax  
 LINQ to Entities-Abfragen können in zwei verschiedenen Syntaxarten verfasst werden: in der Abfrageausdrucksyntax und in der methodenbasierten Abfragesyntax. Abfrageausdrucksyntax ist in C# 3.0 und Visual Basic 9.0 neu. Sie besteht aus einem Satz von in einer deklarativen Syntax geschriebenen Klauseln, ähnlich Transact-SQL oder XQuery. Die .NET Framework Common Language Runtime (CLR) kann die Syntax des Abfrageausdrucks jedoch nicht selbst lesen. Daher werden die Abfrageausdrücke beim Kompilieren in etwas übersetzt, was die CLR versteht: Methodenaufrufe. Diese Methoden werden als *Standardabfrageoperatoren*bezeichnet. Als Entwickler können Sie entscheiden, ob Sie die Methoden mittels Methodensyntax direkt aufrufen möchten oder ob dafür die Abfragesyntax verwendet werden soll. Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Syntax für Abfrageausdrücke  
 Abfrageausdrücke sind eine deklarative Abfragesyntax. Mit dieser Syntax kann ein Entwickler Abfragen in einer allgemeinen Programmiersprache in einem Format ähnlich dem von Transact-SQL schreiben. Die Abfrageausdruckssyntax ermöglicht die Ausführung komplexer Filter-, Sortier- und Gruppiervorgänge mit minimalem Codeeinsatz. Weitere Informationen finden Sie unter [Basic Query Operations (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Beispiele, die veranschaulichen, wie die Abfrageausdrucksyntax verwendet wird, finden Sie in den folgenden Themen:  
  
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
 Eine weitere Möglichkeit zum Verfassen von LINQ to Entities-Abfragen besteht in der Verwendung methodenbasierter Abfragen. Dabei handelt es sich um eine Abfolge direkter Methodenaufrufe der LINQ-Operatormethoden, wobei als Parameter Lambdaausdrücke übergeben werden. Weitere Informationen finden Sie unter [Lambda-Ausdrücke](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Beispiele, die veranschaulichen, wie die methodenbasierte Syntax verwendet wird, finden Sie in den folgenden Themen:  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Projektion](method-based-query-syntax-examples-projection.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Filtern](method-based-query-syntax-examples-filtering.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Sortieren](method-based-query-syntax-examples-ordering.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren](method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Partitionierung](method-based-query-syntax-examples-partitioning.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Konvertierung](method-based-query-syntax-examples-conversion.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren](method-based-query-syntax-examples-join-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren](method-based-query-syntax-examples-element-operators.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Gruppieren](method-based-query-syntax-examples-grouping.md)  
  
- [Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen](method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to Entities](linq-to-entities.md)
- [Erste Schritte mit LINQ in C #](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Erste Schritte mit LINQ in Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [EF-Mergeoptionen und kompilierte Abfragen](https://docs.microsoft.com/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries)
