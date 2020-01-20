---
title: Konvertieren von Datentypen (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 328c790a1a360907c91f69b3b6330b0b25eb414b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347204"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="f167c-102">Konvertieren von Datentypen (C#)</span><span class="sxs-lookup"><span data-stu-id="f167c-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="f167c-103">Konvertierungsmethoden ändern den Typ von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="f167c-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="f167c-104">Konvertierungsvorgänge in LINQ-Abfragen sind in vielen Anwendungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="f167c-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="f167c-105">Nachstehend sind einige Beispiele aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f167c-105">Following are some examples:</span></span>

- <span data-ttu-id="f167c-106">Die <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>-Methode kann zum Ausblenden einer benutzerdefinierten Implementierung eines Standardabfrageoperators eines Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f167c-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="f167c-107">Die <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType>-Methode kann verwendet werden, um nicht parametrisierte Auflistungen für LINQ-Abfragen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f167c-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="f167c-108">Die Methoden <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> und <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> können verwendet werden, um die sofortige Ausführung einer Abfrage zu erzwingen, statt sie zu verzögern, bis die Abfrage enumeriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f167c-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="f167c-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f167c-109">Methods</span></span>
 <span data-ttu-id="f167c-110">Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f167c-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="f167c-111">Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit „As“ beginnen, ändern den statischen Typ der Quellauflistung, listen ihn jedoch nicht auf.</span><span class="sxs-lookup"><span data-stu-id="f167c-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="f167c-112">Die Methoden, deren Namen mit „To“ anfangen, listen die Quellauflistung auf und verschieben die Elemente in den entsprechenden Auflistungstyp.</span><span class="sxs-lookup"><span data-stu-id="f167c-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="f167c-113">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f167c-113">Method Name</span></span>|<span data-ttu-id="f167c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f167c-114">Description</span></span>|<span data-ttu-id="f167c-115">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f167c-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="f167c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f167c-116">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="f167c-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="f167c-117">AsEnumerable</span></span>|<span data-ttu-id="f167c-118">Gibt die Eingabe als <xref:System.Collections.Generic.IEnumerable%601> typisiert zurück</span><span class="sxs-lookup"><span data-stu-id="f167c-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="f167c-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="f167c-120">AsQueryable</span></span>|<span data-ttu-id="f167c-121">Konvertiert ein (generisches) <xref:System.Collections.IEnumerable>-Element in ein (generisches) <xref:System.Linq.IQueryable>-Element</span><span class="sxs-lookup"><span data-stu-id="f167c-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="f167c-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-123">Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="f167c-123">Cast</span></span>|<span data-ttu-id="f167c-124">Kopiert die Elemente einer Auflistung in einen bestimmten Typ.</span><span class="sxs-lookup"><span data-stu-id="f167c-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="f167c-125">Verwenden Sie eine explizit typisierte Bereichsvariable.</span><span class="sxs-lookup"><span data-stu-id="f167c-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="f167c-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f167c-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-127">OfType</span><span class="sxs-lookup"><span data-stu-id="f167c-127">OfType</span></span>|<span data-ttu-id="f167c-128">Filtert Werte, je nach ihrer Fähigkeit, die in einen angegebenen Typ umgewandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f167c-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="f167c-129">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="f167c-130">ToArray</span></span>|<span data-ttu-id="f167c-131">Konvertiert eine Auflistung in ein Array.</span><span class="sxs-lookup"><span data-stu-id="f167c-131">Converts a collection to an array.</span></span> <span data-ttu-id="f167c-132">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f167c-132">This method forces query execution.</span></span>|<span data-ttu-id="f167c-133">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="f167c-134">ToDictionary</span></span>|<span data-ttu-id="f167c-135">Platziert Elemente in ein <xref:System.Collections.Generic.Dictionary%602> auf Grundlage einer Schlüsselauswahlfunktion.</span><span class="sxs-lookup"><span data-stu-id="f167c-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="f167c-136">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f167c-136">This method forces query execution.</span></span>|<span data-ttu-id="f167c-137">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-138">ToList</span><span class="sxs-lookup"><span data-stu-id="f167c-138">ToList</span></span>|<span data-ttu-id="f167c-139">Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="f167c-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="f167c-140">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f167c-140">This method forces query execution.</span></span>|<span data-ttu-id="f167c-141">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="f167c-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="f167c-142">ToLookup</span></span>|<span data-ttu-id="f167c-143">Platziert Elemente, basierend auf einer Schlüsselauswahlfunktion, in ein <xref:System.Linq.Lookup%602> (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="f167c-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="f167c-144">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f167c-144">This method forces query execution.</span></span>|<span data-ttu-id="f167c-145">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f167c-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="f167c-146">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f167c-146">Query Expression Syntax Example</span></span>

<span data-ttu-id="f167c-147">Das folgende Codebeispiel verwendet eine explizit typisierte Bereichsvariable, um einen Typ vor dem Zugriff auf ein Element, das nur im Untertyp verfügbar ist, in einen Untertyp umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f167c-147">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f167c-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f167c-148">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f167c-149">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="f167c-149">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="f167c-150">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="f167c-150">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="f167c-151">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="f167c-151">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="f167c-152">Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="f167c-152">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
