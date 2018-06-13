---
title: Filtern von Daten (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: ad8c167cf1b084c5e05bec84cd5c2f3f05716d03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321492"
---
# <a name="filtering-data-c"></a>Filtern von Daten (C#)
Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen. Es ist auch bekannt als Auswahl.  
  
 Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge. Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.  
  
 ![LINQ-Filtervorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|description|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.|Nicht zutreffend.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|Where|Wählt Werte aus, die auf einer Prädikatfunktion basieren.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Beispiel für die Abfrageausdruckssyntax  
 Im folgenden Beispiel wird die `where`-Klausel verwendet, um die Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 [Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [where-Klausel](../../../../csharp/language-reference/keywords/where-clause.md)  
 [Gewusst wie: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
 [Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [How to: Query for Files with a Specified Attribute or Name (C#) (Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
