---
title: Partielle Methoden (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: a1708c1d953a60429c1bd87fd858da5c50a3e759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651595"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="4cdb3-102">Partielle Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cdb3-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="4cdb3-103">Partielle Methoden können Entwickler benutzerdefinierten Logik in Code einzufügen.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="4cdb3-104">In der Regel ist der Code Teil einer vom Designer generierte Klasse.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="4cdb3-105">Partielle Methoden werden in einer partiellen Klasse, die von einem Codegenerator erstellt wird definiert, und sie werden häufig verwendet, um die Benachrichtigung angeben, dass etwas geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="4cdb3-106">Sie ermöglichen es den Entwickler, die benutzerdefiniertes Verhalten als Reaktion auf die Änderung angeben.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="4cdb3-107">Der Designer des Code-Generators definiert nur die Signatur der Methode und eine oder mehrere Aufrufe der Methode.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="4cdb3-108">Entwickler können dann Implementierungen für die Methode bereitstellen, wenn sie das Verhalten des generierten Codes anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="4cdb3-109">Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der Methode durch den Compiler, wodurch keine zusätzliche Leistung beansprucht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="4cdb3-110">Deklaration</span><span class="sxs-lookup"><span data-stu-id="4cdb3-110">Declaration</span></span>  
 <span data-ttu-id="4cdb3-111">Der generierte Code kennzeichnet die Definition einer partiellen Methode, indem dem Schlüsselwort `Partial` am Anfang der Signaturzeile.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="4cdb3-112">Die Definition muss die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="4cdb3-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="4cdb3-113">Die Methode muss ein `Sub`, sondern eine `Function`.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="4cdb3-114">Der Text der Methode muss leer sein.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="4cdb3-115">Der Zugriffsmodifizierer muss `Private`.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="4cdb3-116">Implementierung</span><span class="sxs-lookup"><span data-stu-id="4cdb3-116">Implementation</span></span>  
 <span data-ttu-id="4cdb3-117">Die Implementierung besteht im Wesentlichen aus im Text der partiellen Methode zu füllen.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="4cdb3-118">Die Implementierung ist in der Regel in einer eigenen partiellen Klasse aus der Definition und durch ein Entwickler möchte, erweitern den generierten Code geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="4cdb3-119">Im vorherigen Beispiel wird die Signatur in der Deklaration genau dupliziert allerdings Varianten sind möglich.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="4cdb3-120">Insbesondere weiteren Modifizierer können hinzugefügt werden, z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="4cdb3-121">Nur ein `Overrides` -Modifizierer ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="4cdb3-122">Weitere Informationen zur Methodenmodifizierer finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4cdb3-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="4cdb3-123">Mit</span><span class="sxs-lookup"><span data-stu-id="4cdb3-123">Use</span></span>  
 <span data-ttu-id="4cdb3-124">Sie eine partielle Methode aufrufen, wie jeder andere würde `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="4cdb3-125">Wenn die Methode implementiert wurde, die Argumente ausgewertet werden, und der Text der Methode wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="4cdb3-126">Beachten Sie jedoch, dass eine partielle Methode implementieren optional ist.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="4cdb3-127">Wenn die Methode nicht implementiert wird, ein Aufruf hat keine Auswirkungen, und Ausdrücke, die als Argumente an die Methode übergeben werden nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cdb3-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cdb3-128">Example</span></span>  
 <span data-ttu-id="4cdb3-129">In einer Datei namens Product.Designer.vb, definieren eine `Product` -Klasse, verfügt ein `Quantity` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="4cdb3-130">Stellen Sie in einer Datei mit dem Namen Product.vb eine Implementierung für `QuantityChanged`.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="4cdb3-131">Deklarieren Sie schließlich in die Main-Methode eines Projekts eine `Product` Instanz, und geben Sie einen Anfangswert für seine `Quantity` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4cdb3-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="4cdb3-132">Ein Meldungsfeld sollte angezeigt, in dem diese Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4cdb3-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="4cdb3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cdb3-133">See Also</span></span>  
 [<span data-ttu-id="4cdb3-134">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4cdb3-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="4cdb3-135">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4cdb3-135">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="4cdb3-136">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="4cdb3-136">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="4cdb3-137">Partial</span><span class="sxs-lookup"><span data-stu-id="4cdb3-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="4cdb3-138">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4cdb3-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="4cdb3-139">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="4cdb3-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
