---
title: 'Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: f393f17f87c5920fb9bfa2a2097c09d48bebdc16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650591"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="28c4c-102">Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28c4c-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="28c4c-103">Wenn Sie eine Prozedur aufrufen, folgen Sie den Namen der Prozedur mit einer Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="28c4c-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="28c4c-104">Geben Sie ein Argument für jeden erforderlichen Parameter der Prozedur definiert, und geben Sie optional Argumente für die `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="28c4c-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="28c4c-105">Wenn Sie keine angeben einer `Optional` Parameter im Aufruf muss ein Komma, um seine Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben, sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="28c4c-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="28c4c-106">Wenn Sie beabsichtigen, ein Argument eines Datentyps wie z. B. unterscheidet, von den entsprechenden Parameter übergeben `Byte` auf `String`, Sie können festlegen, dass den Switch Typprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) zu `Off`.</span><span class="sxs-lookup"><span data-stu-id="28c4c-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="28c4c-107">Wenn `Option Strict` ist `On`, verwenden Sie entweder erweiternde Konvertierungen oder explizite Konvertierungsschlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="28c4c-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="28c4c-108">Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="28c4c-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="28c4c-109">Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="28c4c-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="28c4c-110">Um ein oder mehrere Argumente an eine Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="28c4c-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="28c4c-111">Führen Sie in der aufrufenden Anweisung den Prozedurnamen mit Klammern aus.</span><span class="sxs-lookup"><span data-stu-id="28c4c-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="28c4c-112">Fügen Sie innerhalb der Klammern eine Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="28c4c-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="28c4c-113">Ein Argument für jeden Parameter erforderlich, dass die Prozedur definiert sind, und trennen Sie die Argumente durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="28c4c-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="28c4c-114">Stellen Sie sicher, dass jedes Argument ist ein gültiger Ausdruck, der eine Daten konvertiert werden kann, den Typ der Prozedur ergibt für den entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="28c4c-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="28c4c-115">Wenn ein Parameter, als definiert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), Sie können entweder in der Argumentliste eingeschlossen wird, oder lassen sie.</span><span class="sxs-lookup"><span data-stu-id="28c4c-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="28c4c-116">Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.</span><span class="sxs-lookup"><span data-stu-id="28c4c-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="28c4c-117">Wenn Sie ein Argument für weglassen ein `Optional` Parameter ein anderer Parameter nach ihm in der Parameterliste ist, können Sie die Stelle der ausgelassenes Argument markieren, durch ein zusätzliches Komma in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="28c4c-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="28c4c-118">Im folgenden Beispiel wird das Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktion.</span><span class="sxs-lookup"><span data-stu-id="28c4c-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     <span data-ttu-id="28c4c-119">Das obige Beispiel liefert das erforderliche erste Argument, also die Zeichenfolge, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="28c4c-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="28c4c-120">Es wird ein Argument für den optionalen zweiten Parameter, der angibt, die Schaltflächen im Meldungsfeld anzuzeigende ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="28c4c-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="28c4c-121">Da der Aufruf einen Wert nicht angegeben wird `MsgBox` verwendet den Standardwert `MsgBoxStyle.OKOnly`, woraufhin nur ein **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="28c4c-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="28c4c-122">Das zweite Komma in der Argumentliste markiert die Position des zweiten Arguments nicht angegeben, und die letzte Zeichenfolge übergeben wird, des optionalen dritten Parameters von `MsgBox`, dies ist der Text, der in der Titelleiste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="28c4c-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c4c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28c4c-123">See also</span></span>

 [<span data-ttu-id="28c4c-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="28c4c-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="28c4c-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="28c4c-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="28c4c-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="28c4c-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="28c4c-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="28c4c-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="28c4c-128">Gewusst wie: Definieren eines Parameters für eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="28c4c-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="28c4c-129">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="28c4c-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="28c4c-130">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="28c4c-130">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="28c4c-131">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="28c4c-131">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="28c4c-132">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="28c4c-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="28c4c-133">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28c4c-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
