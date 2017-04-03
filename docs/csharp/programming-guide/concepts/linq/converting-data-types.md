---
title: Konvertieren von Datentypen (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 922e2f26c5f8ded260644e8effa043b03b721020
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-c"></a>Konvertieren von Datentypen (C#)
Konvertierungsmethoden ändern den Typ von Eingabeobjekten.  
  
 Konvertierungsvorgänge in LINQ-Abfragen sind in vielen Anwendungen nützlich. Nachstehend sind einige Beispiele aufgeführt:  
  
-   Die Methode <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> kann verwendet werden, um die benutzerdefinierte Implementierung eines Standardabfrageoperators eines Typs auszublenden.  
  
-   Die Methode <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> kann verwendet werden, um nicht-parametrisierte Sammlungen für LINQ-Abfragen zu aktivieren.  
  
-   Die Methoden <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> sowie <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> können verwendet werden, um die sofortige Ausführung einer Abfrage zu erzwingen, statt sie so lange zu verzögern, bis die Abfrage aufgelistet wird.  
  
## <a name="methods"></a>Methoden  
 Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.  
  
 Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit „As“ beginnen, ändern den statischen Typ der Quellauflistung, listen ihn jedoch nicht auf. Die Methoden, deren Namen mit „To“ anfangen, listen die Quellauflistung auf und verschieben die Elemente in den entsprechenden Auflistungstyp.  
  
|Methodenname|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|AsEnumerable|Gibt die Eingabe zurück, die als <xref:System.Collections.Generic.IEnumerable%601> festgelegt ist.|Nicht zutreffend.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Konvertiert eine (generische) <xref:System.Collections.IEnumerable>-Methode in eine (generische) <xref:System.Linq.IQueryable>-Methode.|Nicht zutreffend.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Typumwandlung|Kopiert die Elemente einer Auflistung in einen bestimmten Typ.|Verwenden Sie eine explizit typisierte Bereichsvariable. Zum Beispiel:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Filtert Werte, je nach ihrer Fähigkeit, die in einen angegebenen Typ umgewandelt werden sollen.|Nicht zutreffend.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Konvertiert eine Auflistung in ein Array. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Fügt Elemente in eine <xref:System.Collections.Generic.Dictionary%602>-Methode ein, basierend auf einer Schlüsselauswahlfunktion. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>-Methode. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Fügt Elemente, basierend auf einer Schlüsselauswahlfunktion, in ein <xref:System.Linq.Lookup%602> (one-to-many Wörterbuch) ein. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Beispiele für die Abfrageausdruckssyntax  
 Das folgende Codebeispiel verwendet eine explizit typisierte Bereichsvariable, um einen Typ vor dem Zugriff auf ein Element, das nur im Untertyp verfügbar ist, in einen Untertyp umzuwandeln.  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>   
 [Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [From-Klausel](../../../../csharp/language-reference/keywords/from-clause.md)   
 [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
