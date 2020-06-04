---
title: Implizite Konvertierung von "<typename1>" in "<typename2>" beim Zurückkopieren des Wertes des ByRef-Parameters "<parametername>" in das entsprechende Argument.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 4d0f9aac795f683cf58210ea38b3783e451ccfc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402861"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="f51da-102">Implizite Konvertierung von "\<typename1>" in "\<typename2>" beim Zurückkopieren des Wertes des ByRef-Parameters "\<parametername>" in das entsprechende Argument.</span><span class="sxs-lookup"><span data-stu-id="f51da-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>
<span data-ttu-id="f51da-103">Eine Prozedur wird mit einem [ByRef](../modifiers/byref.md) -Argument eines anderen Typs aufgerufen als der des entsprechenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="f51da-103">A procedure is called with a [ByRef](../modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="f51da-104">Wenn Sie ein Argument übergeben `ByRef` , kopiert Visual Basic manchmal den Argument Wert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f51da-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="f51da-105">In diesem Fall muss Visual Basic den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren, wenn die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f51da-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="f51da-106">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f51da-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="f51da-107">Wenn die Typen jedoch unterschiedlich sind, müssen Visual Basic in beide Richtungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f51da-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="f51da-108">Da Sie `CType` oder keines der anderen Konvertierungs Schlüsselwörter für ein Prozedur Argument oder einen Parameter verwenden können, ist eine solche Konvertierung immer implizit.</span><span class="sxs-lookup"><span data-stu-id="f51da-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="f51da-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f51da-109">By default, this message is a warning.</span></span> <span data-ttu-id="f51da-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f51da-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f51da-111">**Fehler-ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="f51da-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f51da-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f51da-112">To correct this error</span></span>  
  
- <span data-ttu-id="f51da-113">Verwenden Sie nach Möglichkeit ein Aufruf Endes Argument desselben Typs wie der Prozedur Parameter, sodass Visual Basic keine Konvertierung durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="f51da-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="f51da-114">Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="f51da-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51da-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f51da-115">See also</span></span>

- [<span data-ttu-id="f51da-116">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f51da-116">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f51da-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f51da-117">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f51da-118">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="f51da-118">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f51da-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f51da-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
