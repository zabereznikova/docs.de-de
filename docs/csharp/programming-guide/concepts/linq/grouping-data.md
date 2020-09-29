---
title: Gruppieren von Daten (C#)
description: Beim Gruppieren werden Daten in Gruppen von Elementen zusammengefasst, die alle über ein bestimmtes Attribut verfügen. Hier erfahren Sie mehr über die Standardabfrageoperatoren in LINQ in C#, die Datenelemente gruppieren.
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 584d50fc15dd8b4ce1cfdf4766f3bc8b8383eb12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202564"
---
# <a name="grouping-data-c"></a><span data-ttu-id="57375-104">Gruppieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="57375-104">Grouping Data (C#)</span></span>

<span data-ttu-id="57375-105">Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="57375-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="57375-106">Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="57375-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="57375-107">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="57375-107">The key for each group is the character.</span></span>  
  
 ![Diagramm, das eine LINQ-Gruppierung zeigt.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="57375-109">Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="57375-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57375-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="57375-110">Methods</span></span>  
  
|<span data-ttu-id="57375-111">Methodenname</span><span class="sxs-lookup"><span data-stu-id="57375-111">Method Name</span></span>|<span data-ttu-id="57375-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57375-112">Description</span></span>|<span data-ttu-id="57375-113">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="57375-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="57375-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57375-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="57375-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="57375-115">GroupBy</span></span>|<span data-ttu-id="57375-116">Gruppenelemente, die über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="57375-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="57375-117">Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="57375-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="57375-118">- oder -</span><span class="sxs-lookup"><span data-stu-id="57375-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57375-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="57375-119">ToLookup</span></span>|<span data-ttu-id="57375-120">Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="57375-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="57375-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="57375-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="57375-122">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="57375-122">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="57375-123">Im folgenden Codebeispiel wird die `group by`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="57375-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="57375-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57375-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="57375-125">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="57375-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="57375-126">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="57375-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="57375-127">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="57375-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="57375-128">Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="57375-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="57375-129">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="57375-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="57375-130">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="57375-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="57375-131">Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="57375-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
