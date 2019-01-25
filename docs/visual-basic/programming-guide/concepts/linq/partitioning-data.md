---
title: Partitionieren von Daten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: afbbd479d3dadd69b81cdd6aead0a4263b92dfe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728267"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="988fa-102">Partitionieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="988fa-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="988fa-103">Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.</span><span class="sxs-lookup"><span data-stu-id="988fa-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="988fa-104">Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="988fa-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="988fa-105">Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="988fa-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="988fa-106">Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="988fa-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="988fa-107">Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="988fa-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="988fa-108">![LINQ-Partitionierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="988fa-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="988fa-109">Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="988fa-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="988fa-110">Operatoren</span><span class="sxs-lookup"><span data-stu-id="988fa-110">Operators</span></span>  
  
|<span data-ttu-id="988fa-111">Name des Operators</span><span class="sxs-lookup"><span data-stu-id="988fa-111">Operator Name</span></span>|<span data-ttu-id="988fa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="988fa-112">Description</span></span>|<span data-ttu-id="988fa-113">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="988fa-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="988fa-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="988fa-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="988fa-115">Skip</span><span class="sxs-lookup"><span data-stu-id="988fa-115">Skip</span></span>|<span data-ttu-id="988fa-116">Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="988fa-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="988fa-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="988fa-117">SkipWhile</span></span>|<span data-ttu-id="988fa-118">Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="988fa-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="988fa-119">Take</span><span class="sxs-lookup"><span data-stu-id="988fa-119">Take</span></span>|<span data-ttu-id="988fa-120">Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="988fa-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="988fa-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="988fa-121">TakeWhile</span></span>|<span data-ttu-id="988fa-122">Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="988fa-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="988fa-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="988fa-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="988fa-124">Skip</span><span class="sxs-lookup"><span data-stu-id="988fa-124">Skip</span></span>  
 <span data-ttu-id="988fa-125">Im folgenden Codebeispiel wird die `Skip` -Klausel in Visual Basic, um über die ersten vier Zeichenfolgen in ein Array von Zeichenfolgen zu überspringen, vor der Rückgabe die restlichen Zeichenfolgen im Array.</span><span class="sxs-lookup"><span data-stu-id="988fa-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a><span data-ttu-id="988fa-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="988fa-126">SkipWhile</span></span>  
 <span data-ttu-id="988fa-127">Im folgenden Codebeispiel wird die `Skip While` -Klausel in Visual Basic, um die Zeichenfolgen in einem Array überspringen, wenn es sich bei den ersten Buchstaben der Zeichenfolge ist "a".</span><span class="sxs-lookup"><span data-stu-id="988fa-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="988fa-128">Es werden die restlichen Zeichenfolgen im Array zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="988fa-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a><span data-ttu-id="988fa-129">Take</span><span class="sxs-lookup"><span data-stu-id="988fa-129">Take</span></span>  
 <span data-ttu-id="988fa-130">Im folgenden Codebeispiel wird die `Take` -Klausel in Visual Basic, um die ersten beiden Zeichenfolgen in ein Array von Zeichenfolgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="988fa-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a><span data-ttu-id="988fa-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="988fa-131">TakeWhile</span></span>  
 <span data-ttu-id="988fa-132">Im folgenden Codebeispiel wird die `Take While` -Klausel in Visual Basic, um Zeichenfolgen aus einem Array zurück, während sich die Länge der Zeichenfolge bis zu fünf befindet.</span><span class="sxs-lookup"><span data-stu-id="988fa-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="988fa-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="988fa-133">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="988fa-134">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="988fa-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="988fa-135">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="988fa-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="988fa-136">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="988fa-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="988fa-137">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="988fa-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="988fa-138">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="988fa-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
