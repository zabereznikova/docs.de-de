---
title: Partitionieren von Daten (C#)
description: Erfahren Sie, wie Sie Daten in LINQ partitionieren. Sehen Sie sich eine Abbildung mit den Ergebnissen von Partitionierungsvorgängen an.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 31beacd672addb3eb38ade8f2bf9cfae25f4d27a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176265"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="57fca-104">Partitionieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="57fca-104">Partitioning Data (C#)</span></span>

<span data-ttu-id="57fca-105">Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.</span><span class="sxs-lookup"><span data-stu-id="57fca-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="57fca-106">Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="57fca-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="57fca-107">Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="57fca-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="57fca-108">Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="57fca-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="57fca-109">Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="57fca-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Abbildung zu drei LINQ-Partitionierungsvorgängen.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="57fca-111">Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="57fca-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="57fca-112">Operatoren</span><span class="sxs-lookup"><span data-stu-id="57fca-112">Operators</span></span>  
  
|<span data-ttu-id="57fca-113">Name des Operators</span><span class="sxs-lookup"><span data-stu-id="57fca-113">Operator Name</span></span>|<span data-ttu-id="57fca-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57fca-114">Description</span></span>|<span data-ttu-id="57fca-115">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="57fca-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="57fca-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57fca-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="57fca-117">Skip</span><span class="sxs-lookup"><span data-stu-id="57fca-117">Skip</span></span>|<span data-ttu-id="57fca-118">Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="57fca-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="57fca-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="57fca-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57fca-120">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="57fca-120">SkipWhile</span></span>|<span data-ttu-id="57fca-121">Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="57fca-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="57fca-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="57fca-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57fca-123">Take</span><span class="sxs-lookup"><span data-stu-id="57fca-123">Take</span></span>|<span data-ttu-id="57fca-124">Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="57fca-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="57fca-125">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="57fca-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57fca-126">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="57fca-126">TakeWhile</span></span>|<span data-ttu-id="57fca-127">Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="57fca-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="57fca-128">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="57fca-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="57fca-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57fca-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="57fca-130">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="57fca-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
