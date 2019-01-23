---
title: 'Vorgehensweise: Definieren eines Konvertierungsoperators (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 76d0769456e30766b830023c1f27381ceca59cbb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521529"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="1a8e9-102">Vorgehensweise: Definieren eines Konvertierungsoperators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a8e9-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="1a8e9-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Operator für die Konvertierung zwischen dem Typ der Klasse oder Struktur und einen anderen Datentyp definieren (z. B. `Integer`, `Double`, oder `String`).</span><span class="sxs-lookup"><span data-stu-id="1a8e9-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="1a8e9-104">Definieren Sie die typkonvertierung als eine [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="1a8e9-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="1a8e9-105">Alle Konvertierungsprozeduren muss `Public Shared`, und geben jeweils [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) oder [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="1a8e9-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="1a8e9-106">Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="1a8e9-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a8e9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a8e9-107">Example</span></span>  
 <span data-ttu-id="1a8e9-108">Das folgende Beispiel definiert Konvertierungsoperatoren zwischen einer Struktur mit dem Namen `digit` und `Byte`.</span><span class="sxs-lookup"><span data-stu-id="1a8e9-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="1a8e9-109">Sie können die Struktur testen `digit` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="1a8e9-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1a8e9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a8e9-110">See also</span></span>
- [<span data-ttu-id="1a8e9-111">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="1a8e9-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="1a8e9-112">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="1a8e9-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="1a8e9-113">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="1a8e9-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="1a8e9-114">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="1a8e9-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="1a8e9-115">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1a8e9-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="1a8e9-116">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1a8e9-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="1a8e9-117">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="1a8e9-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="1a8e9-118">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1a8e9-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="1a8e9-119">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1a8e9-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
