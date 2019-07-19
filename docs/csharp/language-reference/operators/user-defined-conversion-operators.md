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
ms.openlocfilehash: 5d1882048b2af12c29a3771055cbeba9565b7dab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67787396"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="be04b-103">Benutzerdefinierte Konvertierungsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="be04b-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="be04b-104">Ein benutzerdefinierter Typ kann eine benutzerdefinierte implizite oder explizite Konvertierung von einem oder in einen anderen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="be04b-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="be04b-105">Zum Aufrufen von impliziten Konvertierungen ist keine spezielle Syntax erforderlich. Implizite Konvertierungen können in verschiedenen Situationen auftreten, beispielswiese in Arbeitsaufträgen und Methodenaufrufen.</span><span class="sxs-lookup"><span data-stu-id="be04b-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="be04b-106">Vordefinierte implizite Konvertierungen in C# werden immer erfolgreich ausgeführt. Bei deren Ausführung wird nie eine Ausnahme ausgelöst, und es gehen nie Informationen verloren.</span><span class="sxs-lookup"><span data-stu-id="be04b-106">Predefined C# implicit conversions always succeed and never throw an exception or lose information.</span></span> <span data-ttu-id="be04b-107">Benutzerdefinierte Konvertierungen sollten sich ebenso verhalten.</span><span class="sxs-lookup"><span data-stu-id="be04b-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="be04b-108">Wenn bei einer benutzerdefinierten Konvertierung eine Ausnahme ausgelöst werden kann oder Informationen verloren gehen können, definieren Sie sie als explizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="be04b-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="be04b-109">Benutzerdefinierte Konvertierungen werden vom [is](type-testing-and-conversion-operators.md#is-operator)- und [as](type-testing-and-conversion-operators.md#as-operator)-Operator nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="be04b-109">User-defined conversions are not considered by the [is](type-testing-and-conversion-operators.md#is-operator) and [as](type-testing-and-conversion-operators.md#as-operator) operators.</span></span> <span data-ttu-id="be04b-110">Verwenden Sie den [cast-Operator ()](type-testing-and-conversion-operators.md#cast-operator-), um eine benutzerdefinierte explizite Konvertierung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="be04b-110">Use the [cast operator ()](type-testing-and-conversion-operators.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="be04b-111">Verwenden Sie zum Definieren einer impliziten bzw. expliziten Konvertierung die Schlüsselwörter `operator` und `implicit` bzw. `explicit`.</span><span class="sxs-lookup"><span data-stu-id="be04b-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="be04b-112">Bei dem Typ, der eine Konvertierung definiert, muss es sich um einen Quelltyp oder um einen Zieltyp dieser Konvertierung handeln.</span><span class="sxs-lookup"><span data-stu-id="be04b-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="be04b-113">Eine Konvertierung zwischen zwei benutzerdefinierten Typen kann in einem der beiden Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="be04b-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="be04b-114">Im folgenden Beispiel wird gezeigt, wie eine implizite und eine explizite Konvertierung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="be04b-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="be04b-115">Sie können auch das Schlüsselwort `operator` verwenden, um einen vordefinierten C#-Operator zu überladen.</span><span class="sxs-lookup"><span data-stu-id="be04b-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="be04b-116">Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="be04b-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="be04b-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="be04b-117">C# language specification</span></span>

<span data-ttu-id="be04b-118">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="be04b-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="be04b-119">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="be04b-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="be04b-120">User-defined conversions (Benutzerdefinierte Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="be04b-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="be04b-121">Implicit conversions (Implizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="be04b-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="be04b-122">Explicit conversions (Explizite Konvertierungen)</span><span class="sxs-lookup"><span data-stu-id="be04b-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="be04b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be04b-123">See also</span></span>

- [<span data-ttu-id="be04b-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="be04b-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="be04b-125">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="be04b-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="be04b-126">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="be04b-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="be04b-127">Typtest- und Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="be04b-127">Type-testing and conversion operators</span></span>](type-testing-and-conversion-operators.md)
- [<span data-ttu-id="be04b-128">Umwandlung und Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="be04b-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="be04b-129">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="be04b-129">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
