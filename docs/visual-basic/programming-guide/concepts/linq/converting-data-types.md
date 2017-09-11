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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 948779e1648291b00a68bfd83d57750d48a9a6d8
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="21849-102">Konvertieren von Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21849-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="21849-103">Konvertierungsmethoden ändern Sie den Typ von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="21849-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="21849-104">Konvertierungsoperationen in LINQ-Abfragen eignen sich in einer Vielzahl von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="21849-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="21849-105">Im folgenden sind einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="21849-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="21849-106">Die <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>Methode kann verwendet werden, um einen Typ benutzerdefinierte Implementierung eines Standardabfrageoperators ausblenden.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="21849-107">Die <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>Methode kann verwendet werden, um Sammlungen für LINQ-Abfragen nicht parametrisierten aktivieren.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="21849-108">Die <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, und <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>Methoden verwendet werden können, erzwingen der unmittelbaren Ausführung statt es verzögern, bis die Abfrage aufgelistet wird.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21849-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="21849-109">Methods</span></span>  
 <span data-ttu-id="21849-110">Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="21849-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="21849-111">Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit beginnen, "Wie" ändern den statischen Typ der Auflistung, aber nicht aufgelistet, wird.</span><span class="sxs-lookup"><span data-stu-id="21849-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="21849-112">Geben Sie die Methoden, deren Namen mit "Zu Auflisten der Quellsammlung und die Elemente in der entsprechenden Auflistung" zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="21849-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="21849-113">Methodenname</span><span class="sxs-lookup"><span data-stu-id="21849-113">Method Name</span></span>|<span data-ttu-id="21849-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21849-114">Description</span></span>|<span data-ttu-id="21849-115">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="21849-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="21849-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21849-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="21849-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="21849-117">AsEnumerable</span></span>|<span data-ttu-id="21849-118">Gibt die Eingabe als <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="21849-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="21849-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-119">Not applicable.</span></span>|<span data-ttu-id="21849-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="21849-121">AsQueryable</span></span>|<span data-ttu-id="21849-122">Konvertiert ein (generisches) <xref:System.Collections.IEnumerable>auf eine <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (Standard)</xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="21849-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="21849-123">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-123">Not applicable.</span></span>|<span data-ttu-id="21849-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-125">Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="21849-125">Cast</span></span>|<span data-ttu-id="21849-126">Wandelt die Elemente einer Auflistung in einen angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="21849-126">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<span data-ttu-id="21849-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="21849-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-129">OfType</span><span class="sxs-lookup"><span data-stu-id="21849-129">OfType</span></span>|<span data-ttu-id="21849-130">Filtert je nach ihrer Fähigkeit in einen angegebenen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="21849-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="21849-131">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-131">Not applicable.</span></span>|<span data-ttu-id="21849-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="21849-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-134">ToArray</span><span class="sxs-lookup"><span data-stu-id="21849-134">ToArray</span></span>|<span data-ttu-id="21849-135">Konvertiert eine Auflistung in ein Array.</span><span class="sxs-lookup"><span data-stu-id="21849-135">Converts a collection to an array.</span></span> <span data-ttu-id="21849-136">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="21849-136">This method forces query execution.</span></span>|<span data-ttu-id="21849-137">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-137">Not applicable.</span></span>|<span data-ttu-id="21849-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-139">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="21849-139">ToDictionary</span></span>|<span data-ttu-id="21849-140">Fügt Elemente in einer <xref:System.Collections.Generic.Dictionary%602>basierend auf einer Schlüsselauswahlfunktion.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="21849-140">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="21849-141">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="21849-141">This method forces query execution.</span></span>|<span data-ttu-id="21849-142">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-142">Not applicable.</span></span>|<span data-ttu-id="21849-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-144">ToList</span><span class="sxs-lookup"><span data-stu-id="21849-144">ToList</span></span>|<span data-ttu-id="21849-145">Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="21849-145">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="21849-146">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="21849-146">This method forces query execution.</span></span>|<span data-ttu-id="21849-147">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-147">Not applicable.</span></span>|<span data-ttu-id="21849-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="21849-149">ToLookup</span><span class="sxs-lookup"><span data-stu-id="21849-149">ToLookup</span></span>|<span data-ttu-id="21849-150">Fügt Elemente in einer <xref:System.Linq.Lookup%602>(ein&1;: n-Wörterbuch) basierend auf einer Schlüsselauswahlfunktion.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="21849-150">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="21849-151">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="21849-151">This method forces query execution.</span></span>|<span data-ttu-id="21849-152">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="21849-152">Not applicable.</span></span>|<span data-ttu-id="21849-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="21849-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="21849-154">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="21849-154">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="21849-155">Im folgenden Codebeispiel wird die `From As` -Klausel, um einen Typ in einen Untertyp umzuwandeln, vor dem Zugriff auf ein Element, das nur im Untertyp verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="21849-155">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21849-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21849-156">See Also</span></span>  
 <span data-ttu-id="21849-157"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="21849-157"><xref:System.Linq></span></span>   
<span data-ttu-id="21849-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="21849-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="21849-159"> [FROM-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="21849-159"> [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="21849-160"> [Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="21849-160"> [How to: Query an ArrayList with LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span></span>
