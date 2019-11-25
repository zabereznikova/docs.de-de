---
title: Benutzerdefinierte Konvertierungsoperatoren – C#-Referenz
description: Hier erfahren Sie, wie Sie benutzerdefinierte implizite und explizite Konvertierungen in C# definieren.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: 25f042dec5fd5594b7e166cc064394e90db01c27
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036119"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="74a71-103">Benutzerdefinierte Konvertierungsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="74a71-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="74a71-104">Ein benutzerdefinierter Typ kann eine benutzerdefinierte implizite oder explizite Konvertierung von einem oder in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="74a71-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="74a71-105">Zum Aufrufen von impliziten Konvertierungen ist keine spezielle Syntax erforderlich. Implizite Konvertierungen können in verschiedenen Situationen auftreten, beispielswiese in Arbeitsaufträgen und Methodenaufrufen.</span><span class="sxs-lookup"><span data-stu-id="74a71-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="74a71-106">Vordefinierte implizite C#-Konvertierungen sind immer erfolgreich und lösen keine Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="74a71-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="74a71-107">Benutzerdefinierte Konvertierungen sollten sich ebenso verhalten.</span><span class="sxs-lookup"><span data-stu-id="74a71-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="74a71-108">Wenn bei einer benutzerdefinierten Konvertierung eine Ausnahme ausgelöst werden kann oder Informationen verloren gehen können, definieren Sie sie als explizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="74a71-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="74a71-109">Benutzerdefinierte Konvertierungen werden vom [is](type-testing-and-cast.md#is-operator)- und [as](type-testing-and-cast.md#as-operator)-Operator nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="74a71-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="74a71-110">Verwenden Sie den [cast-Operator ()](type-testing-and-cast.md#cast-operator-), um eine benutzerdefinierte explizite Konvertierung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="74a71-110">Use the [cast operator ()](type-testing-and-cast.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="74a71-111">Verwenden Sie zum Definieren einer impliziten bzw. expliziten Konvertierung die Schlüsselwörter `operator` und `implicit` bzw. `explicit`.</span><span class="sxs-lookup"><span data-stu-id="74a71-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="74a71-112">Bei dem Typ, der eine Konvertierung definiert, muss es sich um einen Quelltyp oder um einen Zieltyp dieser Konvertierung handeln.</span><span class="sxs-lookup"><span data-stu-id="74a71-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="74a71-113">Eine Konvertierung zwischen zwei benutzerdefinierten Typen kann in einem der beiden Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="74a71-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="74a71-114">Im folgenden Beispiel wird gezeigt, wie eine implizite und eine explizite Konvertierung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="74a71-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="74a71-115">Sie können auch das Schlüsselwort `operator` verwenden, um einen vordefinierten C#-Operator zu überladen.</span><span class="sxs-lookup"><span data-stu-id="74a71-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="74a71-116">Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="74a71-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="74a71-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="74a71-117">C# language specification</span></span>

<span data-ttu-id="74a71-118">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="74a71-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="74a71-119">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="74a71-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="74a71-120">User-defined conversions (Benutzerdefinierte Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="74a71-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="74a71-121">Implicit conversions (Implizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="74a71-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="74a71-122">Explicit conversions (Explizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="74a71-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="74a71-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a71-123">See also</span></span>

- [<span data-ttu-id="74a71-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="74a71-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="74a71-125">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="74a71-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="74a71-126">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="74a71-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="74a71-127">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="74a71-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="74a71-128">Umwandlung und Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="74a71-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="74a71-129">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="74a71-129">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
