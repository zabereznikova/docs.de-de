---
description: goto-Anweisung – C#-Referenz
title: goto-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128425"
---
# <a name="goto-c-reference"></a><span data-ttu-id="bc77d-103">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bc77d-103">goto (C# Reference)</span></span>

<span data-ttu-id="bc77d-104">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="bc77d-104">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="bc77d-105">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bc77d-105">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="bc77d-106">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="bc77d-106">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="bc77d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc77d-107">Example</span></span>

<span data-ttu-id="bc77d-108">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bc77d-108">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="bc77d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc77d-109">Example</span></span>

<span data-ttu-id="bc77d-110">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bc77d-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="bc77d-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bc77d-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bc77d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc77d-112">See also</span></span>

- [<span data-ttu-id="bc77d-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bc77d-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bc77d-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bc77d-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bc77d-115">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bc77d-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bc77d-116">goto-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="bc77d-116">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
