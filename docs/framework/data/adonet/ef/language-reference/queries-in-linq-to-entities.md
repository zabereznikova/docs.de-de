---
title: "Abfragen in LINQ to Entities | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Abfragen in LINQ to Entities
Eine Abfrage ist ein Ausdruck, der Daten von einer Datenquelle abruft.  Abfragen werden in der Regel in einer speziellen Abfragesprache, wie SQL für relationale Datenbanken oder XQuery für XML, geschrieben.  Deshalb mussten Entwickler bisher für jeden abzufragenden Datenquellentyp oder Datenformattyp eine neue Abfragesprache lernen.  Language\-Integrated Query \(LINQ\) bietet ein einfacheres, konsistenteres Modell zum Arbeiten mit Daten in verschiedenen Arten von Datenquellen und Formaten.  In einer LINQ\-Abfrage arbeiten Sie immer mit Programmierobjekten.  
  
 Eine LINQ\-Abfrageoperation besteht aus drei Aktionen: Abrufen der Datenquelle\(n\), Erstellen der Abfrage und Ausführen der Abfrage.  
  
 Datenquellen, die die generische <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle oder die generische <xref:System.Linq.IQueryable%601>\-Schnittstelle implementieren, können durch LINQ abgefragt werden.  Instanzen der generischen <xref:System.Data.Objects.ObjectQuery%601>\-Klasse, die die generische <xref:System.Linq.IQueryable%601>\-Schnittstelle implementiert, dienen als Datenquelle für [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen.  Die generische Klasse <xref:System.Data.Objects.ObjectQuery%601> stellt eine Abfrage dar, die eine Auflistung von null oder mehr typisierten Entitätsobjekten zurückgibt.  Sie können auch den Compiler mit dem C\#\-Schlüsselwort `var` \(Dim in Visual Basic\) den Typ einer Entität ableiten lassen.  
  
 In der Abfrage geben Sie genau die Informationen an, die aus der Datenquelle abgerufen werden sollen.  In der Abfrage kann auch angegeben werden, wie die Abfrageergebnisse sortiert, gruppiert und formatiert werden sollen, bevor sie zurückgegeben werden.  In LINQ wird eine Abfrage in einer Variablen gespeichert.  Wenn die Abfrage eine Sequenz von Werten zurückgibt, muss die Abfragevariable selbst ein abfragbarer Typ sein.  Diese Abfragevariable führt keine Aktion aus und gibt keine Daten zurück. Sie dient lediglich zur Speicherung der Abfrageinformationen.  Nachdem Sie eine Abfrage erstellt haben, müssen Sie sie ausführen, damit Daten abgerufen werden.  
  
## Abfragesyntax  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen können sich aus zwei verschiedenen Syntaxarten zusammensetzen: in der Abfrageausdrucksyntax und in der methodenbasierten Abfragesyntax.  Abfrageausdrucksyntax ist in C\# 3.0 und Visual Basic 9.0 neu. Sie besteht aus einem Satz von in einer deklarativen Syntax geschriebenen Klauseln, ähnlich Transact\-SQL oder XQuery.  Beachten Sie jedoch, dass die [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]\-Common Language Runtime \(CLR\) die Abfrageausdruckssyntax selbst nicht lesen kann.  Daher werden die Abfrageausdrücke beim Kompilieren in etwas übersetzt, was die CLR versteht: Methodenaufrufe.  Diese Methoden werden als *Standardabfrageoperatoren* bezeichnet.  Als Entwickler können Sie entscheiden, ob Sie die Methoden mittels Methodensyntax direkt aufrufen möchten oder ob dafür die Abfragesyntax verwendet werden soll. Weitere Informationen finden Sie unter [Query Syntax and Method Syntax in LINQ](../Topic/Query%20Syntax%20and%20Method%20Syntax%20in%20LINQ%20\(C%23\).md).  
  
### Abfrageausdruckssyntax  
 Abfrageausdrücke sind eine deklarative Abfragesyntax.  Mit dieser Syntax kann ein Entwickler Abfragen in einer allgemeinen Programmiersprache in einem Format ähnlich dem von Transact\-SQL schreiben.  Die Abfrageausdruckssyntax ermöglicht die Ausführung komplexer Filter\-, Sortier\- und Gruppiervorgänge mit minimalem Codeeinsatz.  Weitere Informationen finden Sie unter [Grundlegende Abfrageoperationen \(Visual Basic\)](../Topic/Basic%20Query%20Operations%20\(Visual%20Basic\).md).  Beispiele, die veranschaulichen, wie die Abfrageausdrucksyntax verwendet wird, finden Sie in den folgenden Themen:  
  
-   [Beispiele für die Abfrageausdruckssyntax: Projektion](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Filtern](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Sortieren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Partitionierung](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Joinoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Elementoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Gruppierung](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Beispiele für die Abfrageausdruckssyntax: Navigieren in Beziehungen](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### Methodenbasierte Abfragesyntax  
 Eine weitere Möglichkeit [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen zu erstellen, besteht im Verwenden von methodenbasierten Abfragen.  Dabei handelt es sich um eine Abfolge direkter Methodenaufrufe der LINQ\-Operatormethoden, wobei als Parameter Lambda\-Ausdrücke übergeben werden.  Weitere Informationen finden Sie unter [Lambda\-Ausdrücke](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md).  Beispiele, die veranschaulichen, wie die methodenbasierte Syntax verwendet wird, finden Sie in den folgenden Themen:  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Projektion](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Filterung](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Sortieren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Partitionierung](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Konvertierung](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Gruppierung](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## Siehe auch  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)   
 [Getting Started with LINQ in C\#](../Topic/Getting%20Started%20with%20LINQ%20in%20C%23.md)   
 [Getting Started with LINQ in Visual Basic](../Topic/Getting%20Started%20with%20LINQ%20in%20Visual%20Basic.md)   
 [Entity Framework: Zusammenführungsoptionen und kompilierte Abfragen](http://go.microsoft.com/fwlink/?LinkId=199591)