---
title: Erstellen und Implementieren von Schnittstellen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322029"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="4dec8-102">Exemplarische Vorgehensweise: Erstellen und Implementieren von Schnittstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dec8-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="4dec8-103">Schnittstellen werden die Merkmale der Eigenschaften, Methoden und Ereignisse beschrieben, aber die Einzelheiten der Implementierung in Strukturen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="4dec8-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="4dec8-104">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie deklarieren und Implementieren einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4dec8-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dec8-105">In dieser exemplarischen Vorgehensweise stellt Informationen zum Erstellen einer Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="4dec8-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="4dec8-106">Um eine Schnittstelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4dec8-106">To define an interface</span></span>
  
1. <span data-ttu-id="4dec8-107">Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="4dec8-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="4dec8-108">Fügen Sie ein neues Modul für das Projekt, indem Sie auf **Modul hinzufügen** auf die **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="4dec8-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="4dec8-109">Nennen Sie das neue Modul `Module1.vb` , und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4dec8-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="4dec8-110">Der Code für das neue Modul wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dec8-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="4dec8-111">Definieren Sie eine Schnittstelle, die mit dem Namen `TestInterface` in `Module1` durch Eingabe `Interface TestInterface` zwischen der `Module` und `End Module` Anweisungen und dann die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="4dec8-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="4dec8-112">Die **Code-Editor** Einzüge der `Interface` Schlüsselwort und fügt eine `End Interface` Anweisung, um einen Codeblock zu bilden.</span><span class="sxs-lookup"><span data-stu-id="4dec8-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="4dec8-113">Definieren Sie eine Eigenschaft, Methode und Ereignis für die Schnittstelle, platzieren Sie den folgenden Code zwischen den `Interface` und `End Interface` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="4dec8-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="4dec8-114">Implementierung</span><span class="sxs-lookup"><span data-stu-id="4dec8-114">Implementation</span></span>

 <span data-ttu-id="4dec8-115">Sie können feststellen, dass die Syntax zum Deklarieren der Schnittstellenmember verwendet verschiedene, von der Syntax verwendet, um Klassenmember zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4dec8-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="4dec8-116">Dieser Unterschied gibt die Tatsache, dass Schnittstellen Implementierungscode enthalten können.</span><span class="sxs-lookup"><span data-stu-id="4dec8-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="4dec8-117">Implementieren die Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dec8-117">To implement the interface</span></span>
  
1. <span data-ttu-id="4dec8-118">Fügen Sie eine Klasse, die mit dem Namen `ImplementationClass` durch Hinzufügen der folgenden Anweisung auf `Module1`, nachdem die `End Interface` Anweisung aber vor der `End Module` -Anweisung und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4dec8-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="4dec8-119">Wenn Sie in der integrierten Entwicklungsumgebung, arbeiten die **Code-Editor** stellt ein entsprechendes `End Class` -Anweisung, wenn Sie die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="4dec8-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="4dec8-120">Fügen Sie die folgenden `Implements` Anweisung `ImplementationClass`, die Namen der Schnittstelle an, der Klasse implementiert:</span><span class="sxs-lookup"><span data-stu-id="4dec8-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="4dec8-121">Wenn separat von anderen Elementen am Anfang einer Klasse oder Struktur, steht die `Implements` Anweisung gibt an, dass die Klasse oder Struktur eine Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="4dec8-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="4dec8-122">Wenn Sie in der integrierten Entwicklungsumgebung, arbeiten die **Code-Editor** implementiert die erforderlichen Member `TestInterface` Wenn Sie die EINGABETASTE drücken, und Sie können den nächsten Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="4dec8-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="4dec8-123">Wenn Sie nicht innerhalb der integrierten Entwicklungsumgebung arbeiten, müssen Sie alle Member der Schnittstelle implementieren `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="4dec8-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="4dec8-124">Fügen Sie den folgenden Code `ImplementationClass` implementieren `Event1`, `Method1`, und `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="4dec8-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="4dec8-125">Die `Implements` Anweisung benennt die Schnittstelle und Schnittstellenmember implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="4dec8-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="4dec8-126">Führen Sie die Definition der `Prop1` durch Hinzufügen eines privaten Felds auf die Klasse, die den Wert der Eigenschaft gespeichert:</span><span class="sxs-lookup"><span data-stu-id="4dec8-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="4dec8-127">Der Rückgabewert von der `pval` aus der Eigenschaft get-Accessor.</span><span class="sxs-lookup"><span data-stu-id="4dec8-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="4dec8-128">Legen Sie den Wert der `pval` set-Accessor der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4dec8-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="4dec8-129">Führen Sie die Definition der `Method1` durch den folgenden Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4dec8-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="4dec8-130">So testen Sie die Implementierung der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dec8-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="4dec8-131">Mit der rechten Maustaste in des Startformulars für Ihr Projekt in der **Projektmappen-Explorer**, und klicken Sie auf **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="4dec8-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="4dec8-132">Der Editor zeigt die Klasse des Startformulars.</span><span class="sxs-lookup"><span data-stu-id="4dec8-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="4dec8-133">Standardmäßig heißt das Startformular `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4dec8-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="4dec8-134">Fügen Sie die folgenden `testInstance` Feld der `Form1` Klasse:</span><span class="sxs-lookup"><span data-stu-id="4dec8-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="4dec8-135">Durch Deklarieren `testInstance` als `WithEvents`, `Form1` Klasse die Ereignisse behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="4dec8-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="4dec8-136">Fügen Sie den folgenden Ereignishandler, um die `Form1` -Klasse, von ausgelösten Ereignisse behandeln `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="4dec8-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="4dec8-137">Fügen Sie eine Unterroutine namens `Test` auf die `Form1` Klasse, um die Implementierungsklasse zu testen:</span><span class="sxs-lookup"><span data-stu-id="4dec8-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="4dec8-138">Die `Test` Prozedur erstellt eine Instanz der Klasse, die implementiert `MyInterface`, weist diese Instanz die `testInstance` Feld legt eine Eigenschaft fest, und führt eine Methode über die Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4dec8-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="4dec8-139">Fügen Sie Code zum Aufrufen der `Test` Prozedur aus der `Form1 Load` Verfahren des Startformulars:</span><span class="sxs-lookup"><span data-stu-id="4dec8-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="4dec8-140">Führen Sie die `Test` Prozedur durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="4dec8-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="4dec8-141">Die Meldung "Prop1 set bis 9" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dec8-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="4dec8-142">Nachdem Sie OK, der Nachricht klicken Sie auf "Parameters" X "für Method1 ist 5" werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dec8-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="4dec8-143">Klicken Sie auf OK, und die Meldung "der Ereignishandler das Ereignis erkannt" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4dec8-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dec8-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dec8-144">See also</span></span>

- [<span data-ttu-id="4dec8-145">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4dec8-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="4dec8-146">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4dec8-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="4dec8-147">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4dec8-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="4dec8-148">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4dec8-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
