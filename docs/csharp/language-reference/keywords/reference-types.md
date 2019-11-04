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
ms.openlocfilehash: 61b9f8096e1b2093b1ea5589f4336618cd189c34
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422456"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="33da9-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="33da9-102">Reference types (C# Reference)</span></span>

<span data-ttu-id="33da9-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="33da9-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="33da9-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="33da9-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="33da9-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="33da9-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="33da9-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](in-parameter-modifier.md), [ref](ref.md) und [out](out-parameter-modifier.md)-Parametermodifizierer).</span><span class="sxs-lookup"><span data-stu-id="33da9-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="33da9-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="33da9-107">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="33da9-108">class</span><span class="sxs-lookup"><span data-stu-id="33da9-108">class</span></span>](class.md)

- [<span data-ttu-id="33da9-109">interface</span><span class="sxs-lookup"><span data-stu-id="33da9-109">interface</span></span>](interface.md)

- [<span data-ttu-id="33da9-110">delegate</span><span class="sxs-lookup"><span data-stu-id="33da9-110">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="33da9-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="33da9-111">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="33da9-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="33da9-112">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="33da9-113">object</span><span class="sxs-lookup"><span data-stu-id="33da9-113">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="33da9-114">string</span><span class="sxs-lookup"><span data-stu-id="33da9-114">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="33da9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33da9-115">See also</span></span>

- [<span data-ttu-id="33da9-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="33da9-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="33da9-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="33da9-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="33da9-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33da9-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="33da9-119">Typen</span><span class="sxs-lookup"><span data-stu-id="33da9-119">Types</span></span>](/dotnet/csharp/language-reference/keywords)
- [<span data-ttu-id="33da9-120">Werttypen</span><span class="sxs-lookup"><span data-stu-id="33da9-120">Value Types</span></span>](value-types.md)
