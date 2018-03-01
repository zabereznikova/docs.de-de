---
title: "Implizite Konvertierung von &#39; &lt;Typname1&gt;&#39; in &#39;&lt; Typname2&gt;&#39; kopieren Sie den Wert des &#39; ByRef &#39; Parameter &#39; &lt;Parametername&gt;&#39; zurück in das entsprechende Argument."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="7853a-102">Implizite Konvertierung von &#39; &lt;Typname1&gt;&#39; in &#39;&lt; Typname2&gt;&#39; kopieren Sie den Wert des &#39; ByRef &#39; Parameter &#39; &lt;Parametername&gt;&#39; zurück in das entsprechende Argument.</span><span class="sxs-lookup"><span data-stu-id="7853a-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="7853a-103">Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="7853a-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="7853a-104">Wenn Sie ein Argument übergeben `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7853a-104">If you pass an argument `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="7853a-105">In diesem Fall muss [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nach Abschluss der Prozedur den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.</span><span class="sxs-lookup"><span data-stu-id="7853a-105">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="7853a-106">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7853a-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="7853a-107">Wenn hingegen die Typen unterschiedlich sind, muss [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die Konvertierung in beide Richtungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="7853a-107">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="7853a-108">Da Sie nicht über `CType` oder eines anderes Konvertierungsschlüsselwort eines Prozedurarguments oder Parameter, eine solche Konvertierung ist immer implizit.</span><span class="sxs-lookup"><span data-stu-id="7853a-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="7853a-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="7853a-109">By default, this message is a warning.</span></span> <span data-ttu-id="7853a-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7853a-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7853a-111">**Fehler-ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="7853a-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7853a-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7853a-112">To correct this error</span></span>  
  
-   <span data-ttu-id="7853a-113">Verwenden Sie nach Möglichkeit ein aufrufendes Argument, das denselben Typ aufweist wie der Prozedurparameter, sodass [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keine Konvertierung ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="7853a-113">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="7853a-114">Wenn Sie die Prozedur mit einem Argument aufrufen müssen, Typ sich vom Parametertyp unterscheidet, jedoch müssen nicht in das aufrufende Argument einen Wert zurückgeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="7853a-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7853a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7853a-115">See Also</span></span>  
 [<span data-ttu-id="7853a-116">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7853a-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="7853a-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7853a-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7853a-118">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="7853a-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="7853a-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="7853a-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
