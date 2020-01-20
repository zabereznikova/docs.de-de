---
title: Gruppieren von Daten (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 7ef3d3c9097d7a9478605565518ac8975feb9fe2
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635742"
---
# <a name="grouping-data-c"></a><span data-ttu-id="7c78b-102">Gruppieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="7c78b-102">Grouping Data (C#)</span></span>
<span data-ttu-id="7c78b-103">Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="7c78b-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="7c78b-104">Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7c78b-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="7c78b-105">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="7c78b-105">The key for each group is the character.</span></span>  
  
 ![Diagramm, das eine LINQ-Gruppierung zeigt.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="7c78b-107">Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7c78b-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c78b-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="7c78b-108">Methods</span></span>  
  
|<span data-ttu-id="7c78b-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="7c78b-109">Method Name</span></span>|<span data-ttu-id="7c78b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c78b-110">Description</span></span>|<span data-ttu-id="7c78b-111">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="7c78b-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="7c78b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c78b-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="7c78b-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="7c78b-113">GroupBy</span></span>|<span data-ttu-id="7c78b-114">Gruppenelemente, die über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="7c78b-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="7c78b-115">Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7c78b-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="7c78b-116">- oder -</span><span class="sxs-lookup"><span data-stu-id="7c78b-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="7c78b-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="7c78b-117">ToLookup</span></span>|<span data-ttu-id="7c78b-118">Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="7c78b-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="7c78b-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="7c78b-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="7c78b-120">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="7c78b-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="7c78b-121">Im folgenden Codebeispiel wird die `group by`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="7c78b-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c78b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c78b-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="7c78b-123">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="7c78b-123">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="7c78b-124">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="7c78b-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="7c78b-125">Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="7c78b-125">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="7c78b-126">Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7c78b-126">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="7c78b-127">Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="7c78b-127">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="7c78b-128">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="7c78b-128">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="7c78b-129">Vorgehensweise: Aufteilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7c78b-129">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
