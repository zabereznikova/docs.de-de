---
description: Verweistypen – C#-Referenz
title: Verweistypen – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 075ec5ecd8f71f5cb85bab0e2baff56409709191
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899612"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="cf450-103">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cf450-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="cf450-104">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="cf450-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="cf450-105">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf450-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="cf450-106">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cf450-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="cf450-107">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](in-parameter-modifier.md), [ref](ref.md) und [out](out-parameter-modifier.md)-Parametermodifizierer).</span><span class="sxs-lookup"><span data-stu-id="cf450-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="cf450-108">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="cf450-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="cf450-109">class</span><span class="sxs-lookup"><span data-stu-id="cf450-109">class</span></span>](class.md)

- [<span data-ttu-id="cf450-110">interface</span><span class="sxs-lookup"><span data-stu-id="cf450-110">interface</span></span>](interface.md)

- [<span data-ttu-id="cf450-111">delegate</span><span class="sxs-lookup"><span data-stu-id="cf450-111">delegate</span></span>](../builtin-types/reference-types.md)
- [<span data-ttu-id="cf450-112">record</span><span class="sxs-lookup"><span data-stu-id="cf450-112">record</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="cf450-113">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="cf450-113">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="cf450-114">dynamic</span><span class="sxs-lookup"><span data-stu-id="cf450-114">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="cf450-115">object</span><span class="sxs-lookup"><span data-stu-id="cf450-115">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="cf450-116">string</span><span class="sxs-lookup"><span data-stu-id="cf450-116">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="cf450-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf450-117">See also</span></span>

- [<span data-ttu-id="cf450-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cf450-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cf450-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cf450-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cf450-120">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="cf450-120">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="cf450-121">Werttypen</span><span class="sxs-lookup"><span data-stu-id="cf450-121">Value types</span></span>](../builtin-types/value-types.md)
