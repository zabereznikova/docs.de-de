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
ms.openlocfilehash: 14aa25de78eb357f8474d3828aa45e48e7a4f9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863844"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="18575-102">Vorgehensweise: Definieren eines Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18575-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="18575-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten von Standardoperatoren definieren (z. B. `*`, `<>`, oder `And`) Wenn eine oder beide der Operanden vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="18575-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="18575-104">Definieren Sie den standard-Operator als einer Operatorprozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="18575-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="18575-105">Alle Operatorprozeduren muss `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="18575-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="18575-106">Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="18575-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18575-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18575-107">Example</span></span>  
 <span data-ttu-id="18575-108">Das folgende Beispiel definiert die `+` Operator für eine Struktur namens `height`.</span><span class="sxs-lookup"><span data-stu-id="18575-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="18575-109">Die Struktur wird verwendet, gemessen in Fuß und Zoll Höhe.</span><span class="sxs-lookup"><span data-stu-id="18575-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="18575-110">Eine *Zoll* ist 2,54 Zentimeter, *foot* ist 12 Zoll.</span><span class="sxs-lookup"><span data-stu-id="18575-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="18575-111">Um sicherzustellen, dass normalisierte Werte (Zoll < 12.0), der Konstruktor führt *modulo* arithmetische 12.</span><span class="sxs-lookup"><span data-stu-id="18575-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="18575-112">Die `+` Operator wird der Konstruktor verwendet, um normalisierte Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="18575-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="18575-113">Sie können die Struktur testen `height` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="18575-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="18575-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18575-114">See also</span></span>

- [<span data-ttu-id="18575-115">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="18575-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="18575-116">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="18575-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="18575-117">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="18575-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="18575-118">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="18575-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="18575-119">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18575-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="18575-120">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="18575-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="18575-121">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="18575-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="18575-122">Mod-Operator</span><span class="sxs-lookup"><span data-stu-id="18575-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
