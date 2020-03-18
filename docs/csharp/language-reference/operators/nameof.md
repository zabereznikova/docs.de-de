---
title: Operator „nameof“ – C#-Referenz
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846271"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="9f2f4-102">Operator „nameof“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9f2f4-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="9f2f4-103">Der Operator `nameof` ruft den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante ab:</span><span class="sxs-lookup"><span data-stu-id="9f2f4-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="9f2f4-104">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="9f2f4-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="9f2f4-105">Der Operator `nameof` wird zur Kompilierzeit ausgewertet und hat zum Zeitpunkt der Ausführung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9f2f4-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="9f2f4-106">Der Operator `nameof` kann zur besseren Verwaltbarkeit des Argumentüberprüfungscodes beitragen:</span><span class="sxs-lookup"><span data-stu-id="9f2f4-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="9f2f4-107">Der Operator `nameof` ist ab C# 6 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f2f4-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9f2f4-108">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9f2f4-108">C# language specification</span></span>

<span data-ttu-id="9f2f4-109">Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9f2f4-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f2f4-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f2f4-110">See also</span></span>

- [<span data-ttu-id="9f2f4-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9f2f4-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9f2f4-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9f2f4-112">C# operators</span></span>](index.md)
