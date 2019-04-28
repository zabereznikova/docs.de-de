---
title: Operatorprozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 80c9a77494be95365899c6a25435fcfc5d2a7293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791975"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="84b71-102">Operatorprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b71-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="84b71-103">Eine Operatorprozedur besteht aus einer Reihe von Visual Basic-Anweisungen, die das Verhalten von Standardoperatoren definieren (z. B. `*`, `<>`, oder `And`) auf eine Klasse oder Struktur, die Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="84b71-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="84b71-104">Dies ist die Abkürzung *operatorüberladung*.</span><span class="sxs-lookup"><span data-stu-id="84b71-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="84b71-105">Beim Definieren von Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="84b71-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="84b71-106">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie die Variablen den Typ der Klasse oder Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="84b71-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="84b71-107">Manchmal muss eine solche Variable in einem Vorgang im Rahmen eines Ausdrucks teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="84b71-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="84b71-108">Zu diesem Zweck müssen sie ein Operand eines Operators sein.</span><span class="sxs-lookup"><span data-stu-id="84b71-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="84b71-109">Visual Basic definiert nur die grundlegenden Datentypen von Operatoren.</span><span class="sxs-lookup"><span data-stu-id="84b71-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="84b71-110">Sie können das Verhalten eines Operators, wenn bei mindestens einem definieren oder beider Operanden sind vom Typ der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="84b71-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="84b71-111">Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="84b71-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="84b71-112">Typen von Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="84b71-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="84b71-113">Eine Operatorprozedur kann es sich um eine der folgenden Typen sein:</span><span class="sxs-lookup"><span data-stu-id="84b71-113">An operator procedure can be one of the following types:</span></span>  
  
- <span data-ttu-id="84b71-114">Eine Definition eines unären Operators, in dem das Argument vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="84b71-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="84b71-115">Eine Definition eines binären Operators, in denen mindestens eines der Argumente des Typs der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="84b71-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="84b71-116">Eine Definition eines Konvertierungsoperators, der den Typ der Klasse oder Struktur, in dem das Argument ist.</span><span class="sxs-lookup"><span data-stu-id="84b71-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="84b71-117">Eine Definition eines Konvertierungsoperators, die den Typ der Klasse oder Struktur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="84b71-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="84b71-118">Konvertierungsoperatoren sind immer unär, und Sie immer `CType` wie der Operator, die Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="84b71-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="84b71-119">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="84b71-119">Declaration Syntax</span></span>  
 <span data-ttu-id="84b71-120">Die Syntax zum Deklarieren einer Operatorprozedur lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="84b71-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="84b71-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *Operatorsymbol* `(` *operand1*`[,`*operand2* `]) As` *Datatype*</span><span class="sxs-lookup"><span data-stu-id="84b71-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="84b71-122">Sie verwenden die `Widening` oder `Narrowing` Schlüsselwort nur auf einen Operator für die Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="84b71-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="84b71-123">Das Operatorsymbol ist immer [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) für einen Typkonvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="84b71-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="84b71-124">Sie deklarieren die beiden Operanden einen binären Operator definieren, und Sie deklarieren, dass einer der Operanden einen unäroperator, einschließlich einen Typkonvertierungsoperator zu definieren.</span><span class="sxs-lookup"><span data-stu-id="84b71-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="84b71-125">Alle Operanden müssen deklariert werden `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="84b71-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="84b71-126">Sie deklarieren jeder Operand auf die gleiche Weise, die Sie deklarieren die Parameter für [Sub-Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="84b71-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="84b71-127">Datentyp</span><span class="sxs-lookup"><span data-stu-id="84b71-127">Data Type</span></span>  
 <span data-ttu-id="84b71-128">Da Sie für eine Klasse oder Struktur, die Sie definiert haben einen Operator definieren, muss mindestens einer der Operanden für den Datentyp, der diese Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="84b71-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="84b71-129">Für einen Typumwandlungsoperator verwenden muss entweder der Operand oder der Rückgabetyp des Datentyps der Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="84b71-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="84b71-130">Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="84b71-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="84b71-131">Die Syntax aufrufen</span><span class="sxs-lookup"><span data-stu-id="84b71-131">Calling Syntax</span></span>  
 <span data-ttu-id="84b71-132">Sie aufrufen eine Operatorprozedur implizit mit dem Symbol "Operator" in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="84b71-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="84b71-133">Sie geben die Operanden auf die gleiche Weise, die für die vordefinierten Operatoren erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="84b71-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="84b71-134">Die Syntax für einen impliziten Aufruf einer Operatorprozedur lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="84b71-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="84b71-135">`Dim testStruct As`  *Strukturname*</span><span class="sxs-lookup"><span data-stu-id="84b71-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="84b71-136">`Dim testNewStruct As`  *Strukturname*`= testStruct`*Operatorsymbol*  `10`</span><span class="sxs-lookup"><span data-stu-id="84b71-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="84b71-137">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="84b71-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="84b71-138">Die folgende Struktur speichert einen 128-Bit-Ganzzahl-Wert als die höherwertigen und niederwertigen Bestandteile.</span><span class="sxs-lookup"><span data-stu-id="84b71-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="84b71-139">Definiert die `+` Operator, um zwei `veryLong` Werte und generiert eine resultierende `veryLong` Wert.</span><span class="sxs-lookup"><span data-stu-id="84b71-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="84b71-140">Das folgende Beispiel zeigt einen typischen Aufruf von der `+` Operator definiert `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="84b71-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="84b71-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84b71-141">See also</span></span>

- [<span data-ttu-id="84b71-142">Verfahren</span><span class="sxs-lookup"><span data-stu-id="84b71-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="84b71-143">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="84b71-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="84b71-144">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="84b71-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="84b71-145">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="84b71-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="84b71-146">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="84b71-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="84b71-147">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="84b71-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="84b71-148">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="84b71-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="84b71-149">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="84b71-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="84b71-150">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="84b71-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="84b71-151">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="84b71-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
