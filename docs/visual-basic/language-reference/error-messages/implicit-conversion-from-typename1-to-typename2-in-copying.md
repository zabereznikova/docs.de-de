---
title: "Implizite Konvertierung von &quot;&lt;&quot;Typname1&quot;&gt;&quot;to&quot;&lt;typename2&gt;&quot;in das Zurückkopieren des ByRef-Parameters&quot;&lt;Parametername&gt;&quot;in das entsprechende Argument. | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
dev_langs:
- VB
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0d69bc5074ed5ef2f58010b3477752d3aa6a4b26
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="084be-103">Implizite Konvertierung von '&lt;"Typname1"&gt;'to'&lt;typename2&gt;'in das Zurückkopieren des ByRef-Parameters'&lt;Parametername&gt;"in das entsprechende Argument.</span><span class="sxs-lookup"><span data-stu-id="084be-103">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="084be-104">Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.</span><span class="sxs-lookup"><span data-stu-id="084be-104">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="084be-105">Wenn Sie ein Argument übergeben `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="084be-105">If you pass an argument `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="084be-106">In diesem Fall gibt die Prozedur [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen den Wert der lokalen Variablen in das Argument im aufrufenden Code kopieren.</span><span class="sxs-lookup"><span data-stu-id="084be-106">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="084be-107">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="084be-107">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="084be-108">Wenn die Typen unterschiedlich sind, aber [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen in beide Richtungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="084be-108">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="084be-109">Da Sie verwenden können `CType` oder eines der anderen Konvertierungsschlüsselwörter auf Prozedurarguments oder Parameter, eine solche Konvertierung immer implizit ist.</span><span class="sxs-lookup"><span data-stu-id="084be-109">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="084be-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="084be-110">By default, this message is a warning.</span></span> <span data-ttu-id="084be-111">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="084be-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="084be-112">**Fehler-ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="084be-112">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="084be-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="084be-113">To correct this error</span></span>  
  
-   <span data-ttu-id="084be-114">Verwenden Sie nach Möglichkeit ein aufrufendes Argument vom gleichen Typ wie der Prozedurparameter also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] muss nicht Konvertierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="084be-114">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="084be-115">Wenn Sie die Prozedur mit einem Argument aufrufen müssen anderen vom Parametertyp müssen jedoch nicht in das aufrufende Argument kein Wert zurückgegeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="084be-115">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084be-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="084be-116">See Also</span></span>  
 <span data-ttu-id="084be-117">[Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="084be-117">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="084be-118"> [Prozedurparameter und Argumente](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="084be-118"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="084be-119"> [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="084be-119"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="084be-120"> [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="084be-120"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)</span></span>
