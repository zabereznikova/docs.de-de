---
title: Zugreifen auf ein Arrayelement mit einem Zeiger – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 4f5d82e0ccdffcb694e3030aabe58b8da687a5e1
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084796"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="88853-102">Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="88853-102">How to access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="88853-103">In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="88853-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="88853-104">Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="88853-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="88853-105">Der Vorgang `p[e]` entspricht `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="88853-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="88853-106">Wie in C und C++ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="88853-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="88853-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88853-107">Example</span></span>

<span data-ttu-id="88853-108">In diesem Beispiel werden einem Zeichenarray, `charPointer`, 123 Speicheradressen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="88853-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="88853-109">Das Array wird verwendet, um die Klein- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)-Schleifen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88853-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="88853-110">Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="88853-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="88853-111">**Großbuchstaben:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Kleinbuchstaben:**
**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="88853-111">**Uppercase letters:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Lowercase letters:**
**abcdefghijklmnopqrstuvwxyz**</span></span>

## <a name="see-also"></a><span data-ttu-id="88853-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88853-112">See also</span></span>

- [<span data-ttu-id="88853-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="88853-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="88853-114">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="88853-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="88853-115">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="88853-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="88853-116">Typen</span><span class="sxs-lookup"><span data-stu-id="88853-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="88853-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="88853-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="88853-118">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="88853-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="88853-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="88853-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
