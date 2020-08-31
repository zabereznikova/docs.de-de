---
description: nameof-Ausdruck – C#-Referenz
title: nameof-Ausdruck – C#-Referenz
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 04109cde2a1f9146bf9bb44f301272808797ded0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118311"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="8db06-103">nameof-Ausdruck (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8db06-103">nameof expression (C# reference)</span></span>

<span data-ttu-id="8db06-104">Ein `nameof`-Ausdruck erzeugt den Namen einer Variablen, eines Typs oder eines Members als Zeichenfolgenkonstante:</span><span class="sxs-lookup"><span data-stu-id="8db06-104">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="8db06-105">Im Falle eines Typs und eines Namespace ist der erzeugte Name in der Regel nicht [vollqualifiziert](~/_csharplang/spec/basic-concepts.md#fully-qualified-names), wie im obigen Beispiel zu sehen.</span><span class="sxs-lookup"><span data-stu-id="8db06-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="8db06-106">Im Fall von [ausführlichen Bezeichnern](../tokens/verbatim.md) ist das `@`-Zeichen nicht der Teil eines Namens, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8db06-106">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="8db06-107">Ein `nameof`-Ausdruck wird zur Kompilierzeit ausgewertet und hat zur Laufzeit keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="8db06-107">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="8db06-108">Sie können einen `nameof`-Ausdruck nutzen, um den Code zur Argumentüberprüfung besser verwalten zu können:</span><span class="sxs-lookup"><span data-stu-id="8db06-108">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="8db06-109">Der `nameof`-Ausdruck ist ab C# 6 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8db06-109">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8db06-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="8db06-110">C# language specification</span></span>

<span data-ttu-id="8db06-111">Weitere Informationen finden Sie im Abschnitt [Nameof-Ausdrücke](~/_csharplang/spec/expressions.md#nameof-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8db06-111">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8db06-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8db06-112">See also</span></span>

- [<span data-ttu-id="8db06-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8db06-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8db06-114">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8db06-114">C# operators and expressions</span></span>](index.md)
