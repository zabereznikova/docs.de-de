---
title: Operator %= (C#-Referenz)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085639"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e8cba-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e8cba-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="e8cba-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="e8cba-103">The remainder assignment operator.</span></span>

<span data-ttu-id="e8cba-104">Ein Ausdruck mit dem Operator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="e8cba-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="e8cba-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e8cba-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="e8cba-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e8cba-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="e8cba-107">Der [Restoperator](remainder-operator.md) `%` wird von allen numerischen Typen unterstützt und berechnet den Rest nach der Division der Operanden.</span><span class="sxs-lookup"><span data-stu-id="e8cba-107">The [remainder operator](remainder-operator.md) `%` is supported by all numeric types and computes the remainder after division of its operands.</span></span>

<span data-ttu-id="e8cba-108">Wenn ein benutzerdefinierter Typ den [Restoperator](remainder-operator.md) `%` [überlädt](../keywords/operator.md), ist der Restzuweisungsoperator `%=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e8cba-108">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="e8cba-109">Im folgenden Beispiel wird die Verwendung des `%=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e8cba-109">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="e8cba-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8cba-110">See also</span></span>

- [<span data-ttu-id="e8cba-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e8cba-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e8cba-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e8cba-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e8cba-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e8cba-113">C# Operators</span></span>](index.md)
