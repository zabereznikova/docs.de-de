---
title: Benutzerdefinierte Konvertierungsoperatoren – C#-Referenz
description: Hier erfahren Sie, wie Sie benutzerdefinierte implizite und explizite Konvertierungen in C# definieren.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
- explicit
- implicit
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: a0eb11d55ad9e9cccde1704ba4c5ae8acb609989
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916628"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="00d6e-103">Benutzerdefinierte Konvertierungsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="00d6e-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="00d6e-104">Ein benutzerdefinierter Typ kann eine benutzerdefinierte implizite oder explizite Konvertierung von einem oder in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="00d6e-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="00d6e-105">Zum Aufrufen von impliziten Konvertierungen ist keine spezielle Syntax erforderlich. Implizite Konvertierungen können in verschiedenen Situationen auftreten, beispielswiese in Arbeitsaufträgen und Methodenaufrufen.</span><span class="sxs-lookup"><span data-stu-id="00d6e-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="00d6e-106">Vordefinierte implizite C#-Konvertierungen sind immer erfolgreich und lösen keine Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="00d6e-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="00d6e-107">Benutzerdefinierte Konvertierungen sollten sich ebenso verhalten.</span><span class="sxs-lookup"><span data-stu-id="00d6e-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="00d6e-108">Wenn bei einer benutzerdefinierten Konvertierung eine Ausnahme ausgelöst werden kann oder Informationen verloren gehen können, definieren Sie sie als explizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="00d6e-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="00d6e-109">Benutzerdefinierte Konvertierungen werden vom [is](type-testing-and-cast.md#is-operator)- und [as](type-testing-and-cast.md#as-operator)-Operator nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="00d6e-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="00d6e-110">Verwenden Sie einen [Cast-Ausdruck](type-testing-and-cast.md#cast-expression), um eine benutzerdefinierte explizite Konvertierung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="00d6e-110">Use a [cast expression](type-testing-and-cast.md#cast-expression) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="00d6e-111">Verwenden Sie zum Definieren einer impliziten bzw. expliziten Konvertierung die Schlüsselwörter `operator` und `implicit` bzw. `explicit`.</span><span class="sxs-lookup"><span data-stu-id="00d6e-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="00d6e-112">Bei dem Typ, der eine Konvertierung definiert, muss es sich um einen Quelltyp oder um einen Zieltyp dieser Konvertierung handeln.</span><span class="sxs-lookup"><span data-stu-id="00d6e-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="00d6e-113">Eine Konvertierung zwischen zwei benutzerdefinierten Typen kann in einem der beiden Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="00d6e-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="00d6e-114">Im folgenden Beispiel wird gezeigt, wie eine implizite und eine explizite Konvertierung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="00d6e-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](snippets/shared/UserDefinedConversions.cs)]

<span data-ttu-id="00d6e-115">Sie können auch das Schlüsselwort `operator` verwenden, um einen vordefinierten C#-Operator zu überladen.</span><span class="sxs-lookup"><span data-stu-id="00d6e-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="00d6e-116">Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="00d6e-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="00d6e-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="00d6e-117">C# language specification</span></span>

<span data-ttu-id="00d6e-118">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="00d6e-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="00d6e-119">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="00d6e-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="00d6e-120">User-defined conversions (Benutzerdefinierte Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="00d6e-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="00d6e-121">Implicit conversions (Implizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="00d6e-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="00d6e-122">Explicit conversions (Explizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="00d6e-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="00d6e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00d6e-123">See also</span></span>

- [<span data-ttu-id="00d6e-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="00d6e-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="00d6e-125">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="00d6e-125">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="00d6e-126">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="00d6e-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="00d6e-127">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="00d6e-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="00d6e-128">Umwandlung und Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="00d6e-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="00d6e-129">Entwurfsrichtlinien: Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="00d6e-129">Design guidelines - Conversion operators</span></span>](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [<span data-ttu-id="00d6e-130">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="00d6e-130">Chained user-defined explicit conversions in C#</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
