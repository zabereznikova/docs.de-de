---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic) | Microsoft-Dokumentation
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: ef1ec16005bf0a7967d396054ae23c1023143c2a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="937e3-102">Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="937e3-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="937e3-103">Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignisse, aber die Einzelheiten der Implementierung in Strukturen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="937e3-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="937e3-104">Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Implementieren einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="937e3-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="937e3-105">Diese exemplarische Vorgehensweise stellt Informationen zum Erstellen einer Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="937e3-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="937e3-106">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="937e3-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="937e3-107">Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="937e3-107">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="937e3-108">Fügen Sie ein neues Modul in das Projekt, indem Sie auf **Modul hinzufügen** auf der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="937e3-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="937e3-109">Nennen Sie das neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="937e3-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="937e3-110">Der Code für das neue Modul wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="937e3-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="937e3-111">Definieren Sie eine Schnittstelle mit dem Namen `TestInterface` in `Module1` durch Eingabe `Interface TestInterface` zwischen der `Module` und `End Module` -Anweisungen, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="937e3-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="937e3-112">Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung um einen Codeblock zu bilden.</span><span class="sxs-lookup"><span data-stu-id="937e3-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="937e3-113">Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle durch Platzieren den folgenden Code zwischen die `Interface` und `End Interface` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="937e3-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     <span data-ttu-id="937e3-114">[!code-vb[VbVbalrOOP&#98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-114">[!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="937e3-115">Implementierung</span><span class="sxs-lookup"><span data-stu-id="937e3-115">Implementation</span></span>  
 <span data-ttu-id="937e3-116">Sie können feststellen, dass die Syntax zum Deklarieren von Schnittstellenmembern unterscheidet die Syntax zum Deklarieren von Klassenmembern.</span><span class="sxs-lookup"><span data-stu-id="937e3-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="937e3-117">Ursache für diesen Unterschied die Tatsache, dass Schnittstellen Implementierungscode enthalten können.</span><span class="sxs-lookup"><span data-stu-id="937e3-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="937e3-118">Implementieren die Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="937e3-118">To implement the interface</span></span>  
  
1.  <span data-ttu-id="937e3-119">Fügen Sie eine Klasse mit dem Namen `ImplementationClass` durch Hinzufügen folgender Anweisung zu `Module1`nach dem `End Interface` Anweisung aber vor der `End Module` -Anweisung, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="937e3-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     <span data-ttu-id="937e3-120">[!code-vb[VbVbalrOOP&#99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-120">[!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span></span>  
  
     <span data-ttu-id="937e3-121">Wenn Sie in der IDE arbeiten die **Code-Editor** stellt eine entsprechende `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="937e3-121">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="937e3-122">Fügen Sie die folgenden `Implements` -Anweisung `ImplementationClass`, implementiert die Schnittstelle der Klasse Namen:</span><span class="sxs-lookup"><span data-stu-id="937e3-122">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     <span data-ttu-id="937e3-123">[!code-vb[VbVbalrOOP&#100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-123">[!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span></span>  
  
     <span data-ttu-id="937e3-124">Wenn getrennt von anderen Elementen am Anfang einer Klasse oder Struktur steht die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="937e3-124">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="937e3-125">Wenn Sie in der IDE arbeiten die **Code-Editor** implementiert die erforderlichen Klassenmember `TestInterface` Wenn Sie die EINGABETASTE, und können Sie den nächsten Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="937e3-125">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="937e3-126">Wenn Sie nicht innerhalb der IDE arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="937e3-126">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="937e3-127">Fügen Sie den folgenden Code `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="937e3-127">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     <span data-ttu-id="937e3-128">[!code-vb[VbVbalrOOP&#101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-128">[!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span></span>  
  
     <span data-ttu-id="937e3-129">Die `Implements` -Anweisung benennt die Schnittstelle und die Member der Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="937e3-129">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="937e3-130">Vervollständigen Sie die Definition des `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:</span><span class="sxs-lookup"><span data-stu-id="937e3-130">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     <span data-ttu-id="937e3-131">[!code-vb[VbVbalrOOP&#102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-131">[!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span></span>  
  
     <span data-ttu-id="937e3-132">Der Rückgabewert von der `pval` aus der Eigenschaft get-Accessor.</span><span class="sxs-lookup"><span data-stu-id="937e3-132">Return the value of the `pval` from the property get accessor.</span></span>  
  
     <span data-ttu-id="937e3-133">[!code-vb[VbVbalrOOP&#103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-133">[!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span></span>  
  
     <span data-ttu-id="937e3-134">Legen Sie den Wert von `pval` in der Eigenschaft set-Accessor.</span><span class="sxs-lookup"><span data-stu-id="937e3-134">Set the value of `pval` in the property set accessor.</span></span>  
  
     <span data-ttu-id="937e3-135">[!code-vb[VbVbalrOOP&#104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-135">[!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span></span>  
  
5.  <span data-ttu-id="937e3-136">Vervollständigen Sie die Definition der `Method1` durch den folgenden Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="937e3-136">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     <span data-ttu-id="937e3-137">[!code-vb[VbVbalrOOP&#105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-137">[!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span></span>  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="937e3-138">So testen Sie die Implementierung der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="937e3-138">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="937e3-139">Mit der rechten Maustaste des Startformulars für das Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="937e3-139">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="937e3-140">Der Editor zeigt die Klasse des Startformulars.</span><span class="sxs-lookup"><span data-stu-id="937e3-140">The editor displays the class for your startup form.</span></span> <span data-ttu-id="937e3-141">Standardmäßig ist das Startformular bezeichnet `Form1`.</span><span class="sxs-lookup"><span data-stu-id="937e3-141">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="937e3-142">Fügen Sie die folgenden `testInstance` Feld der `Form1` Klasse:</span><span class="sxs-lookup"><span data-stu-id="937e3-142">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     <span data-ttu-id="937e3-143">[!code-vb[VbVbalrOOP&#120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-143">[!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span></span>  
  
     <span data-ttu-id="937e3-144">Durch Deklarieren `testInstance` als `WithEvents`die `Form1` Klasse, die Ereignisse behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="937e3-144">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="937e3-145">Fügen Sie den folgenden Ereignishandler, um die `Form1` Klasse ausgelöste Ereignisse behandeln `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="937e3-145">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     <span data-ttu-id="937e3-146">[!code-vb[VbVbalrOOP&#106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-146">[!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span></span>  
  
4.  <span data-ttu-id="937e3-147">Fügen Sie eine Unterroutine namens `Test` an die `Form1` Klasse, um die Implementierungsklasse zu testen:</span><span class="sxs-lookup"><span data-stu-id="937e3-147">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     <span data-ttu-id="937e3-148">[!code-vb[VbVbalrOOP&#107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-148">[!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span></span>  
  
     <span data-ttu-id="937e3-149">Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz dem `testInstance` Feld legt eine Eigenschaft fest und führt eine Methode über die Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="937e3-149">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="937e3-150">Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Verfahren des Startformulars:</span><span class="sxs-lookup"><span data-stu-id="937e3-150">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     <span data-ttu-id="937e3-151">[!code-vb[VbVbalrOOP&#108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="937e3-151">[!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span></span>  
  
6.  <span data-ttu-id="937e3-152">Führen Sie die `Test` Prozedur durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="937e3-152">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="937e3-153">Die Meldung "Prop1 was set to 9" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="937e3-153">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="937e3-154">Nachdem Sie OK, klicken Sie auf die Meldung "The X Parameter for Method1 is 5" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="937e3-154">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="937e3-155">Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis erfasst" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="937e3-155">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937e3-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="937e3-156">See Also</span></span>  
 <span data-ttu-id="937e3-157">[Implements-Anweisung](../../../../visual-basic/language-reference/statements/implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="937e3-157">[Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md) </span></span>  
<span data-ttu-id="937e3-158"> [Schnittstellen](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="937e3-158"> [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span></span>  
<span data-ttu-id="937e3-159"> [Interface-Anweisung](../../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="937e3-159"> [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="937e3-160"> [Event-Anweisung](../../../../visual-basic/language-reference/statements/event-statement.md)</span><span class="sxs-lookup"><span data-stu-id="937e3-160"> [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)</span></span>

