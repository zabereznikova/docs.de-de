---
title: '* -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333732"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="35bd6-102">\*-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="35bd6-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="35bd6-103">Der Multiplikationsoperator (`*`) berechnet das Produkt seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="35bd6-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="35bd6-104">Alle numerischen Typen besitzen vordefinierte Multiplikationsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="35bd6-104">All numeric types have predefined multiplication operators.</span></span>

<span data-ttu-id="35bd6-105">`*` dient auch als Dereferenzierungsoperator, der das Lesen und Schreiben in einen Zeiger ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="35bd6-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>

## <a name="remarks"></a><span data-ttu-id="35bd6-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35bd6-106">Remarks</span></span>

<span data-ttu-id="35bd6-107">Der `*`-Operator wird auch verwendet, um Zeigertypen zu deklarieren und Zeiger zu dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="35bd6-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="35bd6-108">Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, gekennzeichnet durch die Verwendung des [unsafe](../keywords/unsafe.md)-Schlüsselworts und erfordert die Compileroption [/unsafe](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="35bd6-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../keywords/unsafe.md) keyword, and requiring the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="35bd6-109">Die englischen Begriffe „dereference operator“ und „indirection operator“ bezeichnen beide den Dereferenzierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="35bd6-109">The dereference operator is also known as the indirection operator.</span></span>

<span data-ttu-id="35bd6-110">Benutzerdefinierte Typen können den binären `*`-Operator überladen (weitere Informationen finden Sie unter [Operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="35bd6-110">User-defined types can overload the binary `*` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="35bd6-111">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="35bd6-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="35bd6-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35bd6-112">Example</span></span>

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a><span data-ttu-id="35bd6-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35bd6-113">Example</span></span>

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a><span data-ttu-id="35bd6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35bd6-114">See also</span></span>

- [<span data-ttu-id="35bd6-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="35bd6-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35bd6-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="35bd6-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="35bd6-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="35bd6-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="35bd6-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="35bd6-118">C# Operators</span></span>](index.md)