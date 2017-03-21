---
title: Konvertieren von Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 53d8ad292891a567e13ec8a5396bcc114b379351
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-visual-basic"></a>Konvertieren von Datentypen (Visual Basic)
Konvertierungsmethoden ändern Sie den Typ von Eingabeobjekten.  
  
 Konvertierungsoperationen in LINQ-Abfragen eignen sich in einer Vielzahl von Anwendungen. Im folgenden sind einige Beispiele:  
  
-   Die <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>Methode kann verwendet werden, um einen Typ benutzerdefinierte Implementierung eines Standardabfrageoperators ausblenden.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>  
  
-   Die <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>Methode kann verwendet werden, um Sammlungen für LINQ-Abfragen nicht parametrisierten aktivieren.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>  
  
-   Die <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, und <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>Methoden verwendet werden können, erzwingen der unmittelbaren Ausführung statt es verzögern, bis die Abfrage aufgelistet wird.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>  
  
## <a name="methods"></a>Methoden  
 Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.  
  
 Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit beginnen, "Wie" ändern den statischen Typ der Auflistung, aber nicht aufgelistet, wird. Geben Sie die Methoden, deren Namen mit "Zu Auflisten der Quellsammlung und die Elemente in der entsprechenden Auflistung" zu beginnen.  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|AsEnumerable|Gibt die Eingabe als <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601>|Nicht zutreffend.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Konvertiert ein (generisches) <xref:System.Collections.IEnumerable>auf eine <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (Standard)</xref:System.Collections.IEnumerable>|Nicht zutreffend.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Typumwandlung|Wandelt die Elemente einer Auflistung in einen angegebenen Typ.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Filtert je nach ihrer Fähigkeit in einen angegebenen Typ umgewandelt werden.|Nicht zutreffend.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Konvertiert eine Auflistung in ein Array. Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Fügt Elemente in einer <xref:System.Collections.Generic.Dictionary%602>basierend auf einer Schlüsselauswahlfunktion.</xref:System.Collections.Generic.Dictionary%602> Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Fügt Elemente in einer <xref:System.Linq.Lookup%602>(ein&1;: n-Wörterbuch) basierend auf einer Schlüsselauswahlfunktion.</xref:System.Linq.Lookup%602> Diese Methode erzwingt die Ausführung der Abfrage.|Nicht zutreffend.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Beispiele für die Abfrageausdruckssyntax  
 Im folgenden Codebeispiel wird die `From As` -Klausel, um einen Typ in einen Untertyp umzuwandeln, vor dem Zugriff auf ein Element, das nur im Untertyp verfügbar ist.  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [FROM-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
