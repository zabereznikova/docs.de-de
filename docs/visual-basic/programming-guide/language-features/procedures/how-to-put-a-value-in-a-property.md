---
title: 'Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: e6aee5ea36c0315d5b01ae2734d17c9e7dab8e93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341854"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="6477a-102">Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6477a-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="6477a-103">Sie können einen Wert in einer Eigenschaft speichern, indem Sie die Namen der Eigenschaft auf der linken Seite einer zuweisungsanweisung einfügen.</span><span class="sxs-lookup"><span data-stu-id="6477a-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="6477a-104">Des Eigenschaftenwert `Set` Prozedur speichert einen Wert, aber Sie rufen sie nicht explizit anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="6477a-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="6477a-105">Verwenden Sie die Eigenschaft, genauso wie Sie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="6477a-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="6477a-106">Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6477a-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="6477a-107">Zum Speichern eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6477a-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="6477a-108">Verwenden Sie den Eigenschaftennamen, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="6477a-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="6477a-109">Im folgenden Beispiel wird den Wert des Visual Basic `TimeOfDay` Eigenschaft am Mittag implizit Aufrufen seiner `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="6477a-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="6477a-110">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="6477a-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="6477a-111">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="6477a-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="6477a-112">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="6477a-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="6477a-113">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="6477a-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="6477a-114">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6477a-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6477a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6477a-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="6477a-116">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="6477a-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6477a-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6477a-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6477a-118">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6477a-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="6477a-119">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6477a-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="6477a-120">Vorgehensweise: Erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6477a-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6477a-121">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="6477a-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="6477a-122">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="6477a-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="6477a-123">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6477a-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6477a-124">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6477a-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
