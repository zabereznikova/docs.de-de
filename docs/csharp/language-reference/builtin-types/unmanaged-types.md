---
title: 'Nicht verwaltete Typen: C#-Verweis'
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512073"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="da377-102">Nicht verwaltete Typen (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="da377-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="da377-103">Bei einem **nicht verwalteten Typ** handelt es sich um einen Typ, der kein Verweistyp oder konstruierter Typ ist (ein Typ, der mindestens ein Typargument enthält) und auf einer Schachtelungsebene keinen Verweistyp- oder konstruierte Typfelder aufweist.</span><span class="sxs-lookup"><span data-stu-id="da377-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="da377-104">Anders ausgedrückt bedeutet dies, dass es sich bei einem nicht verwalteten Typ um die Folgenden handelt:</span><span class="sxs-lookup"><span data-stu-id="da377-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="da377-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` oder `bool`</span><span class="sxs-lookup"><span data-stu-id="da377-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="da377-106">Beliebiger [Enumerationstyp](../keywords/enum.md)</span><span class="sxs-lookup"><span data-stu-id="da377-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="da377-107">Beliebiger [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="da377-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="da377-108">Beliebiger benutzerdefinierter [Strukturtyp](../keywords/struct.md), der kein konstruierter Typ ist und nur Felder von nicht verwalteten Typen enthält</span><span class="sxs-lookup"><span data-stu-id="da377-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="da377-109">Ab C# 7.3 können Sie die [`unmanaged`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) verwenden, um anzugeben, dass ein Typparameter ein nicht verwalteter Nichtzeigertyp ist.</span><span class="sxs-lookup"><span data-stu-id="da377-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="da377-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="da377-110">C# language specification</span></span>

<span data-ttu-id="da377-111">Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="da377-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da377-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da377-112">See also</span></span>

- [<span data-ttu-id="da377-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="da377-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="da377-114">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="da377-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="da377-115">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="da377-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="da377-116">sizeof (Operator)</span><span class="sxs-lookup"><span data-stu-id="da377-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="da377-117">stackalloc (Operator)</span><span class="sxs-lookup"><span data-stu-id="da377-117">stackalloc operator</span></span>](../operators/stackalloc.md)
