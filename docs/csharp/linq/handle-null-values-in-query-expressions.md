---
title: "Behandeln von NULL-Werten in Abfrageausdrücken"
description: "Vorgehensweise: Behandeln von NULL-Werten in Abfrageausdrücken"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f4f189504c57c9c01268b10bc96ad3c9af49ddbd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="14e10-104">Behandeln von NULL-Werten in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="14e10-104">Handle null values in query expressions</span></span>

<span data-ttu-id="14e10-105">Dieses Beispiel zeigt, wie mögliche NULL-Werte in Quellauflistungen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="14e10-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="14e10-106">Eine Objektauflistung wie z.B. <xref:System.Collections.Generic.IEnumerable%601> kann Elemente enthalten, deren Wert [NULL](../language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="14e10-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="14e10-107">Wenn eine Quellauflistung NULL ist oder ein Element enthält, dessen Wert NULL ist, und die Abfrage keine NULL-Werte verarbeitet, wird eine <xref:System.NullReferenceException> ausgelöst, wenn Sie die Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="14e10-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e10-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14e10-108">Example</span></span>

 <span data-ttu-id="14e10-109">Sie können defensiv codieren, um eine Nullverweisausnahme wie im folgenden Beispiel dargestellt zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="14e10-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 <span data-ttu-id="14e10-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="14e10-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span></span>  
  
 <span data-ttu-id="14e10-111">Im vorherigen Beispiel filtert die `where`-Klausel alle NULL-Elemente in der Reihenfolge der Kategorien heraus.</span><span class="sxs-lookup"><span data-stu-id="14e10-111">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="14e10-112">Diese Technik ist unabhängig von der NULL-Überprüfung in der join-Klausel.</span><span class="sxs-lookup"><span data-stu-id="14e10-112">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="14e10-113">Der bedingte Ausdruck mit NULL in diesem Beispiel funktioniert, da `Products.CategoryID` vom Typ `int?` ist, was eine Abkürzung für `Nullable<int>` ist.</span><span class="sxs-lookup"><span data-stu-id="14e10-113">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e10-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14e10-114">Example</span></span>

 <span data-ttu-id="14e10-115">Wenn in einer join-Klausel nur einer der Vergleichsschlüssel ein Nullable-Werttyp ist, können Sie den anderen im Abfrageausdruck in einen Nullable-Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="14e10-115">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="14e10-116">Im folgenden Beispiel wird angenommen, dass `EmployeeID` eine Spalte mit Werten vom Typ `int?` ist:</span><span class="sxs-lookup"><span data-stu-id="14e10-116">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 <span data-ttu-id="14e10-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="14e10-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e10-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14e10-118">See also</span></span>  
 <span data-ttu-id="14e10-119"><xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="14e10-119"><xref:System.Nullable%601></span></span>   
 <span data-ttu-id="14e10-120">[LINQ-Abfrageausdrücke](index.md) </span><span class="sxs-lookup"><span data-stu-id="14e10-120">[LINQ query expressions](index.md) </span></span>  
 [<span data-ttu-id="14e10-121">Nullable-Typen</span><span class="sxs-lookup"><span data-stu-id="14e10-121">Nullable types</span></span>](../programming-guide/nullable-types/index.md)

