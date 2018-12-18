---
title: unchecked-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 44301333f7a36e6b0baa6ea9e089d930bb485a45
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238454"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="80985-102">unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="80985-102">unchecked (C# Reference)</span></span>

<span data-ttu-id="80985-103">Das Schlüsselwort `unchecked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="80985-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="80985-104">Wenn ein Ausdruck in einem ungeprüften Kontext einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps ist, wird der Überlauf nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="80985-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="80985-105">Da z.B. die Berechnung im folgenden Beispiel in einem `unchecked`-Block oder -Ausdruck ausgeführt wird, wird ignoriert, dass das Ergebnis zu groß für eine Ganzzahl ist, und `int1` bekommt den Wert -2.147.483.639 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="80985-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="80985-106">Wenn die `unchecked`-Umgebung entfernt wird, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="80985-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="80985-107">Der Überlauf kann zur Kompilierzeit erkannt werden, da alle Begriffe des Ausdrucks Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="80985-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="80985-108">Ausdrücke, die nicht konstante Begriffe enthalten, sind standardmäßig zur Kompilier- und Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="80985-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="80985-109">Informationen zum Aktivieren einer überprüften Umgebung finden Sie unter [checked](checked.md).</span><span class="sxs-lookup"><span data-stu-id="80985-109">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="80985-110">Da die Überprüfung auf Überlauf Zeit in Anspruch nimmt, kann die Verwendung von einem nicht überprüften Code in Situationen, in denen keine Überlaufgefahr besteht, die Leistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="80985-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="80985-111">Wenn jedoch ein Überlauf möglich ist, sollte eine überprüfte Umgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80985-111">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="80985-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80985-112">Example</span></span>

<span data-ttu-id="80985-113">Im folgenden Beispiel wird die Verwendung des Schlüsselworts `unchecked` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="80985-113">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="80985-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="80985-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="80985-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80985-115">See also</span></span>

- [<span data-ttu-id="80985-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="80985-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="80985-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="80985-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="80985-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="80985-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="80985-119">AKtiviert und nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="80985-119">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="80985-120">checked</span><span class="sxs-lookup"><span data-stu-id="80985-120">checked</span></span>](checked.md)