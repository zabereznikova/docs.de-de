---
title: goto-Anweisung (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: d4fd9f1f26b82b409d704c45e4bcf18cceef8282
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507522"
---
# <a name="goto-c-reference"></a><span data-ttu-id="1b4aa-102">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1b4aa-102">goto (C# Reference)</span></span>

<span data-ttu-id="1b4aa-103">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="1b4aa-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="1b4aa-104">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1b4aa-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="1b4aa-105">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="1b4aa-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="1b4aa-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b4aa-106">Example</span></span>

<span data-ttu-id="1b4aa-107">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1b4aa-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="1b4aa-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b4aa-108">Example</span></span>

<span data-ttu-id="1b4aa-109">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1b4aa-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="1b4aa-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1b4aa-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1b4aa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b4aa-111">See also</span></span>

- [<span data-ttu-id="1b4aa-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1b4aa-112">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="1b4aa-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1b4aa-113">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="1b4aa-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1b4aa-114">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="1b4aa-115">goto-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="1b4aa-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)  
- [<span data-ttu-id="1b4aa-116">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="1b4aa-116">Jump Statements</span></span>](jump-statements.md)  
