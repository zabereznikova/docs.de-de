---
title: Operator /= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 1d9b918c66ce361067d906a055df5adb25a5a308
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6adf6-102">Operator /= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6adf6-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="6adf6-103">Der Divisionszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="6adf6-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6adf6-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6adf6-104">Remarks</span></span>  
 <span data-ttu-id="6adf6-105">Ein Ausdruck mit dem Zuweisungsoperator `/=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="6adf6-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="6adf6-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="6adf6-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="6adf6-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="6adf6-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6adf6-108">Die [/ operator](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen vordefiniert, um Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6adf6-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="6adf6-109">Der Operator `/=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[/ operator](../../../csharp/language-reference/operators/division-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="6adf6-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6adf6-110">Bei allen Zusammensetzungszuweisungsoperatoren wird die entsprechende Verbundzuweisung durch das Überladen des binären Operators implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="6adf6-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6adf6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6adf6-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6adf6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6adf6-112">See Also</span></span>  
 [<span data-ttu-id="6adf6-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6adf6-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6adf6-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6adf6-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6adf6-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6adf6-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
