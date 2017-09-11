---
title: "Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
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
ms.openlocfilehash: 1e0a8d5e798f25f22f53f56a7c01bd69e3e14463
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="72975-102">Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72975-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="72975-103">Wenn Sie eine Prozedur aufrufen, führen Sie den Namen der Prozedur mit einer Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="72975-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="72975-104">Ein Argument für jeden erforderlichen Parameter definiert die Prozedur bereit, und geben Sie optional Argumente für die `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="72975-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="72975-105">Wenn Sie keinen angeben einer `Optional` Parameter im Aufruf muss ein Komma, um seine Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben, sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="72975-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="72975-106">Wenn Sie beabsichtigen, die Übergabe eines Arguments einen Datentyp sich von dem des entsprechenden Parameters, wie z. B. `Byte` auf `String`, Sie können festlegen, dass den Switch Typprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) zu `Off`.</span><span class="sxs-lookup"><span data-stu-id="72975-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="72975-107">Wenn `Option Strict` ist `On`, müssen Sie entweder verwenden erweiternde Konvertierungen oder explizite Konvertierungsschlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="72975-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="72975-108">Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="72975-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="72975-109">Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="72975-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="72975-110">Ein oder mehrere Argumente an eine Prozedur übergeben</span><span class="sxs-lookup"><span data-stu-id="72975-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="72975-111">Folgen Sie in der aufrufenden Anweisung den Namen der Prozedur mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="72975-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="72975-112">Fügen Sie innerhalb der Klammern eine Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="72975-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="72975-113">Ein Argument für jeden erforderlichen Parameter die Prozedur definiert sind, und trennen Sie die Argumente durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="72975-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="72975-114">Stellen Sie sicher, dass jedes Argument ein gültiger Ausdruck, der eine Daten konvertiert werden kann, der den Typ der Prozedur ergibt für den entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="72975-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="72975-115">Wenn ein Parameter, als definiert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), können Sie in der Argumentliste einschließen oder weglassen.</span><span class="sxs-lookup"><span data-stu-id="72975-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="72975-116">Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.</span><span class="sxs-lookup"><span data-stu-id="72975-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="72975-117">Wenn Sie ein Argument für auslassen einer `Optional` Parameter und einen weiteren Parameter nach dem in der Parameterliste, Sie können die Position des ausgelassenen Arguments durch ein zusätzliches Komma in der Argumentliste markieren.</span><span class="sxs-lookup"><span data-stu-id="72975-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="72975-118">Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="72975-118">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     <span data-ttu-id="72975-119">[!code-vb[VbVbcnProcedures&#34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="72975-119">[!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="72975-120">Das obige Beispiel liefert das erforderliche erste Argument ist die Zeichenfolge, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="72975-120">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="72975-121">Sie lässt es sich um ein Argument für den optionalen zweiten Parameter, durch Angabe die Schaltflächen im Meldungsfeld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="72975-121">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="72975-122">Da der Aufruf einen Wert nicht angegeben wird `MsgBox` verwendet den Standardwert `MsgBoxStyle.OKOnly`, woraufhin nur ein **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="72975-122">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="72975-123">Das zweite Komma in der Argumentliste markiert die Position des ausgelassenen zweiten Arguments, und die letzte Zeichenfolge wird an den optionalen dritten Parameter von übergeben `MsgBox`, wird in der Titelleiste angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72975-123">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72975-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72975-124">See Also</span></span>  
 <span data-ttu-id="72975-125">[Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="72975-125">[Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="72975-126"> [Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="72975-126"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="72975-127"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="72975-127"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="72975-128"> [Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="72975-128"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="72975-129"> [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="72975-129"> [How to: Define a Parameter for a Procedure](./how-to-define-a-parameter-for-a-procedure.md) </span></span>  
<span data-ttu-id="72975-130"> [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="72975-130"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="72975-131"> [Rekursive Prozeduren](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="72975-131"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="72975-132"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="72975-132"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="72975-133"> [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="72975-133"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="72975-134"> [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="72975-134"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
