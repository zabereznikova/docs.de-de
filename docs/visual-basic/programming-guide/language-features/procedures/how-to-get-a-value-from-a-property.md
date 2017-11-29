---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cde5408ea09398a79a3da01ae9b2d0202c58eaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="8c3c7-102">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c3c7-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="8c3c7-103">Rufen Sie den Wert einer Eigenschaft den Namen der Eigenschaft in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="8c3c7-104">Der Eigenschaft `Get` Prozedur ruft den Wert ab, aber Sie rufen sie nicht explizit nach Namen.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="8c3c7-105">Sie können die Eigenschaft verwenden, wie Sie eine Variable verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="8c3c7-106">Ruft die Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="8c3c7-107">Zum Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c3c7-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="8c3c7-108">Verwenden Sie den Namen der Eigenschaft in einem Ausdruck die gleiche Weise wie ein Variablenname.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="8c3c7-109">Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="8c3c7-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="8c3c7-110">-or-</span></span>  
  
     <span data-ttu-id="8c3c7-111">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="8c3c7-112">Das folgende Beispiel liest den Wert der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` Eigenschaft implizit Aufrufen seiner `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-112">The following example reads the value of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  <span data-ttu-id="8c3c7-113">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8c3c7-114">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="8c3c7-115">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8c3c7-116">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="8c3c7-117">Der Wert der Eigenschaft beteiligt ist, in dem Ausdruck ebenso wie eine Variable oder Konstante oder befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="8c3c7-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3c7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c3c7-118">See Also</span></span>  
 [<span data-ttu-id="8c3c7-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8c3c7-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8c3c7-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="8c3c7-120">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8c3c7-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="8c3c7-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8c3c7-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8c3c7-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="8c3c7-123">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c3c7-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="8c3c7-124">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c3c7-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="8c3c7-125">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="8c3c7-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="8c3c7-126">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="8c3c7-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="8c3c7-127">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c3c7-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="8c3c7-128">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c3c7-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
