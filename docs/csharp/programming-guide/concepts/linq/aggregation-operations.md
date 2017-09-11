---
title: "Aggregationsvorgänge (C#)"
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
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6c453bdccdb3af026fe4f4fb79c6e33e44e7a8f0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="aggregation-operations-c"></a><span data-ttu-id="0664b-102">Aggregationsvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="0664b-102">Aggregation Operations (C#)</span></span>
<span data-ttu-id="0664b-103">Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet.</span><span class="sxs-lookup"><span data-stu-id="0664b-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="0664b-104">Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats.</span><span class="sxs-lookup"><span data-stu-id="0664b-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="0664b-105">Die folgende Abbildung zeigt das Ergebnis von zwei verschiedenen Aggregationsvorgängen bei einer Zahlensequenz.</span><span class="sxs-lookup"><span data-stu-id="0664b-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="0664b-106">Der erste Vorgang zählt die Zahlen zusammen.</span><span class="sxs-lookup"><span data-stu-id="0664b-106">The first operation sums the numbers.</span></span> <span data-ttu-id="0664b-107">Der zweite Vorgang gibt den höchsten Wert der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="0664b-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="0664b-108">![LINQ-Aggregationsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="0664b-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="0664b-109">Die Methoden des Standardabfrageoperators, die Aggregationsvorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0664b-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0664b-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="0664b-110">Methods</span></span>  
  
|<span data-ttu-id="0664b-111">Methodenname</span><span class="sxs-lookup"><span data-stu-id="0664b-111">Method Name</span></span>|<span data-ttu-id="0664b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0664b-112">Description</span></span>|<span data-ttu-id="0664b-113">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="0664b-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="0664b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0664b-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="0664b-115">Aggregat</span><span class="sxs-lookup"><span data-stu-id="0664b-115">Aggregate</span></span>|<span data-ttu-id="0664b-116">Führt einen benutzerdefinierten Aggregationsvorgang für die Werte einer Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="0664b-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="0664b-117">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-118">Average</span><span class="sxs-lookup"><span data-stu-id="0664b-118">Average</span></span>|<span data-ttu-id="0664b-119">Berechnet den Durchschnittswert einer Auflistung von Werten.</span><span class="sxs-lookup"><span data-stu-id="0664b-119">Calculates the average value of a collection of values.</span></span>|<span data-ttu-id="0664b-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-121">Anzahl</span><span class="sxs-lookup"><span data-stu-id="0664b-121">Count</span></span>|<span data-ttu-id="0664b-122">Zählt die Elemente einer Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0664b-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="0664b-123">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="0664b-124">LongCount</span></span>|<span data-ttu-id="0664b-125">Zählt die Elemente einer großen Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0664b-125">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="0664b-126">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-127">Max.</span><span class="sxs-lookup"><span data-stu-id="0664b-127">Max</span></span>|<span data-ttu-id="0664b-128">Bestimmt den Maximalwert einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0664b-128">Determines the maximum value in a collection.</span></span>|<span data-ttu-id="0664b-129">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-130">Min.</span><span class="sxs-lookup"><span data-stu-id="0664b-130">Min</span></span>|<span data-ttu-id="0664b-131">Bestimmt den Minimalwert einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0664b-131">Determines the minimum value in a collection.</span></span>|<span data-ttu-id="0664b-132">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|<span data-ttu-id="0664b-133">Summe</span><span class="sxs-lookup"><span data-stu-id="0664b-133">Sum</span></span>|<span data-ttu-id="0664b-134">Berechnet die Summe der Werte einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0664b-134">Calculates the sum of the values in a collection.</span></span>|<span data-ttu-id="0664b-135">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0664b-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="0664b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0664b-136">See Also</span></span>  
 <span data-ttu-id="0664b-137"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="0664b-137"><xref:System.Linq></span></span>   
 <span data-ttu-id="0664b-138">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="0664b-138">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="0664b-139">[Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span><span class="sxs-lookup"><span data-stu-id="0664b-139">[How to: Compute Column Values in a CSV Text File (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md) </span></span>  
 <span data-ttu-id="0664b-140">[How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#) (Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span><span class="sxs-lookup"><span data-stu-id="0664b-140">[How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md) </span></span>  
 [<span data-ttu-id="0664b-141">Vorgehensweise: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0664b-141">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)

