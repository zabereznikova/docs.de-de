---
title: Implizite Konvertierung von "<typename1>" in "<typename2>" beim Zurückkopieren des Wertes des ByRef-Parameters "<parametername>" in das entsprechende Argument.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 7b02659d96b08c592b25ddf3ef1f99114c3ee269
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831760"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="b0bff-102">Implizite Konvertierung von '\<Typname1 >' zu '\<Typname2 >' beim Zurückkopieren des Wertes des ByRef-Parameters '\<Parametername >' zurück in das entsprechende Argument.</span><span class="sxs-lookup"><span data-stu-id="b0bff-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>
<span data-ttu-id="b0bff-103">Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="b0bff-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="b0bff-104">Wenn Sie ein Argument übergeben `ByRef`, kopiert Visual Basic zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0bff-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="b0bff-105">In diesem Fall müssen Visual Basic klicken Sie dann die Prozedur gibt den Wert den lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.</span><span class="sxs-lookup"><span data-stu-id="b0bff-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="b0bff-106">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0bff-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="b0bff-107">Aber wenn die Typen unterschiedlich sind, müssen in beide Richtungen Visual Basic konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b0bff-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="b0bff-108">Da Sie nicht verwenden können `CType` oder eines anderes Konvertierungsschlüsselwort eines Prozedurarguments oder Parameter, eine solche Konvertierung ist immer implizit.</span><span class="sxs-lookup"><span data-stu-id="b0bff-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="b0bff-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="b0bff-109">By default, this message is a warning.</span></span> <span data-ttu-id="b0bff-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b0bff-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b0bff-111">**Fehler-ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="b0bff-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b0bff-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b0bff-112">To correct this error</span></span>  
  
-   <span data-ttu-id="b0bff-113">Verwenden Sie möglichst ein aufrufendes Argument desselben Typs wie der Prozedurparameter ein, damit Visual Basic nicht Konvertierung vornehmen muss.</span><span class="sxs-lookup"><span data-stu-id="b0bff-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="b0bff-114">Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="b0bff-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0bff-115">See also</span></span>

- [<span data-ttu-id="b0bff-116">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b0bff-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="b0bff-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b0bff-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b0bff-118">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b0bff-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b0bff-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b0bff-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
