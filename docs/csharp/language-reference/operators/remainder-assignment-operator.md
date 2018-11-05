---
title: Operator %= (C#-Referenz)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: ab3a6a8d5cbfeb4d527ca1f9c233ddfaba3d35ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188715"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="726c0-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="726c0-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="726c0-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="726c0-103">The remainder assignment operator.</span></span>

<span data-ttu-id="726c0-104">Ein Ausdruck mit dem Operator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="726c0-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="726c0-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="726c0-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="726c0-106">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="726c0-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="726c0-107">Der [Restoperator](remainder-operator.md) `%` berechnet den Rest nach der Division seiner Operanden.</span><span class="sxs-lookup"><span data-stu-id="726c0-107">The [remainder operator](remainder-operator.md) `%` computes the remainder after division of its operands.</span></span> <span data-ttu-id="726c0-108">Er wird von allen numerischen Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="726c0-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="726c0-109">Wenn ein benutzerdefinierter Typ den [Restoperator](remainder-operator.md) `%` [überlädt](../keywords/operator.md), ist der Restzuweisungsoperator `%=` implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="726c0-109">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="726c0-110">Im folgenden Beispiel wird die Verwendung des `%=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="726c0-110">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="726c0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="726c0-111">See also</span></span>

- [<span data-ttu-id="726c0-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="726c0-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="726c0-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="726c0-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="726c0-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="726c0-114">C# Operators</span></span>](index.md)
