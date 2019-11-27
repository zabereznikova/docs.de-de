---
title: 'Gewusst wie: Definieren eines Konvertierungsoperators'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344896"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="b29d1-102">Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b29d1-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="b29d1-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Typkonvertierungs Operator zwischen dem Typ der Klasse oder Struktur und einem anderen Datentyp (z. b. `Integer`, `Double`oder `String`) definieren.</span><span class="sxs-lookup"><span data-stu-id="b29d1-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="b29d1-104">Definieren Sie die Typkonvertierung als [CType-Funktions](../../../../visual-basic/language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="b29d1-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="b29d1-105">Alle Konvertierungs Prozeduren müssen `Public Shared`werden, und jeder muss entweder eine [Erweiterung](../../../../visual-basic/language-reference/modifiers/widening.md) oder eine [Einschränkung](../../../../visual-basic/language-reference/modifiers/narrowing.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="b29d1-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="b29d1-106">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b29d1-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29d1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b29d1-107">Example</span></span>  
 <span data-ttu-id="b29d1-108">Im folgenden Beispiel werden Konvertierungs Operatoren zwischen einer Struktur namens `digit` und einer `Byte`definiert.</span><span class="sxs-lookup"><span data-stu-id="b29d1-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="b29d1-109">Sie können die Struktur `digit` mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="b29d1-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b29d1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b29d1-110">See also</span></span>

- [<span data-ttu-id="b29d1-111">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="b29d1-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b29d1-112">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="b29d1-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="b29d1-113">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="b29d1-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="b29d1-114">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="b29d1-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="b29d1-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b29d1-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="b29d1-116">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b29d1-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="b29d1-117">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="b29d1-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="b29d1-118">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b29d1-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b29d1-119">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b29d1-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
