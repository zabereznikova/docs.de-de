---
title: Definieren von Klassen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec002e1709fa5fe31dfe7744fb91a230c32337a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="dd25a-102">Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd25a-102">Walkthrough: Defining Classes (Visual Basic)</span></span>
<span data-ttu-id="dd25a-103">Diese exemplarische Vorgehensweise veranschaulicht das Definieren von Klassen, die Sie dann zum Erstellen von Objekten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="dd25a-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="dd25a-104">Außerdem wird gezeigt, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und veranschaulicht, wie ein Objekt initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="dd25a-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-a-class"></a><span data-ttu-id="dd25a-105">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="dd25a-105">To define a class</span></span>  
  
1.  <span data-ttu-id="dd25a-106">Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf die **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="dd25a-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="dd25a-107">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd25a-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="dd25a-108">Wählen Sie aus der Liste der Windows-Anwendung [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Projektvorlagen, um das neue Projekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd25a-108">Select Windows Application from the list of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="dd25a-109">Fügen Sie eine neue Klasse für das Projekt, indem Sie auf **Klasse hinzufügen** auf die **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="dd25a-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="dd25a-110">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd25a-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="dd25a-111">Wählen Sie die **Klasse** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="dd25a-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="dd25a-112">Benennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd25a-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="dd25a-113">Können Sie die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **Code-Editor** hinzufügen eine Klasse zu Ihrem Startformular durch Eingabe der `Class` Schlüsselwort, gefolgt von den Namen der neuen Klasse.</span><span class="sxs-lookup"><span data-stu-id="dd25a-113">You can use the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="dd25a-114">Die **Code-Editor** bietet ein entsprechendes `End Class` -Anweisung für Sie.</span><span class="sxs-lookup"><span data-stu-id="dd25a-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="dd25a-115">Definieren Sie ein privates Feld für die Klasse durch Hinzufügen von den folgenden Code zwischen den `Class` und `End Class` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="dd25a-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     <span data-ttu-id="dd25a-116">Deklarieren das Feld als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd25a-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="dd25a-117">Können Sie Felder verfügbar machen von außerhalb einer Klasse mit Zugriffsmodifizierern wie z. B. `Public` , umfassenderen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dd25a-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="dd25a-118">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="dd25a-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="dd25a-119">Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="dd25a-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  <span data-ttu-id="dd25a-120">Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="dd25a-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. <span data-ttu-id="dd25a-121">Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, indem Sie eine Prozedur mit dem Namen hinzufügen `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="dd25a-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     <span data-ttu-id="dd25a-122">Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dd25a-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="dd25a-123">Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="dd25a-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
### <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="dd25a-124">So erstellen eine Schaltfläche, um die Klasse zu testen</span><span class="sxs-lookup"><span data-stu-id="dd25a-124">To create a button to test the class</span></span>  
  
1.  <span data-ttu-id="dd25a-125">Ändern der Startformular in den Entwurfsmodus durch Rechtsklicken auf seinen Namen im **Projektmappen-Explorer** und dann auf **Sicht-Designer**.</span><span class="sxs-lookup"><span data-stu-id="dd25a-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="dd25a-126">Standardmäßig heißt die Startformular für Windows-Anwendungsprojekten "Form1.vb".</span><span class="sxs-lookup"><span data-stu-id="dd25a-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="dd25a-127">Das Hauptformular wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd25a-127">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="dd25a-128">Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für die Anzeige der `Button1_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="dd25a-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="dd25a-129">Fügen Sie den folgenden Code zum Aufrufen der Testprozedur hinzu:</span><span class="sxs-lookup"><span data-stu-id="dd25a-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a><span data-ttu-id="dd25a-130">So führen Sie Ihre Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="dd25a-130">To run your application</span></span>  
  
1.  <span data-ttu-id="dd25a-131">Drücken Sie F5, um führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="dd25a-131">Run your application by pressing F5.</span></span> <span data-ttu-id="dd25a-132">Klicken Sie auf die Schaltfläche im Formular an die Testprozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dd25a-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="dd25a-133">Zeigt einer Meldung, die besagt, dass die ursprüngliche `UserName` ist "MOORE, BOBBY", da Prozeduraufruf der `Capitalize` -Methode des Objekts.</span><span class="sxs-lookup"><span data-stu-id="dd25a-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="dd25a-134">Klicken Sie auf **OK** auf das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dd25a-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="dd25a-135">Die `Button1 Click` Prozedur ändert den Wert für die `UserName` Eigenschaft und zeigt eine Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.</span><span class="sxs-lookup"><span data-stu-id="dd25a-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd25a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd25a-136">See Also</span></span>  
 [<span data-ttu-id="dd25a-137">Objektorientierte Programmierung</span><span class="sxs-lookup"><span data-stu-id="dd25a-137">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)  
 [<span data-ttu-id="dd25a-138">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="dd25a-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
