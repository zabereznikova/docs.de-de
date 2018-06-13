---
title: 'Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651410"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="2cbbf-102">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cbbf-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="2cbbf-103">Gegebenenfalls die `Get` und `Set` Prozeduren in einer Eigenschaft, die über verschiedene Zugriffsebenen verfügen, können Sie die restriktivere Ebene in der `Property` -Anweisung und die restriktivere Ebene entweder in der `Get` oder `Set` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="2cbbf-104">Verwenden Sie gemischten Zugriffsebenen auf eine Eigenschaft, wenn Sie bestimmte Teile des Codes, um den Wert der Eigenschaft abrufen zu können, und bestimmte andere Teile des Codes in der Lage, zum Ändern des Werts sein möchten.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="2cbbf-105">Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2cbbf-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="2cbbf-106">Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="2cbbf-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="2cbbf-107">Deklarieren Sie die Eigenschaft auf die übliche Weise, und geben Sie die weniger restriktive Zugriffsebene (z. B. `Public`) in der `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="2cbbf-108">Deklarieren Sie entweder die `Get` oder `Set` Prozedur die stärker einschränkende Zugriffsebene angeben (z. B. `Friend`).</span><span class="sxs-lookup"><span data-stu-id="2cbbf-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="2cbbf-109">Geben Sie eine Zugriffsebene auf die anderen Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="2cbbf-110">Es wird davon ausgegangen, die Zugriffsebene, die deklariert wird, der `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="2cbbf-111">Sie können den Zugriff auf nur einer der Eigenschaftenprozeduren einschränken.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="2cbbf-112">Im vorherigen Beispiel der `Get` Prozedur hat die gleiche `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur umfasst `Private` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="2cbbf-113">Eine abgeleitete Klasse `employee` lesen können die `salary` Wert, sondern nur die `employee` Klasse festlegen.</span><span class="sxs-lookup"><span data-stu-id="2cbbf-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbbf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cbbf-114">See Also</span></span>  
 [<span data-ttu-id="2cbbf-115">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2cbbf-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="2cbbf-116">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="2cbbf-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="2cbbf-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2cbbf-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="2cbbf-118">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2cbbf-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="2cbbf-119">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2cbbf-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="2cbbf-120">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2cbbf-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="2cbbf-121">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="2cbbf-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="2cbbf-122">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2cbbf-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="2cbbf-123">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2cbbf-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="2cbbf-124">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2cbbf-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
