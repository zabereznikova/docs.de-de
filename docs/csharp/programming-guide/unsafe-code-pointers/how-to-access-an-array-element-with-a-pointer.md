---
title: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 0e76ebddd8b703e8d0de4aa6825cbd6d0221079b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861649"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="4d8c9-102">Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4d8c9-102">How to access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="4d8c9-103">In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d8c9-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="4d8c9-104">Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="4d8c9-105">Der Vorgang p[e] entspricht \*(p+e).</span><span class="sxs-lookup"><span data-stu-id="4d8c9-105">The operation p[e] is equivalent to \*(p+e).</span></span> <span data-ttu-id="4d8c9-106">Wie in C und C++ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="4d8c9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d8c9-107">Example</span></span>

<span data-ttu-id="4d8c9-108">In diesem Beispiel werden einem Zeichenarray, `charPointer`, 123 Speicheradressen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="4d8c9-109">Das Array wird verwendet, um die Klein- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)-Schleifen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="4d8c9-110">Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d8c9-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="4d8c9-111">**Großbuchstaben:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Kleinbuchstaben:**
**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="4d8c9-111">**Uppercase letters:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Lowercase letters:**
**abcdefghijklmnopqrstuvwxyz**</span></span>

## <a name="see-also"></a><span data-ttu-id="4d8c9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d8c9-112">See also</span></span>

- [<span data-ttu-id="4d8c9-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4d8c9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4d8c9-114">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="4d8c9-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="4d8c9-115">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="4d8c9-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="4d8c9-116">Typen</span><span class="sxs-lookup"><span data-stu-id="4d8c9-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="4d8c9-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="4d8c9-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="4d8c9-118">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d8c9-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="4d8c9-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4d8c9-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
