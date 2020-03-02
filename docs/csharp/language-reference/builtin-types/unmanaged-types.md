---
title: 'Nicht verwaltete Typen: C#-Verweis'
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 042cf382879cc4010a388fb75f41099b4342c9d9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626944"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="ce145-102">Nicht verwaltete Typen (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="ce145-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="ce145-103">Ein Typ ist ein **nicht verwalteter Typ**, wenn es sich um einen der folgenden Typen handelt:</span><span class="sxs-lookup"><span data-stu-id="ce145-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="ce145-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` oder `bool`</span><span class="sxs-lookup"><span data-stu-id="ce145-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="ce145-105">Beliebiger [Enumerationstyp](enum.md)</span><span class="sxs-lookup"><span data-stu-id="ce145-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="ce145-106">Beliebiger [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md)</span><span class="sxs-lookup"><span data-stu-id="ce145-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="ce145-107">Jeder benutzerdefinierte [Strukturtyp](struct.md), der nur Felder mit nicht verwalteten Typen enthält und – in C# 7.3 und früher – kein konstruierter Typ ist (ein konstruierter Typ ist ein Typ, der mindestens ein Typargument enthält)</span><span class="sxs-lookup"><span data-stu-id="ce145-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="ce145-108">Ab C# 7.3 können Sie die [`unmanaged`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) verwenden, um anzugeben, dass ein Typparameter ein nicht verwalteter Nicht-Nullable-Nichtzeigertyp ist.</span><span class="sxs-lookup"><span data-stu-id="ce145-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="ce145-109">Ab C# 8.0 ist ein *konstruierter* Strukturtyp, der Felder mit nicht verwalteten Typen enthält, ebenfalls nicht verwaltet, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="ce145-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="ce145-110">Eine generische Struktur kann als Quelle sowohl für nicht verwaltete als auch für verwaltete konstruierte Typen dienen.</span><span class="sxs-lookup"><span data-stu-id="ce145-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="ce145-111">Das oben stehende Beispiel definiert die generische Struktur `Coords<T>` und zeigt Beispiele nicht verwalteter konstruierter Typen.</span><span class="sxs-lookup"><span data-stu-id="ce145-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="ce145-112">Ein Beispiel für einen verwalteten Typ ist `Coords<object>`.</span><span class="sxs-lookup"><span data-stu-id="ce145-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="ce145-113">Der Typ ist verwaltet, weil er Felder des Typs `object` enthält, der verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="ce145-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="ce145-114">Wenn *alle* konstruierten Typen nicht verwaltet sein sollen, verwenden Sie die `unmanaged`-Einschränkung in der Definition einer generischen Struktur:</span><span class="sxs-lookup"><span data-stu-id="ce145-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="ce145-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ce145-115">C# language specification</span></span>

<span data-ttu-id="ce145-116">Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ce145-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce145-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce145-117">See also</span></span>

- [<span data-ttu-id="ce145-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ce145-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ce145-119">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="ce145-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="ce145-120">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="ce145-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="ce145-121">sizeof (Operator)</span><span class="sxs-lookup"><span data-stu-id="ce145-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="ce145-122">stackalloc (Operator)</span><span class="sxs-lookup"><span data-stu-id="ce145-122">stackalloc operator</span></span>](../operators/stackalloc.md)
