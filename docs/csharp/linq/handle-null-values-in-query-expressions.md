---
title: Verarbeiten von NULL-Werten in Abfrageausdrücken (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie NULL-Werte in Abfrageausdrücken in C# verarbeiten.
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: 38a5c5e4a869cc44be78f70cbf0e50166baaab16
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353320"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="dfaa8-103">Behandeln von NULL-Werten in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="dfaa8-103">Handle null values in query expressions</span></span>

<span data-ttu-id="dfaa8-104">Dieses Beispiel zeigt, wie mögliche NULL-Werte in Quellauflistungen behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="dfaa8-105">Eine Objektauflistung wie z.B. <xref:System.Collections.Generic.IEnumerable%601> kann Elemente enthalten, deren Wert [NULL](../language-reference/keywords/null.md) ist.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="dfaa8-106">Wenn eine Quellauflistung NULL ist oder ein Element enthält, dessen Wert NULL ist, und die Abfrage keine NULL-Werte verarbeitet, wird eine <xref:System.NullReferenceException> ausgelöst, wenn Sie die Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="dfaa8-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfaa8-107">Example</span></span>

<span data-ttu-id="dfaa8-108">Sie können defensiv codieren, um eine Nullverweisausnahme wie im folgenden Beispiel dargestellt zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="dfaa8-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

<span data-ttu-id="dfaa8-109">Im vorherigen Beispiel filtert die `where`-Klausel alle NULL-Elemente in der Reihenfolge der Kategorien heraus.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="dfaa8-110">Diese Technik ist unabhängig von der NULL-Überprüfung in der join-Klausel.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="dfaa8-111">Der bedingte Ausdruck mit NULL in diesem Beispiel funktioniert, da `Products.CategoryID` vom Typ `int?` ist, was eine Abkürzung für `Nullable<int>` ist.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>

## <a name="example"></a><span data-ttu-id="dfaa8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfaa8-112">Example</span></span>

<span data-ttu-id="dfaa8-113">Wenn in einer join-Klausel nur einer der Vergleichsschlüssel ein Nullable-Werttyp ist, können Sie den anderen im Abfrageausdruck in einen Nullable-Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="dfaa8-114">Im folgenden Beispiel wird angenommen, dass `EmployeeID` eine Spalte mit Werten vom Typ `int?` ist:</span><span class="sxs-lookup"><span data-stu-id="dfaa8-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="dfaa8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfaa8-115">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="dfaa8-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="dfaa8-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="dfaa8-117">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="dfaa8-117">Nullable value types</span></span>](../programming-guide/nullable-types/index.md)
