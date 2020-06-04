---
title: 'Vorgehensweise: Ablegen eines Werts in eine Eigenschaft'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: c0fb3e137010390097a68aea161efcff93839d94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414336"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="55509-102">Gewusst wie: Ablegen eines Werts in eine Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55509-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="55509-103">Sie speichern einen Wert in einer Eigenschaft, indem Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung platzieren.</span><span class="sxs-lookup"><span data-stu-id="55509-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="55509-104">Die-Prozedur der Eigenschaft `Set` speichert einen Wert, Sie wird jedoch nicht explizit anhand des Namens aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="55509-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="55509-105">Sie verwenden die-Eigenschaft wie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="55509-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="55509-106">Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="55509-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="55509-107">So speichern Sie einen Wert in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55509-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="55509-108">Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="55509-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="55509-109">Im folgenden Beispiel wird der Wert der Visual Basic- `TimeOfDay` Eigenschaft auf 12 Uhr festgelegt, und die Prozedur wird implizit aufgerufen `Set` .</span><span class="sxs-lookup"><span data-stu-id="55509-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="55509-110">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="55509-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="55509-111">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="55509-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="55509-112">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="55509-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="55509-113">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="55509-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="55509-114">Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55509-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55509-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55509-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="55509-116">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="55509-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="55509-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="55509-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="55509-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="55509-118">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="55509-119">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55509-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="55509-120">Vorgehensweise: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55509-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="55509-121">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="55509-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="55509-122">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="55509-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="55509-123">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55509-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="55509-124">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55509-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
