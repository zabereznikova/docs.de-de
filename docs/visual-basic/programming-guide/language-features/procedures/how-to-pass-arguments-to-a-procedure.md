---
title: 'Vorgehensweise: Übergeben von Argumenten an eine Prozedur'
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
ms.openlocfilehash: 903e05facccd1f2afdf4bb51b200531feb64aa79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387776"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="c321f-102">Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c321f-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="c321f-103">Wenn Sie eine Prozedur aufzurufen, befolgen Sie den Namen der Prozedur mit einer Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="c321f-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="c321f-104">Sie geben ein Argument an, das allen erforderlichen Parametern entspricht, die die Prozedur definiert, und Sie können optional Argumente für die Parameter bereitstellen `Optional` .</span><span class="sxs-lookup"><span data-stu-id="c321f-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="c321f-105">Wenn Sie im-Befehl keinen- `Optional` Parameter angeben, müssen Sie ein Komma einschließen, um die Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben.</span><span class="sxs-lookup"><span data-stu-id="c321f-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="c321f-106">Wenn Sie beabsichtigen, ein Argument eines Datentyps zu übergeben, das sich von dem des entsprechenden Parameters unterscheidet (z. b. `Byte` in) `String` , können Sie den Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)) auf festlegen `Off` .</span><span class="sxs-lookup"><span data-stu-id="c321f-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="c321f-107">Wenn `Option Strict` ist `On` , müssen Sie entweder Erweiterungs Konvertierungen oder explizite Konvertierungs Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c321f-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="c321f-108">Weitere Informationen finden Sie unter [erweiternde und einschränkende Konvertierungen](../data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungs Funktionen](../../../language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c321f-108">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="c321f-109">Weitere Informationen finden Sie unter [Prozedur Parameter und-Argumente](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="c321f-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="c321f-110">So übergeben Sie ein oder mehrere Argumente an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="c321f-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="c321f-111">Befolgen Sie in der aufrufenden Anweisung den Prozedur Namen mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="c321f-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="c321f-112">Fügen Sie innerhalb der Klammern eine Argumentliste ein.</span><span class="sxs-lookup"><span data-stu-id="c321f-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="c321f-113">Fügen Sie ein Argument für jeden erforderlichen Parameter ein, der von der Prozedur definiert wird, und trennen Sie die Argumente durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="c321f-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="c321f-114">Stellen Sie sicher, dass jedes Argument ein gültiger Ausdruck ist, der einen-Datentyp ergibt, der in den Typ konvertiert wird, den die Prozedur für den entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="c321f-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="c321f-115">Wenn ein Parameter als [optional](../../../language-reference/modifiers/optional.md)definiert ist, können Sie ihn entweder in die Argumentliste einschließen oder ihn weglassen.</span><span class="sxs-lookup"><span data-stu-id="c321f-115">If a parameter is defined as [Optional](../../../language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="c321f-116">Wenn Sie es weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c321f-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="c321f-117">Wenn Sie ein Argument für einen Parameter weglassen `Optional` und in der Parameterliste ein weiterer Parameter vorhanden ist, können Sie die Position des ausgelassenen Arguments mit einem zusätzlichen Komma in der Argumentliste markieren.</span><span class="sxs-lookup"><span data-stu-id="c321f-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="c321f-118">Im folgenden Beispiel wird die Visual Basic- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktion aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c321f-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="c321f-119">Im vorangehenden Beispiel wird das erforderliche erste Argument angegeben, das die anzuzeigende Meldungs Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="c321f-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="c321f-120">Es lässt ein Argument für den optionalen zweiten Parameter aus, das die Schaltflächen angibt, die im Meldungs Feld angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c321f-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="c321f-121">Da der-Befehl keinen Wert bereitstellt, `MsgBox` verwendet den Standardwert, `MsgBoxStyle.OKOnly` , der nur eine Schaltfläche " **OK** " anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c321f-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="c321f-122">Das zweite Komma in der Argumentliste markiert die Stelle des ausgelassenen zweiten Arguments, und die letzte Zeichenfolge wird an den optionalen dritten Parameter von übergeben `MsgBox` . Dies ist der Text, der in der Titelleiste angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c321f-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c321f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c321f-123">See also</span></span>

- [<span data-ttu-id="c321f-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c321f-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="c321f-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c321f-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="c321f-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="c321f-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="c321f-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="c321f-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c321f-128">Vorgehensweise: Definieren eines Parameters für eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="c321f-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="c321f-129">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="c321f-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="c321f-130">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c321f-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="c321f-131">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="c321f-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c321f-132">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="c321f-132">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="c321f-133">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c321f-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
