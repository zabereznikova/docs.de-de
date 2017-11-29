---
title: 'Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)'
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44e7c4a92ea3d087c12e74aa2ede33a52c8730cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="9fc94-102">Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fc94-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="9fc94-103">Sie speichern einen Wert in einer Eigenschaft an, indem Sie den Namen der Eigenschaft auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="9fc94-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="9fc94-104">Der Eigenschaft `Set` Prozedur speichert einen Wert, aber Sie rufen sie nicht explizit nach Namen.</span><span class="sxs-lookup"><span data-stu-id="9fc94-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="9fc94-105">Sie können die Eigenschaft verwenden, wie Sie eine Variable verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="9fc94-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9fc94-106">Ruft die Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="9fc94-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="9fc94-107">Zum Speichern eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9fc94-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="9fc94-108">Verwenden Sie den Namen der Eigenschaft, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="9fc94-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="9fc94-109">Im folgenden Beispiel wird den Wert des der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `TimeOfDay` Eigenschaft am Mittag implizit Aufrufen seiner `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="9fc94-109">The following example sets the value of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="9fc94-110">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="9fc94-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="9fc94-111">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="9fc94-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="9fc94-112">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="9fc94-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="9fc94-113">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="9fc94-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="9fc94-114">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9fc94-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc94-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fc94-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [<span data-ttu-id="9fc94-116">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="9fc94-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="9fc94-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9fc94-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9fc94-118">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9fc94-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="9fc94-119">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fc94-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="9fc94-120">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9fc94-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="9fc94-121">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="9fc94-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="9fc94-122">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="9fc94-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="9fc94-123">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fc94-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="9fc94-124">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9fc94-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
