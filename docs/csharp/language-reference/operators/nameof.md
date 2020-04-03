---
title: nameof-Ausdruck – C#-Referenz
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507138"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="9a4ba-102">nameof-Ausdruck (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9a4ba-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="9a4ba-103">Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:</span><span class="sxs-lookup"><span data-stu-id="9a4ba-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="9a4ba-104">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="9a4ba-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="9a4ba-105">Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="9a4ba-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="9a4ba-106">Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:</span><span class="sxs-lookup"><span data-stu-id="9a4ba-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="9a4ba-107">Der `nameof`-Ausdruck ist ab C# 6 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9a4ba-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9a4ba-108">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9a4ba-108">C# language specification</span></span>

<span data-ttu-id="9a4ba-109">Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9a4ba-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a4ba-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a4ba-110">See also</span></span>

- [<span data-ttu-id="9a4ba-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9a4ba-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9a4ba-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9a4ba-112">C# operators</span></span>](index.md)
