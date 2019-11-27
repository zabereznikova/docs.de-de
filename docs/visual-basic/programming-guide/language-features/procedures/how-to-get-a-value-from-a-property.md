---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 85512d4311d3e731a2c4e129d6a01f9b3273b333
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339832"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="31029-102">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31029-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="31029-103">Sie rufen den Wert einer Eigenschaft ab, indem Sie den Eigenschaftsnamen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="31029-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="31029-104">Die `Get` Prozedur der Eigenschaft ruft den Wert ab, aber Sie rufen ihn nicht explizit anhand des Namens auf.</span><span class="sxs-lookup"><span data-stu-id="31029-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="31029-105">Sie verwenden die-Eigenschaft wie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="31029-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="31029-106">Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="31029-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="31029-107">So rufen Sie einen Wert aus einer Eigenschaft ab</span><span class="sxs-lookup"><span data-stu-id="31029-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="31029-108">Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="31029-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="31029-109">Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.</span><span class="sxs-lookup"><span data-stu-id="31029-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="31029-110">\- oder -</span><span class="sxs-lookup"><span data-stu-id="31029-110">-or-</span></span>  
  
     <span data-ttu-id="31029-111">Verwenden Sie den Eigenschaftsnamen nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="31029-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="31029-112">Im folgenden Beispiel wird der Wert der Visual Basic `Now`-Eigenschaft gelesen, wobei die `Get` Prozedur implizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="31029-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="31029-113">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="31029-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="31029-114">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="31029-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="31029-115">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="31029-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="31029-116">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="31029-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="31029-117">Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="31029-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31029-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31029-118">See also</span></span>

- [<span data-ttu-id="31029-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="31029-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="31029-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="31029-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="31029-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="31029-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="31029-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="31029-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="31029-123">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31029-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="31029-124">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="31029-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="31029-125">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="31029-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="31029-126">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="31029-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="31029-127">Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31029-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="31029-128">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="31029-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
