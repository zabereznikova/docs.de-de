---
title: Operator ^ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: b1333f9d06e2804029550e6364a225558e096431
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925297"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5d6b0-102">Operator ^ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5d6b0-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="5d6b0-103">Binäre `^`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="5d6b0-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="5d6b0-104">Für integrale Typen berechnet `^` die bitweise XOR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="5d6b0-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="5d6b0-105">Für `bool`-Operanden berechnet `^` den XOR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn einer und nur einer der Operanden `true` ist.</span><span class="sxs-lookup"><span data-stu-id="5d6b0-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d6b0-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d6b0-106">Remarks</span></span>  
 <span data-ttu-id="5d6b0-107">Benutzerdefinierte Typen können den Operator `^` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5d6b0-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="5d6b0-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="5d6b0-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d6b0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d6b0-109">Example</span></span>  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 <span data-ttu-id="5d6b0-110">Die Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel führt einen bitweisen XOR-Operator der folgenden beiden binären Werte aus, die den Hexadezimalwerten F8 und 3F entsprechen:</span><span class="sxs-lookup"><span data-stu-id="5d6b0-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="5d6b0-111">Das Ergebnis von XOR ist `1100 0111`, was hexadezimal C7 ist.</span><span class="sxs-lookup"><span data-stu-id="5d6b0-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6b0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d6b0-112">See Also</span></span>

- [<span data-ttu-id="5d6b0-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5d6b0-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5d6b0-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5d6b0-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5d6b0-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d6b0-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
