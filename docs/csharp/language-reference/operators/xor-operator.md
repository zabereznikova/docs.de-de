---
title: Operator ^ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 5cc3cd2cfc932646e5b2dd6ec034555b07582379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d5dc2-102">Operator ^ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d5dc2-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="d5dc2-103">Binäre `^`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="d5dc2-104">Für integrale Typen berechnet `^` die bitweise XOR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="d5dc2-105">Für `bool`-Operanden berechnet `^` den XOR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn einer und nur einer der Operanden `true` ist.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5dc2-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5dc2-106">Remarks</span></span>  
 <span data-ttu-id="d5dc2-107">Benutzerdefinierte Typen können den Operator `^` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="d5dc2-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="d5dc2-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5dc2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5dc2-109">Example</span></span>  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 <span data-ttu-id="d5dc2-110">Die Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel führt einen bitweisen XOR-Operator der folgenden beiden binären Werte aus, die den Hexadezimalwerten F8 und 3F entsprechen:</span><span class="sxs-lookup"><span data-stu-id="d5dc2-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="d5dc2-111">Das Ergebnis von XOR ist `1100 0111`, was hexadezimal C7 ist.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5dc2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5dc2-112">See Also</span></span>  
 [<span data-ttu-id="d5dc2-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d5dc2-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d5dc2-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d5dc2-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d5dc2-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d5dc2-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
