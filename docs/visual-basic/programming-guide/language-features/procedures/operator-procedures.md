---
title: Operatorprozeduren (Visual Basic) | Microsoft-Dokumentation
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
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
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
ms.openlocfilehash: 3b2e8466ad355521dcec3cf7b2949037e569eb9a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="ccb7e-102">Operatorprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccb7e-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="ccb7e-103">In einer Operatorprozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Anweisungen, die das Verhalten eines standard-Operators definieren (z. B. `*`, `<>`, oder `And`) für eine Klasse oder Struktur, die Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-103">An operator procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="ccb7e-104">Dies nennt man auch *überladen*.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="ccb7e-105">Beim Definieren von Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="ccb7e-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="ccb7e-106">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Variablen den Typ der Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="ccb7e-107">Mitunter muss eine solche Variable zur Teilnahme an eines Vorgangs als Teil eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="ccb7e-108">Zu diesem Zweck müssen sie ein Operand eines Operators sein.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-108">To do this, it must be an operand of an operator.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ccb7e-109">Operatoren definiert nur die grundlegenden Datentypen.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-109"> defines operators only on its fundamental data types.</span></span> <span data-ttu-id="ccb7e-110">Sie können das Verhalten eines Operators, wenn eine oder beide der Operanden sind vom Typ der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="ccb7e-111">Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ccb7e-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="ccb7e-112">Typen von Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="ccb7e-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="ccb7e-113">Eine Operatorprozedur kann einer der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="ccb7e-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="ccb7e-114">Eine Definition, in dem das Argument vom Typ der Klasse oder Struktur ist, ein unärer Operator.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="ccb7e-115">Eine Definition eines binären Operators, wobei mindestens eines der Argumente des Typs von der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="ccb7e-116">Eine Definition eines Konvertierungsoperators, wobei das Argument vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="ccb7e-117">Eine Definition eines Konvertierungsoperators, der den Typ der Klasse oder Struktur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="ccb7e-118">Konvertierungsoperatoren sind immer unär, und Sie immer `CType` wie der Operator definieren.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="ccb7e-119">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="ccb7e-119">Declaration Syntax</span></span>  
 <span data-ttu-id="ccb7e-120">Die Syntax zum Deklarieren einer Operatorprozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ccb7e-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="ccb7e-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="ccb7e-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="ccb7e-122">Verwenden Sie die `Widening` oder `Narrowing` nur für einen Typkonvertierungsoperator-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="ccb7e-123">Das Operatorsymbol ist immer [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) für einen Typkonvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="ccb7e-124">Sie deklarieren die beiden Operanden einen binären Operator definieren, und Sie deklarieren, dass einer der Operanden einen unärer Operator, z. B. einen Typkonvertierungsoperator definieren.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="ccb7e-125">Alle Operanden müssen deklariert werden `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="ccb7e-126">Sie deklarieren jeden Operanden auf die gleiche Weise, die Sie deklarieren die Parameter für [Sub-Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ccb7e-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="ccb7e-127">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ccb7e-127">Data Type</span></span>  
 <span data-ttu-id="ccb7e-128">Da Sie für eine Klasse oder Struktur definierten ein Operators definieren, muss mindestens einer der Operanden den Datentyp der Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="ccb7e-129">Für einen Typkonvertierungsoperator muss der Operand oder der Rückgabetyp des Datentyps der Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="ccb7e-130">Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ccb7e-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="ccb7e-131">Aufrufen der Syntax</span><span class="sxs-lookup"><span data-stu-id="ccb7e-131">Calling Syntax</span></span>  
 <span data-ttu-id="ccb7e-132">Sie aufrufen eine Operatorprozedur implizit durch das Operatorsymbol in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="ccb7e-133">Sie geben die Operanden auf die selbe Weise wie für die vordefinierten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="ccb7e-134">Die Syntax für einen impliziten Aufruf einer Operatorprozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ccb7e-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="ccb7e-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="ccb7e-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="ccb7e-136">`Dim testNewStruct As`  *Structurename*`= testStruct`*Operatorsymbol    *  `10`</span><span class="sxs-lookup"><span data-stu-id="ccb7e-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="ccb7e-137">Darstellung von Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="ccb7e-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="ccb7e-138">Die folgende Struktur speichert einen 128-Bit-Ganzzahl mit Vorzeichen-Wert als die konstituierenden höherwertigen und niedrigwertigen Teile.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="ccb7e-139">Definiert die `+` Operator, um zwei `veryLong` Werte und generiert einen `veryLong` Wert.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 <span data-ttu-id="ccb7e-140">[!code-vb[VbVbcnProcedures&23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ccb7e-140">[!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="ccb7e-141">Das folgende Beispiel zeigt einen normalen Aufruf der `+` Operator definiert `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="ccb7e-141">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 <span data-ttu-id="ccb7e-142">[!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ccb7e-142">[!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="ccb7e-143">Weitere Informationen und Beispiele finden Sie unter [Überladen von Operatoren in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="ccb7e-143">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb7e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccb7e-144">See Also</span></span>  
 <span data-ttu-id="ccb7e-145">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-145">[Procedures](./index.md) </span></span>  
<span data-ttu-id="ccb7e-146"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-146"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="ccb7e-147"> [Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-147"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="ccb7e-148"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-148"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="ccb7e-149"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-149"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="ccb7e-150"> [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-150"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="ccb7e-151"> [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-151"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="ccb7e-152"> [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-152"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="ccb7e-153"> [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ccb7e-153"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="ccb7e-154"> [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)</span><span class="sxs-lookup"><span data-stu-id="ccb7e-154"> [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md)</span></span>
