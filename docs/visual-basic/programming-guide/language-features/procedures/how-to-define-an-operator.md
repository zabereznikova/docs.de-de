---
title: 'Gewusst wie: Definieren eines Operators (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: c759ebf38ab0727aeada218d288b5ac01e3ecd03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="f258a-102">Gewusst wie: Definieren eines Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f258a-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="f258a-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines standard-Operators definieren (z. B. `*`, `<>`, oder `And`) Wenn einer oder beide der Operanden vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="f258a-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="f258a-104">Definieren Sie den standard-Operator als einer Operatorprozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="f258a-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="f258a-105">Alle Operatorprozeduren muss `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f258a-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="f258a-106">Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="f258a-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f258a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f258a-107">Example</span></span>  
 <span data-ttu-id="f258a-108">Das folgende Beispiel definiert die `+` -Operator für eine Struktur aufgerufen `height`.</span><span class="sxs-lookup"><span data-stu-id="f258a-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="f258a-109">Die Struktur verwendet in Fuß und Zoll gemessen Höhe.</span><span class="sxs-lookup"><span data-stu-id="f258a-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="f258a-110">Eine *Zoll* handelt 2,54 Zentimeter und mindestens ein *foot* beträgt 12 Zoll.</span><span class="sxs-lookup"><span data-stu-id="f258a-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="f258a-111">Um sicherzustellen, dass normalisierte Werte (Zoll < 12.0), der Konstruktor führt *modulo* arithmetische 12.</span><span class="sxs-lookup"><span data-stu-id="f258a-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="f258a-112">Die `+` -Operator verwendet den Konstruktor, um normalisierte Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f258a-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="f258a-113">Sie können die Struktur testen `height` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="f258a-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="f258a-114">Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005 (Operatorüberladung in Visual Basic 2005)](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="f258a-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f258a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f258a-115">See Also</span></span>  
 [<span data-ttu-id="f258a-116">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="f258a-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="f258a-117">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="f258a-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="f258a-118">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="f258a-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="f258a-119">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="f258a-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="f258a-120">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f258a-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="f258a-121">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f258a-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="f258a-122">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="f258a-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="f258a-123">Mod-Operator</span><span class="sxs-lookup"><span data-stu-id="f258a-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
