---
title: nameof-Ausdruck – C#-Referenz
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: d71acf0cf7d5cdcfa5310455af2120fa1f82d567
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135918"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="c07a6-102">nameof-Ausdruck (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c07a6-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="c07a6-103">Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:</span><span class="sxs-lookup"><span data-stu-id="c07a6-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="c07a6-104">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c07a6-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="c07a6-105">Im Fall von [ausführlichen Bezeichnern](../tokens/verbatim.md) ist das `@`-Zeichen nicht der Teil eines Namens, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c07a6-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="c07a6-106">Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="c07a6-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="c07a6-107">Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:</span><span class="sxs-lookup"><span data-stu-id="c07a6-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="c07a6-108">Der `nameof`-Ausdruck ist ab C# 6 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c07a6-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c07a6-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c07a6-109">C# language specification</span></span>

<span data-ttu-id="c07a6-110">Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c07a6-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c07a6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c07a6-111">See also</span></span>

- [<span data-ttu-id="c07a6-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c07a6-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c07a6-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c07a6-113">C# operators</span></span>](index.md)
