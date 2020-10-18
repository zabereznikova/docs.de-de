---
title: Das Zurückkopieren des ByRef-Parameters "<parametername>" in das entsprechende Argument führt zu einer Einschränkung von Typ "<typename1>" auf Typ "<typename2>".
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: b9a38d3eb4e25d5c9ac765adf47df72e45fd082a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160931"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="6dcff-102">BC32053: der Wert des ByRef-Parameters " \<parametername> " wird auf das entsprechende Argument zurückkopiert. der Typ "" wird \<typename1> auf den Typ " \<typename2> " eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="6dcff-102">BC32053: Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>

<span data-ttu-id="6dcff-103">Eine Prozedur wird mit einem Argument aufgerufen, das zum entsprechenden Parametertyp erweitert wird, und die Konvertierung des-Parameters in das-Argument wird einschränkend.</span><span class="sxs-lookup"><span data-stu-id="6dcff-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>

 <span data-ttu-id="6dcff-104">Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="6dcff-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="6dcff-105">Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6dcff-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="6dcff-106">Wenn Sie den Klassen-oder Strukturtyp in einem Prozedur aufrufstyp verwenden, können Visual Basic Diese Konvertierungs Operatoren verwenden, um den Typ eines Arguments in den Typ des entsprechenden Parameters zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6dcff-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>

 <span data-ttu-id="6dcff-107">Wenn Sie das [ByRef](../modifiers/byref.md)-Argument übergeben, kopiert Visual Basic manchmal den Argument Wert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="6dcff-107">If you pass the argument [ByRef](../modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="6dcff-108">In diesem Fall muss Visual Basic den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren, wenn die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6dcff-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>

 <span data-ttu-id="6dcff-109">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6dcff-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="6dcff-110">Wenn die Typen jedoch unterschiedlich sind, müssen Visual Basic in beide Richtungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6dcff-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="6dcff-111">Wenn einer der Typen Ihr Klassen-oder Strukturtyp ist, muss Visual Basic ihn sowohl in den als auch aus dem anderen Typ konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6dcff-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="6dcff-112">Wenn eine dieser Konvertierungen erweitert wird, kann die umgekehrte Konvertierung einschränkend sein.</span><span class="sxs-lookup"><span data-stu-id="6dcff-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>

 <span data-ttu-id="6dcff-113">**Fehler-ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="6dcff-113">**Error ID:** BC32053</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6dcff-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6dcff-114">To correct this error</span></span>

- <span data-ttu-id="6dcff-115">Verwenden Sie nach Möglichkeit ein Aufruf Endes Argument desselben Typs wie der Prozedur Parameter, sodass Visual Basic keine Konvertierung durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="6dcff-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>

- <span data-ttu-id="6dcff-116">Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="6dcff-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>

- <span data-ttu-id="6dcff-117">Wenn ein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Operator für die umgekehrte Konvertierung als [Erweiterung](../modifiers/widening.md), wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="6dcff-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../modifiers/widening.md), if possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dcff-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dcff-118">See also</span></span>

- [<span data-ttu-id="6dcff-119">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6dcff-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="6dcff-120">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6dcff-120">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6dcff-121">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="6dcff-121">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="6dcff-122">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="6dcff-122">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="6dcff-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6dcff-123">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="6dcff-124">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="6dcff-124">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="6dcff-125">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="6dcff-125">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="6dcff-126">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6dcff-126">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="6dcff-127">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="6dcff-127">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
