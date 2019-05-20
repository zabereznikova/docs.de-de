---
title: Verweistypen – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 4b3b1d5b27c3f6a88ce752243ab2d1389b168f0e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634063"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="364d5-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="364d5-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="364d5-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="364d5-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="364d5-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="364d5-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="364d5-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="364d5-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="364d5-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](in-parameter-modifier.md), [ref](ref.md) und [out](out-parameter-modifier.md)-Parametermodifizierer).</span><span class="sxs-lookup"><span data-stu-id="364d5-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="364d5-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="364d5-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="364d5-108">class</span><span class="sxs-lookup"><span data-stu-id="364d5-108">class</span></span>](class.md)

- [<span data-ttu-id="364d5-109">interface</span><span class="sxs-lookup"><span data-stu-id="364d5-109">interface</span></span>](interface.md)

- [<span data-ttu-id="364d5-110">delegate</span><span class="sxs-lookup"><span data-stu-id="364d5-110">delegate</span></span>](delegate.md)

 <span data-ttu-id="364d5-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="364d5-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="364d5-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="364d5-112">dynamic</span></span>](dynamic.md)

- [<span data-ttu-id="364d5-113">object</span><span class="sxs-lookup"><span data-stu-id="364d5-113">object</span></span>](object.md)

- [<span data-ttu-id="364d5-114">string</span><span class="sxs-lookup"><span data-stu-id="364d5-114">string</span></span>](string.md)

## <a name="see-also"></a><span data-ttu-id="364d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364d5-115">See also</span></span>

- [<span data-ttu-id="364d5-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="364d5-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="364d5-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="364d5-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="364d5-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="364d5-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="364d5-119">Typen</span><span class="sxs-lookup"><span data-stu-id="364d5-119">Types</span></span>](types.md)
- [<span data-ttu-id="364d5-120">Werttypen</span><span class="sxs-lookup"><span data-stu-id="364d5-120">Value Types</span></span>](value-types.md)
