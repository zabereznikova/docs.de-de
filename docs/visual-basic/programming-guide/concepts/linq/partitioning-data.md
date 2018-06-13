---
title: Partitionieren von Daten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 17e929d3c95e079a0a73b8e8cadf51d3ece6f5f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645911"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="42f54-102">Partitionieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42f54-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="42f54-103">Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.</span><span class="sxs-lookup"><span data-stu-id="42f54-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="42f54-104">Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="42f54-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="42f54-105">Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="42f54-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="42f54-106">Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="42f54-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="42f54-107">Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="42f54-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="42f54-108">![LINQ-Partitionierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="42f54-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="42f54-109">Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="42f54-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="42f54-110">Operatoren</span><span class="sxs-lookup"><span data-stu-id="42f54-110">Operators</span></span>  
  
|<span data-ttu-id="42f54-111">Name des Operators</span><span class="sxs-lookup"><span data-stu-id="42f54-111">Operator Name</span></span>|<span data-ttu-id="42f54-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42f54-112">Description</span></span>|<span data-ttu-id="42f54-113">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="42f54-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="42f54-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42f54-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="42f54-115">Skip</span><span class="sxs-lookup"><span data-stu-id="42f54-115">Skip</span></span>|<span data-ttu-id="42f54-116">Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="42f54-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42f54-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="42f54-117">SkipWhile</span></span>|<span data-ttu-id="42f54-118">Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="42f54-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42f54-119">Take</span><span class="sxs-lookup"><span data-stu-id="42f54-119">Take</span></span>|<span data-ttu-id="42f54-120">Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="42f54-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="42f54-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="42f54-121">TakeWhile</span></span>|<span data-ttu-id="42f54-122">Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="42f54-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="42f54-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="42f54-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="42f54-124">Skip</span><span class="sxs-lookup"><span data-stu-id="42f54-124">Skip</span></span>  
 <span data-ttu-id="42f54-125">Im folgenden Codebeispiel wird mit der `Skip` -Klausel in Visual Basic, überspringen die ersten vier Zeichenfolgen in ein Array von Zeichenfolgen vor der Rückgabe der verbleibenden Zeichenfolgen im Array.</span><span class="sxs-lookup"><span data-stu-id="42f54-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a><span data-ttu-id="42f54-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="42f54-126">SkipWhile</span></span>  
 <span data-ttu-id="42f54-127">Im folgenden Codebeispiel wird mit der `Skip While` -Klausel in Visual Basic, um die Zeichenfolgen in einem Array überspringen, wenn es sich bei der erste Buchstaben der Zeichenfolge ist "a".</span><span class="sxs-lookup"><span data-stu-id="42f54-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="42f54-128">Die übrigen Zeichenfolgen im Array werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42f54-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a><span data-ttu-id="42f54-129">Take</span><span class="sxs-lookup"><span data-stu-id="42f54-129">Take</span></span>  
 <span data-ttu-id="42f54-130">Im folgenden Codebeispiel wird mit der `Take` -Klausel in Visual Basic, um die ersten zwei Zeichenfolgen in ein Array von Zeichenfolgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="42f54-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a><span data-ttu-id="42f54-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="42f54-131">TakeWhile</span></span>  
 <span data-ttu-id="42f54-132">Im folgenden Codebeispiel wird mit der `Take While` -Klausel in Visual Basic, um Zeichenfolgen aus einem Array zurück, während die Länge der Zeichenfolge fünf oder weniger beträgt.</span><span class="sxs-lookup"><span data-stu-id="42f54-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="42f54-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42f54-133">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="42f54-134">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="42f54-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="42f54-135">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="42f54-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="42f54-136">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="42f54-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="42f54-137">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="42f54-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="42f54-138">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="42f54-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
