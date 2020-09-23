---
title: 'Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen'
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
ms.openlocfilehash: 78363f7b2fb5b251f7409e53b2802baf83b05810
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072703"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="57144-102">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57144-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>

<span data-ttu-id="57144-103">Wenn Sie möchten, dass die `Get` -und- `Set` Prozeduren einer Eigenschaft über unterschiedliche Zugriffsebenen verfügen, können Sie in der- `Property` Anweisung und in der-oder-Anweisung die restriktivere Ebene verwenden `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="57144-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="57144-104">Sie verwenden gemischte Zugriffsebenen für eine Eigenschaft, wenn bestimmte Teile des Codes in der Lage sein sollen, den Wert der Eigenschaft zu erhalten, und bestimmte andere Teile des Codes in der Lage sein sollen, den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="57144-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="57144-105">Weitere Informationen zu Zugriffsebenen finden Sie unter [Zugriffsebenen in Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="57144-105">For more information on access levels, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="57144-106">So deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="57144-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="57144-107">Deklarieren Sie die-Eigenschaft auf normale Weise, und geben Sie die weniger restriktive Zugriffsebene (z `Public` . b.) in der- `Property` Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="57144-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="57144-108">Deklarieren Sie entweder die- `Get` oder die-Prozedur, und geben Sie `Set` die restriktivere Zugriffsebene (z `Friend` . b</span><span class="sxs-lookup"><span data-stu-id="57144-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="57144-109">Geben Sie für die andere Eigenschaften Prozedur keine Zugriffsebene an.</span><span class="sxs-lookup"><span data-stu-id="57144-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="57144-110">Es wird davon ausgegangen, dass die in der Anweisung deklarierte Zugriffsebene `Property` .</span><span class="sxs-lookup"><span data-stu-id="57144-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="57144-111">Sie können den Zugriff nur für eine der Eigenschaften Prozeduren einschränken.</span><span class="sxs-lookup"><span data-stu-id="57144-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="57144-112">Im vorherigen Beispiel `Get` hat die Prozedur denselben `Protected` Zugriff wie die Eigenschaft selbst, während die `Set` Prozedur `Private` Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="57144-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="57144-113">Eine von abgeleitete Klasse `employee` kann den `salary` Wert lesen, aber nur von der `employee` Klasse kann Sie festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="57144-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57144-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57144-114">See also</span></span>

- [<span data-ttu-id="57144-115">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="57144-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="57144-116">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="57144-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="57144-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="57144-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="57144-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="57144-118">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="57144-119">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57144-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="57144-120">Vorgehensweise: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57144-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="57144-121">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="57144-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="57144-122">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57144-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="57144-123">Vorgehensweise: Ablegen eines Werts in eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57144-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="57144-124">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57144-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
