---
title: Partitionieren von Daten
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 07e33c4ce0d062a0f083d8970c0ad01f98923a52
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075316"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="b7c3f-102">Partitionierung von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7c3f-102">Partitioning Data (Visual Basic)</span></span>

<span data-ttu-id="b7c3f-103">Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="b7c3f-104">Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="b7c3f-105">Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="b7c3f-106">Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="b7c3f-107">Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Abbildung zu drei LINQ-Partitionierungsvorgängen.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="b7c3f-109">Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="b7c3f-110">Operatoren</span><span class="sxs-lookup"><span data-stu-id="b7c3f-110">Operators</span></span>  
  
|<span data-ttu-id="b7c3f-111">Name des Operators</span><span class="sxs-lookup"><span data-stu-id="b7c3f-111">Operator Name</span></span>|<span data-ttu-id="b7c3f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7c3f-112">Description</span></span>|<span data-ttu-id="b7c3f-113">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="b7c3f-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b7c3f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7c3f-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="b7c3f-115">Skip</span><span class="sxs-lookup"><span data-stu-id="b7c3f-115">Skip</span></span>|<span data-ttu-id="b7c3f-116">Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="b7c3f-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7c3f-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="b7c3f-117">SkipWhile</span></span>|<span data-ttu-id="b7c3f-118">Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="b7c3f-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7c3f-119">Take</span><span class="sxs-lookup"><span data-stu-id="b7c3f-119">Take</span></span>|<span data-ttu-id="b7c3f-120">Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="b7c3f-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7c3f-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="b7c3f-121">TakeWhile</span></span>|<span data-ttu-id="b7c3f-122">Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt</span><span class="sxs-lookup"><span data-stu-id="b7c3f-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b7c3f-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="b7c3f-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="b7c3f-124">Überspringen</span><span class="sxs-lookup"><span data-stu-id="b7c3f-124">Skip</span></span>  

 <span data-ttu-id="b7c3f-125">Im folgenden Codebeispiel wird die- `Skip` Klausel in Visual Basic verwendet, um die ersten vier Zeichen folgen in einem Array von Zeichen folgen zu überspringen, bevor die restlichen Zeichen folgen im Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="b7c3f-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="b7c3f-126">SkipWhile</span></span>  

 <span data-ttu-id="b7c3f-127">Im folgenden Codebeispiel wird die- `Skip While` Klausel in Visual Basic verwendet, um die Zeichen folgen in einem Array zu überspringen, während der erste Buchstabe der Zeichenfolge "a" ist.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="b7c3f-128">Die verbleibenden Zeichen folgen im Array werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="b7c3f-129">Take</span><span class="sxs-lookup"><span data-stu-id="b7c3f-129">Take</span></span>  

 <span data-ttu-id="b7c3f-130">Im folgenden Codebeispiel wird die- `Take` Klausel in Visual Basic verwendet, um die ersten beiden Zeichen folgen in einem Array von Zeichen folgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="b7c3f-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="b7c3f-131">TakeWhile</span></span>  

 <span data-ttu-id="b7c3f-132">Im folgenden Codebeispiel wird die- `Take While` Klausel in Visual Basic verwendet, um Zeichen folgen aus einem Array zurückzugeben, während die Länge der Zeichenfolge fünf oder kleiner ist.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b7c3f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7c3f-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b7c3f-134">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="b7c3f-134">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="b7c3f-135">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7c3f-135">Skip Clause</span></span>](../../../language-reference/queries/skip-clause.md)
- [<span data-ttu-id="b7c3f-136">SkipWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7c3f-136">Skip While Clause</span></span>](../../../language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="b7c3f-137">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7c3f-137">Take Clause</span></span>](../../../language-reference/queries/take-clause.md)
- [<span data-ttu-id="b7c3f-138">TakeWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7c3f-138">Take While Clause</span></span>](../../../language-reference/queries/take-while-clause.md)
