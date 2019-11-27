---
title: 'Gewusst wie: Definieren eines Operators'
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
ms.openlocfilehash: b99af8ff4d5428f1749bfc1a4c51a136f12405ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344875"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="3be52-102">Gewusst wie: Definieren eines Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3be52-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="3be52-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines Standard Operators (z. b. `*`, `<>`oder `And`) definieren, wenn mindestens einer der Operanden vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="3be52-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3be52-104">Definieren Sie den Standard Operator als Operator Prozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="3be52-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="3be52-105">Alle Operator Prozeduren müssen `Shared``Public` werden.</span><span class="sxs-lookup"><span data-stu-id="3be52-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="3be52-106">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3be52-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3be52-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3be52-107">Example</span></span>  
 <span data-ttu-id="3be52-108">Im folgenden Beispiel wird der `+`-Operator für eine Struktur mit dem Namen `height`definiert.</span><span class="sxs-lookup"><span data-stu-id="3be52-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="3be52-109">Die Struktur verwendet Höhen, gemessen in Höhe und Zoll.</span><span class="sxs-lookup"><span data-stu-id="3be52-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="3be52-110">Ein *Zoll* beträgt 2,54 Zentimeter und ein *Fuß* ist 12 Zoll.</span><span class="sxs-lookup"><span data-stu-id="3be52-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="3be52-111">Um normalisierte Werte (Zoll < 12,0) sicherzustellen, führt der Konstruktor *Modulo* 12-Arithmetik aus.</span><span class="sxs-lookup"><span data-stu-id="3be52-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="3be52-112">Der `+`-Operator verwendet den-Konstruktor, um normalisierte Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3be52-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="3be52-113">Sie können die Struktur `height` mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="3be52-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="3be52-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3be52-114">See also</span></span>

- [<span data-ttu-id="3be52-115">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="3be52-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="3be52-116">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="3be52-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="3be52-117">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="3be52-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="3be52-118">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="3be52-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="3be52-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="3be52-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3be52-120">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3be52-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="3be52-121">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="3be52-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="3be52-122">Mod-Operator</span><span class="sxs-lookup"><span data-stu-id="3be52-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
