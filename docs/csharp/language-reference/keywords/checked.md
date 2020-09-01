---
description: checked-Schlüsselwort – C#-Referenz
title: checked-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 4dd8bc02d3af89d6bab3aef55a88cb8b40704da6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138279"
---
# <a name="checked-c-reference"></a><span data-ttu-id="58ac6-103">checked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="58ac6-103">checked (C# Reference)</span></span>

<span data-ttu-id="58ac6-104">Das Schlüsselwort `checked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen explizit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58ac6-104">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="58ac6-105">Standardmäßig bewirkt ein Ausdruck, der nur konstante Werte enthält, einen Compilerfehler, wenn der Ausdruck einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps liegt.</span><span class="sxs-lookup"><span data-stu-id="58ac6-105">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="58ac6-106">Wenn der Ausdruck einen oder mehrere nicht konstante Werte enthält, erkennt der Compiler den Überlauf nicht.</span><span class="sxs-lookup"><span data-stu-id="58ac6-106">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="58ac6-107">Die Auswertung des Ausdrucks, der im folgenden Beispiel `i2` zugewiesen ist, verursacht keinen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="58ac6-107">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="58ac6-108">Standardmäßig werden diese nicht konstanten Ausdrücke zur Laufzeit auch nicht auf Überläufe überprüft und lösen keine Überlaufausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="58ac6-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="58ac6-109">Das vorherige Beispiel zeigt -2,147,483,639 als Summe von zwei ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="58ac6-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="58ac6-110">Die Überlaufüberprüfung kann durch Compileroptionen, Umgebungskonfiguration oder Verwendung des `checked`-Schlüsselworts aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="58ac6-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="58ac6-111">In den folgenden Beispielen wird veranschaulicht, wie Sie einen `checked`-Ausdruck oder einen `checked`-Block verwenden, um den Überlauf zu erkennen, der von der vorherigen Summe zur Laufzeit erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="58ac6-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="58ac6-112">In beiden Beispielen wird eine Überlaufausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="58ac6-112">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="58ac6-113">Das [unchecked](./unchecked.md)-Schlüsselwort kann verwendet werden, um die Überlaufüberprüfung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="58ac6-113">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="58ac6-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58ac6-114">Example</span></span>

<span data-ttu-id="58ac6-115">Dieses Beispiel zeigt, wie mit `checked` die Überlaufüberprüfung zur Laufzeit aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="58ac6-115">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="58ac6-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="58ac6-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="58ac6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58ac6-117">See also</span></span>

- [<span data-ttu-id="58ac6-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="58ac6-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="58ac6-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="58ac6-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="58ac6-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="58ac6-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="58ac6-121">Checked und Unchecked</span><span class="sxs-lookup"><span data-stu-id="58ac6-121">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="58ac6-122">unchecked</span><span class="sxs-lookup"><span data-stu-id="58ac6-122">unchecked</span></span>](./unchecked.md)
