---
title: goto-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 675893f02a0022b403d2afc018d24d6f826b8f75
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421802"
---
# <a name="goto-c-reference"></a><span data-ttu-id="58062-102">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="58062-102">goto (C# Reference)</span></span>

<span data-ttu-id="58062-103">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="58062-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="58062-104">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="58062-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="58062-105">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="58062-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="58062-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58062-106">Example</span></span>

<span data-ttu-id="58062-107">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58062-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="58062-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58062-108">Example</span></span>

<span data-ttu-id="58062-109">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58062-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="58062-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="58062-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="58062-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58062-111">See also</span></span>

- [<span data-ttu-id="58062-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="58062-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="58062-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="58062-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="58062-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="58062-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="58062-115">goto-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="58062-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
