---
title: 'Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
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
ms.openlocfilehash: c838141a27c30b11765d30ae8b0c19bccc929f4b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="d51d9-102">Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d51d9-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="d51d9-103">Sie speichern einen Wert in einer Eigenschaft durch Festlegen der Eigenschaftenname auf der linken Seite einer Zuweisung-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d51d9-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="d51d9-104">Der Eigenschaft `Set` -Prozedur einen Wert speichert, aber Sie rufen ihn nicht explizit nach Namen.</span><span class="sxs-lookup"><span data-stu-id="d51d9-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="d51d9-105">Verwenden Sie die Eigenschaft, wie Sie eine Variable verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="d51d9-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d51d9-106">Ruft die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d51d9-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="d51d9-107">Zum Speichern eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d51d9-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="d51d9-108">Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisung-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d51d9-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="d51d9-109">Im folgenden Beispiel wird den Wert von der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` -Eigenschaft Uhr implizit aufgerufen seine `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="d51d9-109">The following example sets the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     <span data-ttu-id="d51d9-110">[!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d51d9-110">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="d51d9-111">Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="d51d9-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d51d9-112">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="d51d9-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="d51d9-113">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="d51d9-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d51d9-114">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d51d9-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="d51d9-115">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d51d9-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d51d9-116">See Also</span></span>  
 <span data-ttu-id="d51d9-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="d51d9-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span></span>   
<span data-ttu-id="d51d9-118"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-118"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="d51d9-119"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-119"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="d51d9-120"> [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-120"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="d51d9-121"> [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-121"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="d51d9-122"> [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-122"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="d51d9-123"> [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-123"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="d51d9-124"> [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-124"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="d51d9-125"> [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="d51d9-125"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="d51d9-126"> [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="d51d9-126"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
