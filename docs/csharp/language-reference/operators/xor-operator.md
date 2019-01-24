---
title: ^-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333706"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7b625-102">^-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7b625-102">^ operator (C# Reference)</span></span>

<span data-ttu-id="7b625-103">Binäre `^`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="7b625-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="7b625-104">Für integrale Typen berechnet `^` die bitweise XOR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="7b625-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="7b625-105">Für `bool`-Operanden berechnet `^` den XOR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn einer und nur einer der Operanden `true` ist.</span><span class="sxs-lookup"><span data-stu-id="7b625-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b625-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b625-106">Remarks</span></span>

<span data-ttu-id="7b625-107">Benutzerdefinierte Typen können den Operator `^` überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7b625-107">User-defined types can overload the `^` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="7b625-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="7b625-108">Operations on integral types are generally allowed on enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="7b625-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b625-109">Example</span></span>

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

<span data-ttu-id="7b625-110">Die Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel führt einen bitweisen XOR-Operator der folgenden beiden binären Werte aus, die den Hexadezimalwerten F8 und 3F entsprechen:</span><span class="sxs-lookup"><span data-stu-id="7b625-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>

`1111 1000`

`0011 1111`

<span data-ttu-id="7b625-111">Das Ergebnis von XOR ist `1100 0111`, was hexadezimal C7 ist.</span><span class="sxs-lookup"><span data-stu-id="7b625-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b625-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b625-112">See Also</span></span>

- [<span data-ttu-id="7b625-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7b625-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7b625-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7b625-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7b625-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7b625-115">C# operators</span></span>](index.md)
