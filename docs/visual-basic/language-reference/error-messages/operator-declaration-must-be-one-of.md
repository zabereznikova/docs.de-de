---
title: 'Die Operator Deklaration muss einer der folgenden sein: +,-, *,-,-, ^, &amp; , like, mod, and, or, Xor, not,  <<,  >>, =,  <>, <, <=, >, >=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: a94e62e33427987a302a6244b2b8ce8d295e4f11
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159897"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="5e08d-102">BC33000: die Operator Deklaration muss eine der folgenden sein: +,-, \*, \, /, ^, &amp; , like, mod, and, or, Xor, not, \<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="5e08d-102">BC33000: Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="5e08d-103">Sie können nur einen Operator deklarieren, der für das überladen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5e08d-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="5e08d-104">In der folgenden Tabelle sind die zu deklarierenden Operatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5e08d-104">The following table lists the operators you can declare.</span></span>

|<span data-ttu-id="5e08d-105">type</span><span class="sxs-lookup"><span data-stu-id="5e08d-105">Type</span></span>|<span data-ttu-id="5e08d-106">Operatoren</span><span class="sxs-lookup"><span data-stu-id="5e08d-106">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="5e08d-107">Unär</span><span class="sxs-lookup"><span data-stu-id="5e08d-107">Unary</span></span>|<span data-ttu-id="5e08d-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="5e08d-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="5e08d-109">Binary</span><span class="sxs-lookup"><span data-stu-id="5e08d-109">Binary</span></span>|<span data-ttu-id="5e08d-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="5e08d-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="5e08d-111">Konvertierung (unär)</span><span class="sxs-lookup"><span data-stu-id="5e08d-111">Conversion (unary)</span></span>|`CType`|

 <span data-ttu-id="5e08d-112">Beachten Sie, dass der- `=` Operator in der binären Liste der Vergleichs Operator und nicht der Zuweisungs Operator ist.</span><span class="sxs-lookup"><span data-stu-id="5e08d-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="5e08d-113">**Fehler-ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="5e08d-113">**Error ID:** BC33000</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5e08d-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5e08d-114">To correct this error</span></span>

- <span data-ttu-id="5e08d-115">Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.</span><span class="sxs-lookup"><span data-stu-id="5e08d-115">Select an operator from the set of overloadable operators.</span></span>

- <span data-ttu-id="5e08d-116">Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e08d-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e08d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e08d-117">See also</span></span>

- [<span data-ttu-id="5e08d-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="5e08d-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="5e08d-119">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="5e08d-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="5e08d-120">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="5e08d-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="5e08d-121">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="5e08d-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="5e08d-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5e08d-122">Function Statement</span></span>](../statements/function-statement.md)
