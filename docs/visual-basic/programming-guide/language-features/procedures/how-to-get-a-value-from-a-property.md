---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 719a4fc9ff163fb4437ea40c8265a5e36232347e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="3f748-102">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f748-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="3f748-103">Abrufen des Werts einer Eigenschaft von den Eigenschaftennamen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="3f748-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="3f748-104">Der Eigenschaft `Get` Prozedur ruft den Wert ab, aber Sie rufen ihn nicht explizit nach Namen.</span><span class="sxs-lookup"><span data-stu-id="3f748-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="3f748-105">Verwenden Sie die Eigenschaft, wie Sie eine Variable verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="3f748-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="3f748-106">Ruft die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3f748-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="3f748-107">Zum Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3f748-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="3f748-108">Verwenden Sie den Eigenschaftennamen in einem Ausdruck die gleiche Weise wie ein Variablenname.</span><span class="sxs-lookup"><span data-stu-id="3f748-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="3f748-109">Sie können eine Eigenschaft überall dort verwenden, eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="3f748-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="3f748-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="3f748-110">-or-</span></span>  
  
     <span data-ttu-id="3f748-111">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="3f748-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="3f748-112">Das folgende Beispiel liest den Wert der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` Eigenschaft implizit aufgerufen seine `Get` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="3f748-112">The following example reads the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="3f748-113">[!code-vb[VbVbalrDateProperties&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3f748-113">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="3f748-114">Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="3f748-114">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3f748-115">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="3f748-115">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="3f748-116">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="3f748-116">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3f748-117">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="3f748-117">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="3f748-118">Der Wert der Eigenschaft hat im Ausdruck wie eine Variable oder Konstante, oder wird in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3f748-118">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f748-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f748-119">See Also</span></span>  
 <span data-ttu-id="3f748-120">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-120">[Procedures](./index.md) </span></span>  
<span data-ttu-id="3f748-121"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="3f748-122"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-122"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="3f748-123"> [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-123"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="3f748-124"> [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-124"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="3f748-125"> [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-125"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="3f748-126"> [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-126"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="3f748-127"> [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-127"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="3f748-128"> [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="3f748-128"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="3f748-129"> [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="3f748-129"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md)</span></span>
