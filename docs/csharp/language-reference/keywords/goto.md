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
ms.openlocfilehash: e4642d0e43a538217493298b58d572e435db5dae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645326"
---
# <a name="goto-c-reference"></a><span data-ttu-id="66032-102">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="66032-102">goto (C# Reference)</span></span>

<span data-ttu-id="66032-103">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="66032-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="66032-104">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="66032-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="66032-105">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="66032-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="66032-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66032-106">Example</span></span>

<span data-ttu-id="66032-107">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="66032-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="66032-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66032-108">Example</span></span>

<span data-ttu-id="66032-109">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="66032-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="66032-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="66032-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="66032-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66032-111">See also</span></span>

- [<span data-ttu-id="66032-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="66032-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="66032-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="66032-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="66032-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="66032-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="66032-115">goto-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="66032-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
- [<span data-ttu-id="66032-116">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="66032-116">Jump Statements</span></span>](jump-statements.md)
