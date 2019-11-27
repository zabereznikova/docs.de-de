---
title: Partielle Methoden
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
ms.openlocfilehash: 7abf0565a985f1fb44fcf2bb91b9220d57a10f20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352635"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="f76dc-102">Partielle Methoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f76dc-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="f76dc-103">Mit partiellen Methoden können Entwickler benutzerdefinierte Logik in den Code einfügen.</span><span class="sxs-lookup"><span data-stu-id="f76dc-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="f76dc-104">In der Regel ist der Code Teil einer vom Designer generierten Klasse.</span><span class="sxs-lookup"><span data-stu-id="f76dc-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="f76dc-105">Partielle Methoden werden in einer partiellen Klasse definiert, die von einem Code Generator erstellt wird, und Sie werden häufig verwendet, um Benachrichtigungen bereitzustellen, dass etwas geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f76dc-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="f76dc-106">Sie ermöglichen es dem Entwickler, als Reaktion auf die Änderung benutzerdefiniertes Verhalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f76dc-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="f76dc-107">Der Designer des Code-Generators definiert nur die Methoden Signatur und mindestens einen Aufruf der-Methode.</span><span class="sxs-lookup"><span data-stu-id="f76dc-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="f76dc-108">Entwickler können dann Implementierungen für die-Methode bereitstellen, wenn Sie das Verhalten des generierten Codes anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="f76dc-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="f76dc-109">Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der-Methode durch den Compiler entfernt, was zu keinem zusätzlichen Leistungs Aufwand führt.</span><span class="sxs-lookup"><span data-stu-id="f76dc-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="f76dc-110">Deklaration</span><span class="sxs-lookup"><span data-stu-id="f76dc-110">Declaration</span></span>  
 <span data-ttu-id="f76dc-111">Der generierte Code markiert die Definition einer partiellen Methode, indem das Schlüsselwort `Partial` am Anfang der Signatur Zeile platziert wird.</span><span class="sxs-lookup"><span data-stu-id="f76dc-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="f76dc-112">Die Definition muss die folgenden Bedingungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="f76dc-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="f76dc-113">Die Methode muss eine `Sub`und keine `Function`sein.</span><span class="sxs-lookup"><span data-stu-id="f76dc-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="f76dc-114">Der Text der Methode muss leer gelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f76dc-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="f76dc-115">Der Zugriffsmodifizierer muss `Private`werden.</span><span class="sxs-lookup"><span data-stu-id="f76dc-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="f76dc-116">Implementierung</span><span class="sxs-lookup"><span data-stu-id="f76dc-116">Implementation</span></span>  
 <span data-ttu-id="f76dc-117">Die-Implementierung besteht hauptsächlich aus dem Ausfüllen des Texts der partiellen-Methode.</span><span class="sxs-lookup"><span data-stu-id="f76dc-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="f76dc-118">Die Implementierung befindet sich in der Regel in einer separaten partiellen Klasse von der Definition und wird von einem Entwickler geschrieben, der den generierten Code erweitern möchte.</span><span class="sxs-lookup"><span data-stu-id="f76dc-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="f76dc-119">Im vorherigen Beispiel wird die Signatur in der Deklaration genau dupliziert, aber Variationen sind möglich.</span><span class="sxs-lookup"><span data-stu-id="f76dc-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="f76dc-120">Insbesondere können andere modifiziererer hinzugefügt werden, z. b. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="f76dc-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="f76dc-121">Es ist nur ein `Overrides` Modifizierer zulässig.</span><span class="sxs-lookup"><span data-stu-id="f76dc-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="f76dc-122">Weitere Informationen über methodenmodifiziererer finden Sie [unter Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f76dc-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="f76dc-123">Verwendung</span><span class="sxs-lookup"><span data-stu-id="f76dc-123">Use</span></span>  
 <span data-ttu-id="f76dc-124">Sie sollten eine partielle Methode wie jede andere `Sub` Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f76dc-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="f76dc-125">Wenn die-Methode implementiert wurde, werden die Argumente ausgewertet, und der Text der Methode wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f76dc-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="f76dc-126">Beachten Sie jedoch, dass die Implementierung einer partiellen Methode optional ist.</span><span class="sxs-lookup"><span data-stu-id="f76dc-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="f76dc-127">Wenn die Methode nicht implementiert wird, hat ein-aufrufsvorgang keine Auswirkung, und Ausdrücke, die als Argumente an die-Methode übermittelt werden, werden nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f76dc-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f76dc-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f76dc-128">Example</span></span>  
 <span data-ttu-id="f76dc-129">Definieren Sie in einer Datei mit dem Namen Product. Designer. vb eine `Product`-Klasse mit einer `Quantity`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f76dc-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="f76dc-130">Stellen Sie in einer Datei mit dem Namen Product. vb eine Implementierung für `QuantityChanged`bereit.</span><span class="sxs-lookup"><span data-stu-id="f76dc-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="f76dc-131">Deklarieren Sie schließlich in der Main-Methode eines Projekts eine `Product` Instanz, und geben Sie einen Anfangswert für die `Quantity`-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="f76dc-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="f76dc-132">Daraufhin wird ein Meldungs Feld angezeigt, in dem diese Meldung angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f76dc-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="f76dc-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f76dc-133">See also</span></span>

- [<span data-ttu-id="f76dc-134">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f76dc-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f76dc-135">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f76dc-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="f76dc-136">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="f76dc-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="f76dc-137">Partial</span><span class="sxs-lookup"><span data-stu-id="f76dc-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="f76dc-138">Codegenerierung in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f76dc-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="f76dc-139">Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden</span><span class="sxs-lookup"><span data-stu-id="f76dc-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
