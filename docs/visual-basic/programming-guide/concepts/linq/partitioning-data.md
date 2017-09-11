---
title: Partitionieren von Daten (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
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
ms.openlocfilehash: 9d0df2bc473f48fba4bbb094317166407f7c7ec2
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="2a43f-102">Partitionieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a43f-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="2a43f-103">Partitionieren in LINQ ist für die Ausführung einer Eingabesequenz in zwei Abschnitte unterteilt, ohne die Elemente neu anordnen und anschließend einen der Abschnitte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a43f-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="2a43f-104">Die folgende Abbildung zeigt die Ergebnisse von drei verschiedenen Partitionierung Operationen für eine Sequenz von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2a43f-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="2a43f-105">Die erste Operation gibt die ersten drei Elemente in der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="2a43f-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="2a43f-106">Die zweite Operation überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="2a43f-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="2a43f-107">Die dritte Operation überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="2a43f-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="2a43f-108">![LINQ-Partitionierung Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="2a43f-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="2a43f-109">Die Standardabfrageoperator-Methoden, die Sequenzen partitionieren, werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2a43f-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="2a43f-110">Operatoren</span><span class="sxs-lookup"><span data-stu-id="2a43f-110">Operators</span></span>  
  
|<span data-ttu-id="2a43f-111">Name des Operators</span><span class="sxs-lookup"><span data-stu-id="2a43f-111">Operator Name</span></span>|<span data-ttu-id="2a43f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a43f-112">Description</span></span>|<span data-ttu-id="2a43f-113">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2a43f-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2a43f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a43f-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="2a43f-115">Skip</span><span class="sxs-lookup"><span data-stu-id="2a43f-115">Skip</span></span>|<span data-ttu-id="2a43f-116">Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="2a43f-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<span data-ttu-id="2a43f-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2a43f-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2a43f-119">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="2a43f-119">SkipWhile</span></span>|<span data-ttu-id="2a43f-120">Überspringt die Elemente basierend auf einer Prädikatfunktion, bis ein Element die Bedingung nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2a43f-120">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<span data-ttu-id="2a43f-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2a43f-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2a43f-123">Take</span><span class="sxs-lookup"><span data-stu-id="2a43f-123">Take</span></span>|<span data-ttu-id="2a43f-124">Übernimmt die Elemente bis zu einer angegebenen Position in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="2a43f-124">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<span data-ttu-id="2a43f-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2a43f-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2a43f-127">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="2a43f-127">TakeWhile</span></span>|<span data-ttu-id="2a43f-128">Übernimmt die Elemente basierend auf einer Prädikatfunktion, bis ein Element die Bedingung nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2a43f-128">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<span data-ttu-id="2a43f-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2a43f-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2a43f-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="2a43f-131">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2a43f-131">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="2a43f-132">Skip</span><span class="sxs-lookup"><span data-stu-id="2a43f-132">Skip</span></span>  
 <span data-ttu-id="2a43f-133">Im folgenden Codebeispiel wird die `Skip` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] über die ersten vier Zeichenfolgen in einem Array von Zeichenfolgen zu überspringen, bevor die restlichen Zeichenfolgen im Array zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a43f-133">The following code example uses the `Skip` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 <span data-ttu-id="2a43f-134">[!code-vb[CsLINQPartitioning&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a43f-134">[!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span></span>  
  
### <a name="skipwhile"></a><span data-ttu-id="2a43f-135">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="2a43f-135">SkipWhile</span></span>  
 <span data-ttu-id="2a43f-136">Im folgenden Codebeispiel wird die `Skip While` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , überspringen die Zeichenfolgen in einem Array, wenn der erste Buchstabe der Zeichenfolge ist "a".</span><span class="sxs-lookup"><span data-stu-id="2a43f-136">The following code example uses the `Skip While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="2a43f-137">Die übrigen Zeichenfolgen im Array werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a43f-137">The remaining strings in the array are returned.</span></span>  
  
 <span data-ttu-id="2a43f-138">[!code-vb[CsLINQPartitioning&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a43f-138">[!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span></span>  
  
### <a name="take"></a><span data-ttu-id="2a43f-139">Take</span><span class="sxs-lookup"><span data-stu-id="2a43f-139">Take</span></span>  
 <span data-ttu-id="2a43f-140">Im folgenden Codebeispiel wird die `Take` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die ersten zwei Zeichenfolgen in einem Array von Zeichenfolgen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2a43f-140">The following code example uses the `Take` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return the first two strings in an array of strings.</span></span>  
  
 <span data-ttu-id="2a43f-141">[!code-vb[CsLINQPartitioning&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a43f-141">[!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span></span>  
  
### <a name="takewhile"></a><span data-ttu-id="2a43f-142">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="2a43f-142">TakeWhile</span></span>  
 <span data-ttu-id="2a43f-143">Im folgenden Codebeispiel wird die `Take While` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] um Zeichenfolgen aus einem Array zurückzugeben, wenn die Länge der Zeichenfolge fünf oder weniger beträgt.</span><span class="sxs-lookup"><span data-stu-id="2a43f-143">The following code example uses the `Take While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return strings from an array while the length of the string is five or less.</span></span>  
  
 <span data-ttu-id="2a43f-144">[!code-vb[CsLINQPartitioning&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a43f-144">[!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a43f-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a43f-145">See Also</span></span>  
 <span data-ttu-id="2a43f-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2a43f-146"><xref:System.Linq></span></span>   
<span data-ttu-id="2a43f-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2a43f-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="2a43f-148"> [Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2a43f-148"> [Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md) </span></span>  
<span data-ttu-id="2a43f-149"> [Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2a43f-149"> [Skip While Clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span></span>  
<span data-ttu-id="2a43f-150"> [Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2a43f-150"> [Take Clause](../../../../visual-basic/language-reference/queries/take-clause.md) </span></span>  
<span data-ttu-id="2a43f-151"> [Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span><span class="sxs-lookup"><span data-stu-id="2a43f-151"> [Take While Clause](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span></span>
