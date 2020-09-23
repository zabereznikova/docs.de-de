---
title: 'Vorgehensweise: Definieren eines Operators'
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
ms.openlocfilehash: 5acbd0439ddbb956b80d56e23d11cd5e152f37ff
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087400"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="6aa7f-102">Gewusst wie: Definieren eines Operators (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6aa7f-102">How to: Define an Operator (Visual Basic)</span></span>

<span data-ttu-id="6aa7f-103">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines Standard Operators (z. b. `*` , `<>` oder) definieren, `And` Wenn mindestens einer der Operanden vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="6aa7f-104">Definieren Sie den Standard Operator als Operator Prozedur innerhalb der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="6aa7f-105">Alle Operator Prozeduren müssen sein `Public` `Shared` .</span><span class="sxs-lookup"><span data-stu-id="6aa7f-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="6aa7f-106">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa7f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6aa7f-107">Example</span></span>  

 <span data-ttu-id="6aa7f-108">Im folgenden Beispiel wird der- `+` Operator für eine Struktur mit dem Namen definiert `height` .</span><span class="sxs-lookup"><span data-stu-id="6aa7f-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="6aa7f-109">Die Struktur verwendet Höhen, gemessen in Höhe und Zoll.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="6aa7f-110">Ein *Zoll* beträgt 2,54 Zentimeter und ein *Fuß* ist 12 Zoll.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="6aa7f-111">Um normalisierte Werte (Zoll < 12,0) sicherzustellen, führt der Konstruktor *Modulo* 12-Arithmetik aus.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="6aa7f-112">Der- `+` Operator verwendet den-Konstruktor, um normalisierte Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="6aa7f-113">Sie können die Struktur `height` mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="6aa7f-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="6aa7f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aa7f-114">See also</span></span>

- [<span data-ttu-id="6aa7f-115">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="6aa7f-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="6aa7f-116">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="6aa7f-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="6aa7f-117">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="6aa7f-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="6aa7f-118">Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="6aa7f-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="6aa7f-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="6aa7f-119">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="6aa7f-120">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="6aa7f-120">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="6aa7f-121">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="6aa7f-121">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="6aa7f-122">Operator Mod</span><span class="sxs-lookup"><span data-stu-id="6aa7f-122">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
