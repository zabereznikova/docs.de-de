---
title: 'Vorgehensweise: Definieren eines Operators (Visual Basic)'
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
ms.openlocfilehash: fb150298562c1ec91f73f3c8075f4f8a4fc20b27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679525"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="f9ae9-102">Vorgehensweise: Definieren eines Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9ae9-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="f9ae9-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten von Standardoperatoren definieren (z. B. `*`, `<>`, oder `And`) Wenn eine oder beide der Operanden vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="f9ae9-104">Definieren Sie den standard-Operator als einer Operatorprozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="f9ae9-105">Alle Operatorprozeduren muss `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="f9ae9-106">Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9ae9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9ae9-107">Example</span></span>  
 <span data-ttu-id="f9ae9-108">Das folgende Beispiel definiert die `+` Operator für eine Struktur namens `height`.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="f9ae9-109">Die Struktur wird verwendet, gemessen in Fuß und Zoll Höhe.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="f9ae9-110">Eine *Zoll* ist 2,54 Zentimeter, *foot* ist 12 Zoll.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="f9ae9-111">Um sicherzustellen, dass normalisierte Werte (Zoll < 12.0), der Konstruktor führt *modulo* arithmetische 12.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="f9ae9-112">Die `+` Operator wird der Konstruktor verwendet, um normalisierte Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="f9ae9-113">Sie können die Struktur testen `height` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="f9ae9-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="f9ae9-114">Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005 (Operatorüberladung in Visual Basic 2005)](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span><span class="sxs-lookup"><span data-stu-id="f9ae9-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ae9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9ae9-115">See also</span></span>
- [<span data-ttu-id="f9ae9-116">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="f9ae9-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f9ae9-117">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="f9ae9-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="f9ae9-118">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="f9ae9-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f9ae9-119">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="f9ae9-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="f9ae9-120">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f9ae9-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f9ae9-121">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f9ae9-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f9ae9-122">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="f9ae9-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f9ae9-123">Mod-Operator</span><span class="sxs-lookup"><span data-stu-id="f9ae9-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
