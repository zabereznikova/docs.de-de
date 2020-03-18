---
title: Verweistypen – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: b2d6cc94c11ca6305a75e9ee489af53ad957201e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744520"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="c6d6f-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c6d6f-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="c6d6f-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="c6d6f-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="c6d6f-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="c6d6f-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="c6d6f-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c6d6f-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="c6d6f-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](in-parameter-modifier.md), [ref](ref.md) und [out](out-parameter-modifier.md)-Parametermodifizierer).</span><span class="sxs-lookup"><span data-stu-id="c6d6f-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="c6d6f-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="c6d6f-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="c6d6f-108">class</span><span class="sxs-lookup"><span data-stu-id="c6d6f-108">class</span></span>](class.md)

- [<span data-ttu-id="c6d6f-109">interface</span><span class="sxs-lookup"><span data-stu-id="c6d6f-109">interface</span></span>](interface.md)

- [<span data-ttu-id="c6d6f-110">delegate</span><span class="sxs-lookup"><span data-stu-id="c6d6f-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="c6d6f-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="c6d6f-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="c6d6f-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="c6d6f-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="c6d6f-113">object</span><span class="sxs-lookup"><span data-stu-id="c6d6f-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="c6d6f-114">string</span><span class="sxs-lookup"><span data-stu-id="c6d6f-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="c6d6f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6d6f-115">See also</span></span>

- [<span data-ttu-id="c6d6f-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c6d6f-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c6d6f-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c6d6f-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c6d6f-118">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="c6d6f-118">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="c6d6f-119">Value types (Werttypen)</span><span class="sxs-lookup"><span data-stu-id="c6d6f-119">Value types</span></span>](../builtin-types/value-types.md)
