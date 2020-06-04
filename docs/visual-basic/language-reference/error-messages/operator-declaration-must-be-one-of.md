---
title: 'Die Operator Deklaration muss einer der folgenden sein: +,-, *,-,-, ^, &amp; , like, mod, and, or, Xor, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 3fb2cf392611e5ca83818e3bf173513be031085d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409333"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="20bea-102">Die Operator Deklaration muss eine der folgenden sein: +,-, \*, \, /, ^, &amp; , like, mod, and, or, Xor, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="20bea-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="20bea-103">Sie können nur einen Operator deklarieren, der für das überladen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="20bea-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="20bea-104">In der folgenden Tabelle sind die zu deklarierenden Operatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="20bea-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="20bea-105">type</span><span class="sxs-lookup"><span data-stu-id="20bea-105">Type</span></span>|<span data-ttu-id="20bea-106">Operatoren</span><span class="sxs-lookup"><span data-stu-id="20bea-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="20bea-107">Unäroperatoren</span><span class="sxs-lookup"><span data-stu-id="20bea-107">Unary</span></span>|<span data-ttu-id="20bea-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="20bea-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="20bea-109">Binary</span><span class="sxs-lookup"><span data-stu-id="20bea-109">Binary</span></span>|<span data-ttu-id="20bea-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="20bea-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="20bea-111">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="20bea-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="20bea-112">Beachten Sie, dass der- `=` Operator in der binären Liste der Vergleichs Operator und nicht der Zuweisungs Operator ist.</span><span class="sxs-lookup"><span data-stu-id="20bea-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="20bea-113">**Fehler-ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="20bea-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20bea-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="20bea-114">To correct this error</span></span>  
  
1. <span data-ttu-id="20bea-115">Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.</span><span class="sxs-lookup"><span data-stu-id="20bea-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="20bea-116">Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="20bea-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20bea-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20bea-117">See also</span></span>

- [<span data-ttu-id="20bea-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="20bea-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="20bea-119">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="20bea-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="20bea-120">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="20bea-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="20bea-121">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="20bea-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="20bea-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20bea-122">Function Statement</span></span>](../statements/function-statement.md)
