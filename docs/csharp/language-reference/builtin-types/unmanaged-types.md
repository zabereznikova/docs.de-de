---
description: Informationen zu nicht verwalteten Typen in C#
title: 'Nicht verwaltete Typen: C#-Verweis'
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 4374872af13c94e1a1af6b9f2c431f076c6f7dff
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471798"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="56dab-103">Nicht verwaltete Typen (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="56dab-103">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="56dab-104">Ein Typ ist ein **nicht verwalteter Typ** , wenn es sich um einen der folgenden Typen handelt:</span><span class="sxs-lookup"><span data-stu-id="56dab-104">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="56dab-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` oder `bool`</span><span class="sxs-lookup"><span data-stu-id="56dab-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="56dab-106">Beliebiger [Enumerationstyp](enum.md)</span><span class="sxs-lookup"><span data-stu-id="56dab-106">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="56dab-107">Beliebiger [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="56dab-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="56dab-108">Jeder benutzerdefinierte [Strukturtyp](struct.md), der nur Felder mit nicht verwalteten Typen enthält und – in C# 7.3 und früher – kein konstruierter Typ ist (ein konstruierter Typ ist ein Typ, der mindestens ein Typargument enthält)</span><span class="sxs-lookup"><span data-stu-id="56dab-108">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="56dab-109">Ab C# 7.3 können Sie die [`unmanaged`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) verwenden, um anzugeben, dass ein Typparameter ein nicht verwalteter Nicht-Nullable-Nichtzeigertyp ist.</span><span class="sxs-lookup"><span data-stu-id="56dab-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="56dab-110">Ab C# 8.0 ist ein *konstruierter* Strukturtyp, der Felder mit nicht verwalteten Typen enthält, ebenfalls nicht verwaltet, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="56dab-110">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/shared/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="56dab-111">Eine generische Struktur kann als Quelle sowohl für nicht verwaltete als auch für verwaltete konstruierte Typen dienen.</span><span class="sxs-lookup"><span data-stu-id="56dab-111">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="56dab-112">Das oben stehende Beispiel definiert die generische Struktur `Coords<T>` und zeigt Beispiele nicht verwalteter konstruierter Typen.</span><span class="sxs-lookup"><span data-stu-id="56dab-112">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="56dab-113">Ein Beispiel für einen verwalteten Typ ist `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="56dab-113">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="56dab-114">Der Typ ist verwaltet, weil er Felder des Typs `object` enthält, der verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="56dab-114">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="56dab-115">Wenn *alle* konstruierten Typen nicht verwaltet sein sollen, verwenden Sie die `unmanaged`-Einschränkung in der Definition einer generischen Struktur:</span><span class="sxs-lookup"><span data-stu-id="56dab-115">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/shared/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="56dab-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="56dab-116">C# language specification</span></span>

<span data-ttu-id="56dab-117">Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="56dab-117">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56dab-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56dab-118">See also</span></span>

- [<span data-ttu-id="56dab-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="56dab-119">C# reference</span></span>](../index.md)
- [<span data-ttu-id="56dab-120">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="56dab-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="56dab-121">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="56dab-121">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="56dab-122">sizeof (Operator)</span><span class="sxs-lookup"><span data-stu-id="56dab-122">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="56dab-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="56dab-123">stackalloc</span></span>](../operators/stackalloc.md)
