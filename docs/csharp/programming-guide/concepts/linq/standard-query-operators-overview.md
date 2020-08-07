---
title: Übersicht über Standardabfrageoperatoren (C#)
description: Die LINQ-Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation und Sortierung in C# bereit.
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 8a399f52881e10f8d94263843b5992101f96a5ea
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302320"
---
# <a name="standard-query-operators-overview-c"></a>Übersicht über Standardabfrageoperatoren (C#)
Die *Standardabfrageoperatoren* sind die Methoden, die das LINQ-Muster bilden. Die meisten dieser Methoden bearbeiten Sequenzen. Eine Sequenz ist hier ein Objekt, dessen Typ die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert. Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung und weitere bereit.  
  
 Es gibt zwei Gruppen von LINQ-Standardabfrageoperatoren: Eine Gruppe funktioniert auf Grundlage von Objekten vom Typ <xref:System.Collections.Generic.IEnumerable%601>, die andere auf Grundlage von Objekten vom Typ <xref:System.Linq.IQueryable%601>. Die Methoden, die eine Gruppe bilden, sind statische Member der Klassen <xref:System.Linq.Enumerable> und <xref:System.Linq.Queryable>. Sie werden als *Erweiterungsmethoden* des Typs, auf dessen Grundlage sie funktionieren, definiert. Erweiterungsmethoden können entweder mit der Syntax für statische Methoden oder mit der für Instanzmethoden aufgerufen werden.  
  
 Darüber hinaus funktionieren mehrere Standardabfrageoperator-Methoden auf Grundlage anderer Typen als die, die auf <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> basieren. Der Typ <xref:System.Linq.Enumerable> definiert zwei Methoden, die beide auf Grundlage von Objekten vom Typ <xref:System.Collections.IEnumerable> funktionieren. Die Methoden <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> und <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> ermöglichen es Ihnen, eine nicht parametrisierte oder nicht generische Auflistung im LINQ-Muster abfragen zu lassen. Dies erfolgt durch Erstellen einer stark typisierten Sammlung von Objekten. Die Klasse <xref:System.Linq.Queryable> definiert zwei ähnliche Methoden, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> und <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, die auf Grundlage von Objekten vom Typ <xref:System.Linq.Queryable> funktionieren.  
  
 Die Standardabfrageoperatoren unterscheiden sich im Zeitpunkt ihrer Ausführung. Dies hängt davon ab, ob sie einen Singleton-Wert oder eine Sequenz von Werten zurückgeben. Die Methoden, die einen Singleton-Wert zurückgeben (z.B. <xref:System.Linq.Enumerable.Average%2A> und <xref:System.Linq.Enumerable.Sum%2A>), werden sofort ausgeführt. Methoden, die eine Sequenz zurückgeben, verzögern die Abfrageausführung und geben ein auflistbares Objekt zurück.  
  
 Bei Methoden, die auf In-Memory-Sammlungen angewendet werden, d. h. den Methoden, die <xref:System.Collections.Generic.IEnumerable%601> erweitern, erfasst das zurückgegebene auflistbare Objekt die Argumente, die an die Methode übergeben wurden. Wenn dieses Objekt auflistbar ist, tritt die Logik des Abfrageoperators in Kraft, und die Abfrageergebnisse werden zurückgegeben.  
  
 Im Gegensatz dazu implementieren Methoden, die <xref:System.Linq.IQueryable%601> erweitern, kein Abfrageverhalten. Sie erstellen eine Ausdrucksbaumstruktur, die die auszuführende Abfrage darstellt. Die Verarbeitung von Abfragen wird vom Quellobjekt <xref:System.Linq.IQueryable%601> übernommen.  
  
 Aufrufe der Abfragemethode können miteinander in eine Abfrage verkettet werden. Dadurch können Abfragen von beliebiger Komplexität sein.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Standardabfrageoperatoren verwendet werden können, um Informationen zu einer Sequenz zu erhalten.  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a>Abfrageausdruckssyntax  
 Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von C# und Visual Basic-Sprache, wodurch sie als Teil eines *query*-*Ausdrucks* aufgerufen werden können. Weitere Informationen über Standardabfrageoperatoren, die über dedizierte Schlüsselwörter und deren entsprechende Syntax verfügen, finden Sie unter [Query Expression Syntax for Standard Query Operators (C#) (Abfrageausdruckssyntax für Standardabfrageoperatoren (C#))](./query-expression-syntax-for-standard-query-operators.md).  
  
## <a name="extending-the-standard-query-operators"></a>Erweitern der Standardabfrageoperatoren  
 Sie können die Gruppe von Standardabfrageoperatoren durch Erstellen von domänenspezifischen Methoden erweitern, die für Ihre Zieldomäne oder -technologie geeignet sind. Sie können die Standardabfrageoperatoren auch mit ihren eigenen Implementierungen ersetzen, die zusätzliche Dienste bieten, z.B. Remote-Auswertung, Abfrageübersetzung und Optimierung. Ein Beispiel finden Sie unter <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Über die folgenden Links gelangen Sie zu Artikeln, die Ihnen weitere Informationen über die verschiedenen Standardabfrageoperatoren basierend auf deren Funktionen bieten.  
  
 [Sorting Data (C#) (Sortieren von Daten (C#))](./sorting-data.md)  
  
 [Set Operations (C#) (Set-Vorgänge (C#))](./set-operations.md)  
  
 [Filtering Data (C#) (Filtern von Daten (C#))](./filtering-data.md)  
  
 [Quantifier Operations (C#) (Quantifizierer-Vorgänge (C#))](./quantifier-operations.md)  
  
 [Projection Operations (C#) (Projektionsvorgänge (C#))](./projection-operations.md)  
  
 [Partitioning Data (C#) (Partitionieren von Daten (C#))](./partitioning-data.md)  
  
 [Join Operations (C#) (Verknüpfungsvorgänge (C#))](./join-operations.md)  
  
 [Grouping Data (C#) (Gruppieren von Daten (C#))](./grouping-data.md)  
  
 [Generation Operations (C#) (Generierungsvorgänge (C#))](./generation-operations.md)  
  
 [quality Operations (C#) (Gleichheitsvorgänge (C#))](./equality-operations.md)  
  
 [Element Operations (C#) (Elementvorgänge (C#))](./element-operations.md)  
  
 [Converting Data Types (C#) (Konvertieren von Datentypen (C#))](./converting-data-types.md)  
  
 [Concatenation Operations (C#) (Verkettungsvorgänge (C#))](./concatenation-operations.md)  
  
 [Aggregation Operations (C#) (Aggregationsvorgänge (C#))](./aggregation-operations.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))](./introduction-to-linq-queries.md)
- [Abfrageausdruckssyntax für Standardabfrageoperatoren (C#)](./query-expression-syntax-for-standard-query-operators.md)
- [Classification of Standard Query Operators by Manner of Execution (C#) (Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (C#))](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md)
