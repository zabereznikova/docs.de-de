---
title: Definieren von Klassen
ms.date: 07/20/2015
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
ms.openlocfilehash: 646c6ce307131f3edba194af19920eade9c1753c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389113"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="2e3f6-102">Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e3f6-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="2e3f6-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Klassen definiert werden, die Sie dann zum Erstellen von-Objekten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="2e3f6-104">Außerdem wird gezeigt, wie Sie der neuen Klasse Eigenschaften und Methoden hinzufügen und wie ein Objekt initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="2e3f6-105">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="2e3f6-105">To define a class</span></span>
  
1. <span data-ttu-id="2e3f6-106">Erstellen Sie ein Projekt, indem Sie im Menü **Datei** auf **Neues Projekt** klicken.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="2e3f6-107">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="2e3f6-108">Wählen Sie in der Liste der Visual Basic Projektvorlagen die Option Windows-Anwendung aus, um das neue Projekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="2e3f6-109">Fügen Sie dem Projekt eine neue Klasse hinzu, indem Sie im Menü **Projekt** auf **Klasse hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="2e3f6-110">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="2e3f6-111">Wählen Sie die **Klassen** Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="2e3f6-112">Benennen Sie die neue Klasse `UserNameInfo.vb` , und klicken Sie dann auf **Hinzufügen** , um den Code für die neue Klasse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="2e3f6-113">Sie können den Visual Basic **Code-Editor** verwenden, um dem Start Formular eine Klasse hinzuzufügen, indem Sie das `Class` Schlüsselwort gefolgt vom Namen der neuen Klasse eingeben.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="2e3f6-114">Der **Code-Editor** stellt eine entsprechende- `End Class` Anweisung für Sie bereit.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="2e3f6-115">Definieren Sie ein privates Feld für die-Klasse, indem Sie den folgenden Code zwischen den `Class` -und-Anweisungen hinzufügen `End Class` :</span><span class="sxs-lookup"><span data-stu-id="2e3f6-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="2e3f6-116">Das Deklarieren des Felds `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="2e3f6-117">Sie können Felder außerhalb einer Klasse verfügbar machen, indem Sie Zugriffsmodifizierer wie verwenden `Public` , die mehr Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="2e3f6-118">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e3f6-118">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="2e3f6-119">Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2e3f6-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="2e3f6-120">Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2e3f6-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="2e3f6-121">Definieren Sie einen parametrisierten Konstruktor für die neue Klasse, indem Sie eine Prozedur mit dem Namen hinzufügen `Sub New` :</span><span class="sxs-lookup"><span data-stu-id="2e3f6-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="2e3f6-122">Der `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt erstellt wird, das auf dieser Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="2e3f6-123">Dieser Konstruktor legt den Wert des Felds fest, das den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="2e3f6-124">So erstellen Sie eine Schaltfläche zum Testen der Klasse</span><span class="sxs-lookup"><span data-stu-id="2e3f6-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="2e3f6-125">Ändern Sie das Start Formular in den Entwurfs Modus, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Namen klicken und dann **auf Designer anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="2e3f6-126">Standardmäßig hat das Start Formular für Windows-Anwendungsprojekte den Namen Form1. vb.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="2e3f6-127">Das Hauptformular wird dann angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="2e3f6-128">Fügen Sie dem Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code für den `Button1_Click` Ereignishandler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="2e3f6-129">Fügen Sie den folgenden Code hinzu, um die Testprozedur aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="2e3f6-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="2e3f6-130">So führen Sie Ihre Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="2e3f6-130">To run your application</span></span>
  
1. <span data-ttu-id="2e3f6-131">Führen Sie die Anwendung aus, indem Sie F5 drücken.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-131">Run your application by pressing F5.</span></span> <span data-ttu-id="2e3f6-132">Klicken Sie auf die Schaltfläche im Formular, um die Testprozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="2e3f6-133">Es wird eine Meldung angezeigt, die besagt, dass das Original `UserName` "Moore, Bobby" ist, weil die Prozedur die- `Capitalize` Methode des-Objekts aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="2e3f6-134">Klicken Sie auf **OK**, um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="2e3f6-135">Die `Button1 Click` Prozedur ändert den Wert der `UserName` -Eigenschaft und zeigt eine Meldung an, die besagt, dass der neue Wert von `UserName` "hat, Joe" lautet.</span><span class="sxs-lookup"><span data-stu-id="2e3f6-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3f6-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e3f6-136">See also</span></span>

- [<span data-ttu-id="2e3f6-137">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e3f6-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="2e3f6-138">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="2e3f6-138">Objects and Classes</span></span>](index.md)
