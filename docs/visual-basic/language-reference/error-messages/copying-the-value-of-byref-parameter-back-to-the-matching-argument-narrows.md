---
title: "Kopieren des Wertes des ByRef-Parameters &quot;&lt;Parametername&gt;&quot;wieder in das entsprechende Argument führt zu einer Einschränkung vom Typ&quot;&lt;&quot;Typname1&quot;&gt;&quot; in Typ&quot;&lt;typename2&gt;&quot; | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
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
ms.openlocfilehash: 10ad4af689c11f3e4defe43c4fed9ed579ba5305
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="0959d-102">Kopieren des Wertes des ByRef-Parameters '&lt;Parametername&gt;'wieder in das entsprechende Argument führt zu einer Einschränkung vom Typ'&lt;"Typname1"&gt;' in Typ'&lt;typename2&gt;'</span><span class="sxs-lookup"><span data-stu-id="0959d-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="0959d-103">Eine Prozedur wird mit einem Argument, das in den entsprechenden Parametertyp erweitert wird aufgerufen, und die Konvertierung vom Parameter in das Argument führt zu einer Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="0959d-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="0959d-104">Wenn Sie eine Klasse oder Struktur definieren, können Sie einen oder mehrere Konvertierungsoperatoren zum Konvertieren dieses Klassen- oder Strukturtyps in andere Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="0959d-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="0959d-105">Sie können auch Operatoren für die umgekehrte Konvertierung definieren, um dieser anderen Typen zurück in den Klassen- oder Strukturtyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0959d-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="0959d-106">Wenn Sie die Klasse oder Struktur in einem Prozeduraufruf verwenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können mithilfe dieser Konvertierungsoperatoren den Typ eines Arguments in den Typ des entsprechenden Parameters konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0959d-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="0959d-107">Wenn Sie das Argument übergeben [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0959d-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="0959d-108">In diesem Fall gibt die Prozedur [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen den Wert der lokalen Variablen in das Argument im aufrufenden Code kopieren.</span><span class="sxs-lookup"><span data-stu-id="0959d-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="0959d-109">Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0959d-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="0959d-110">Wenn die Typen unterschiedlich sind, aber [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen in beide Richtungen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0959d-110">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="0959d-111">Wenn der Typ den Typ Klasse oder Struktur ist [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen sie umwandeln, um sowohl vom anderen Typ.</span><span class="sxs-lookup"><span data-stu-id="0959d-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="0959d-112">Wenn eine dieser Konvertierungen erweiternde ist, kann die umgekehrte Konvertierung einschränken.</span><span class="sxs-lookup"><span data-stu-id="0959d-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="0959d-113">**Fehler-ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="0959d-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0959d-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0959d-114">To correct this error</span></span>  
  
-   <span data-ttu-id="0959d-115">Verwenden Sie nach Möglichkeit ein aufrufendes Argument vom gleichen Typ wie der Prozedurparameter also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] muss nicht Konvertierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="0959d-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="0959d-116">Wenn Sie die Prozedur mit einem Argument aufrufen müssen anderen vom Parametertyp müssen jedoch nicht in das aufrufende Argument kein Wert zurückgegeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="0959d-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="0959d-117">Wenn in das aufrufende Argument ein Wert zurückgegeben werden sollen, definieren Sie den Operator für die umgekehrte Konvertierung als [Widening](../../../visual-basic/language-reference/modifiers/widening.md), sofern dies möglich.</span><span class="sxs-lookup"><span data-stu-id="0959d-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0959d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0959d-118">See Also</span></span>  
 <span data-ttu-id="0959d-119">[Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-119">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="0959d-120"> [Prozedurparameter und Argumente](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-120"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="0959d-121"> [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-121"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="0959d-122"> [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-122"> [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span></span>  
<span data-ttu-id="0959d-123"> [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-123"> [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="0959d-124"> [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-124"> [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="0959d-125"> [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-125"> [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="0959d-126"> [Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="0959d-126"> [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="0959d-127"> [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="0959d-127"> [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
