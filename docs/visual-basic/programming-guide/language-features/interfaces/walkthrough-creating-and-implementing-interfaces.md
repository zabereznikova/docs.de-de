---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923309"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="30071-102">Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30071-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="30071-103">Schnittstellen beschreiben die Merkmale von Eigenschaften, Methoden und Ereignissen, belassen aber die Implementierungsdetails in Strukturen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="30071-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="30071-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Schnittstelle deklariert und implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="30071-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30071-105">Diese exemplarische Vorgehensweise bietet keine Informationen zum Erstellen einer Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="30071-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="30071-106">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30071-106">To define an interface</span></span>
  
1. <span data-ttu-id="30071-107">Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="30071-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="30071-108">Fügen Sie dem Projekt ein neues Modul hinzu, indem Sie im Menü **Projekt** auf **Modul hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="30071-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="30071-109">Benennen Sie das neue `Module1.vb` Modul, und klicken Sie auf **Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="30071-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="30071-110">Der Code für das neue Modul wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30071-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="30071-111">Definieren Sie eine Schnitt `TestInterface` Stelle `Module1` mit dem Namen in `Module` , `End Module` indem Sie zwischen der-Anweisung und der-Anweisung eingeben `Interface TestInterface`</span><span class="sxs-lookup"><span data-stu-id="30071-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="30071-112">Im **Code-Editor** wird das `Interface` Schlüsselwort eingerückt `End Interface` und eine-Anweisung hinzugefügt, um einen Codeblock zu bilden.</span><span class="sxs-lookup"><span data-stu-id="30071-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="30071-113">Definieren Sie eine Eigenschaft, eine Methode und ein Ereignis für die Schnittstelle, indem Sie den `Interface` folgenden `End Interface` Code zwischen den Anweisungen und platzieren:</span><span class="sxs-lookup"><span data-stu-id="30071-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="30071-114">Implementierung</span><span class="sxs-lookup"><span data-stu-id="30071-114">Implementation</span></span>

 <span data-ttu-id="30071-115">Sie werden feststellen, dass sich die Syntax zum Deklarieren von Schnittstellenmembern von der Syntax unterscheidet, mit der Klassenmember deklariert werden</span><span class="sxs-lookup"><span data-stu-id="30071-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="30071-116">Dieser Unterschied spiegelt die Tatsache wider, dass Schnittstellen keinen Implementierungs Code enthalten können.</span><span class="sxs-lookup"><span data-stu-id="30071-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="30071-117">So implementieren Sie die-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30071-117">To implement the interface</span></span>
  
1. <span data-ttu-id="30071-118">Fügen Sie eine Klasse `ImplementationClass` mit dem Namen hinzu, indem `Module1`Sie nach der `End Interface` Anweisung, aber vor `End Module` der Anweisung die folgende Anweisung hinzufügen, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="30071-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="30071-119">Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, liefert der **Code-Editor** eine entsprechende `End Class` Anweisung, wenn Sie die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="30071-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="30071-120">Fügen Sie die `Implements` folgende- `ImplementationClass`Anweisung hinzu, die die von der Klasse implementierte Schnittstelle benennt:</span><span class="sxs-lookup"><span data-stu-id="30071-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="30071-121">Wenn Sie getrennt von anderen Elementen oben in einer Klasse oder Struktur aufgeführt werden, gibt `Implements` die Anweisung an, dass die Klasse oder Struktur eine Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="30071-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="30071-122">Wenn Sie innerhalb der integrierten Entwicklungsumgebung arbeiten, implementiert der **Code-Editor** die Klassenmember, `TestInterface` die für erforderlich sind, wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="30071-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="30071-123">Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der-Schnittstelle `MyInterface`implementieren.</span><span class="sxs-lookup"><span data-stu-id="30071-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="30071-124">Fügen Sie den folgenden Code `ImplementationClass` hinzu, `Event1`um `Method1`, und `Prop1`zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="30071-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="30071-125">Die `Implements` -Anweisung benennt die implementierte Schnittstelle und den Schnittstellenmember.</span><span class="sxs-lookup"><span data-stu-id="30071-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="30071-126">Vervollständigen Sie die Definition `Prop1` von, indem Sie der Klasse, die den Eigenschafts Wert gespeichert hat, ein privates Feld hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="30071-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="30071-127">Gibt den Wert von `pval` aus dem Get-Accessor der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="30071-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="30071-128">Legen Sie den Wert `pval` von im Eigenschaften Satz-Accessor fest.</span><span class="sxs-lookup"><span data-stu-id="30071-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="30071-129">Vervollständigen Sie die Definition `Method1` von, indem Sie den folgenden Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="30071-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="30071-130">So testen Sie die Implementierung der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30071-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="30071-131">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf das Start Formular für das Projekt, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="30071-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="30071-132">Im Editor wird die Klasse für das Start Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30071-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="30071-133">Standardmäßig wird das Start Formular aufgerufen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="30071-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="30071-134">Fügen Sie der `testInstance` - `Form1` Klasse das folgende Feld hinzu:</span><span class="sxs-lookup"><span data-stu-id="30071-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="30071-135">Durch `testInstance` deklarieren `WithEvents`von als `Form1` kann die-Klasse die-Ereignisse verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="30071-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="30071-136">Fügen Sie der- `Form1` Klasse den folgenden Ereignishandler hinzu, um von `testInstance`aufgebene Ereignisse zu behandeln:</span><span class="sxs-lookup"><span data-stu-id="30071-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="30071-137">Fügen Sie der `Form1` -Klasse `Test` eine Unterroutine mit dem Namen hinzu, um die Implementierungs Klasse zu testen:</span><span class="sxs-lookup"><span data-stu-id="30071-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="30071-138">Die `Test` Prozedur erstellt eine Instanz der-Klasse, die `MyInterface`implementiert, diese Instanz dem `testInstance` Feld zuweist, eine Eigenschaft festlegt und eine Methode über die-Schnittstelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="30071-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="30071-139">Fügen Sie Code hinzu, `Test` um die Prozedur `Form1 Load` aus der Prozedur Ihres Start Formulars aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="30071-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="30071-140">Führen Sie `Test` die Prozedur aus, indem Sie F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="30071-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="30071-141">Die Meldung "Eigenschaft PROP1 wurde auf 9 festgelegt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30071-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="30071-142">Nachdem Sie auf OK geklickt haben, wird die Meldung "der X-Parameter für Methode1 ist 5" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30071-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="30071-143">Klicken Sie auf OK, und die Meldung "der Ereignishandler hat das Ereignis abgefangen" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30071-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30071-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30071-144">See also</span></span>

- [<span data-ttu-id="30071-145">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30071-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="30071-146">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="30071-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="30071-147">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30071-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="30071-148">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30071-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
