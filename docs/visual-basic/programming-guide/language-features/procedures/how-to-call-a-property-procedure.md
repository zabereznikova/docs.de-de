---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic) | Microsoft-Dokumentation'
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
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
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
ms.openlocfilehash: d0d37fc2b7ae1d563a7e9d0a8e75343dd690089b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="1e311-102">Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e311-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="1e311-103">Sie aufrufen eine Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder deren Wert abrufen.</span><span class="sxs-lookup"><span data-stu-id="1e311-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="1e311-104">Sie Zugriff auf eine Eigenschaft die gleiche Weise, die Sie auf eine Variable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1e311-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="1e311-105">Der Eigenschaft `Set` -Prozedur einen Wert speichert und dessen `Get` Prozedur ruft den Wert ab.</span><span class="sxs-lookup"><span data-stu-id="1e311-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="1e311-106">Jedoch Sie nicht explizit diese Prozeduren anhand des Namens aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1e311-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="1e311-107">Wie würden Sie speichern oder den Wert einer Variablen abzurufen, verwenden Sie die Eigenschaft in eine Zuweisung oder einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1e311-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1e311-108">Ruft die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e311-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="1e311-109">Aufrufen einer Eigenschaftenprozedur Get</span><span class="sxs-lookup"><span data-stu-id="1e311-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="1e311-110">Verwenden Sie den Eigenschaftennamen in einem Ausdruck die gleiche Weise wie ein Variablenname.</span><span class="sxs-lookup"><span data-stu-id="1e311-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="1e311-111">Sie können eine Eigenschaft überall dort verwenden, eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="1e311-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="1e311-112">- oder - </span><span class="sxs-lookup"><span data-stu-id="1e311-112">-or-</span></span>  
  
     <span data-ttu-id="1e311-113">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="1e311-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="1e311-114">Das folgende Beispiel liest den Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>Eigenschaft implizit aufgerufen seine `Get` Prozedur.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="1e311-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="1e311-115">[!code-vb[VbVbalrDateProperties&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1e311-115">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="1e311-116">Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="1e311-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1e311-117">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="1e311-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="1e311-118">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="1e311-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1e311-119">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="1e311-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="1e311-120">Der Wert der Eigenschaft hat im Ausdruck wie eine Variable oder Konstante, oder wird in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1e311-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="1e311-121">Zum Aufrufen einer Eigenschaft der Prozedur festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e311-121">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="1e311-122">Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisung-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e311-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="1e311-123">Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>Eigenschaft implizit aufgerufen der `Set` Prozedur.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="1e311-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     <span data-ttu-id="1e311-124">[!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1e311-124">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span></span>  
  
2.  <span data-ttu-id="1e311-125">Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="1e311-125">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1e311-126">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="1e311-126">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="1e311-127">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="1e311-127">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1e311-128">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="1e311-128">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="1e311-129">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1e311-129">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e311-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e311-130">See Also</span></span>  
 <span data-ttu-id="1e311-131">[Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-131">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="1e311-132"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1e311-133"> [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-133"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="1e311-134"> [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-134"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="1e311-135"> [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-135"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="1e311-136"> [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-136"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="1e311-137"> [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-137"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="1e311-138"> [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-138"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="1e311-139"> [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-139"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md) </span></span>  
<span data-ttu-id="1e311-140"> [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1e311-140"> [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="1e311-141"> [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1e311-141"> [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
