---
title: Operator „nameof“ – C#-Referenz
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 965b3e96a20906187df4c8693f050c550a747091
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331437"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="2cfb3-102">Operator „nameof“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2cfb3-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="2cfb3-103">Der Operator `nameof` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:</span><span class="sxs-lookup"><span data-stu-id="2cfb3-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="2cfb3-104">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="2cfb3-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="2cfb3-105">Der Operator `nameof` wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="2cfb3-105">The `nameof` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="2cfb3-106">Der Operator `nameof` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:</span><span class="sxs-lookup"><span data-stu-id="2cfb3-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="2cfb3-107">Der Operator `nameof` ist ab C# 6 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cfb3-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2cfb3-108">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2cfb3-108">C# language specification</span></span>

<span data-ttu-id="2cfb3-109">Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2cfb3-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2cfb3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cfb3-110">See also</span></span>

- [<span data-ttu-id="2cfb3-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2cfb3-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2cfb3-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2cfb3-112">C# operators</span></span>](index.md)
