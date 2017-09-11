---
title: Definieren von Klassen (Visual Basic) | Microsoft-Dokumentation
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
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
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
ms.openlocfilehash: 5b470b8ba9b60dfb1cd1bbb207e02217f5311c27
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="bdb3b-102">Exemplarische Vorgehensweise: Definieren von Klassen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdb3b-102">Walkthrough: Defining Classes (Visual Basic)</span></span>
<span data-ttu-id="bdb3b-103">Diese exemplarische Vorgehensweise veranschaulicht das Definieren von Klassen, die Sie verwenden können, um Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="bdb3b-104">Außerdem erfahren Sie, wie die neue Klasse Eigenschaften und Methoden hinzugefügt, und veranschaulicht, wie ein Objekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a><span data-ttu-id="bdb3b-105">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="bdb3b-105">To define a class</span></span>  
  
1.  <span data-ttu-id="bdb3b-106">Erstellen Sie ein Projekt, indem Sie auf **neues Projekt** auf der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="bdb3b-107">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="bdb3b-108">Wählen Sie aus der Liste der Windows-Anwendung [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Projektvorlagen, um das neue Projekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-108">Select Windows Application from the list of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="bdb3b-109">Fügen Sie eine neue Klasse zum Projekt, indem Sie auf **Klasse hinzufügen** auf der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="bdb3b-110">Die **neues Element hinzufügen** das Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="bdb3b-111">Wählen Sie die **Klasse** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="bdb3b-112">Nennen Sie die neue Klasse `UserNameInfo.vb`, und klicken Sie dann auf **hinzufügen** um den Code für die neue Klasse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     <span data-ttu-id="bdb3b-113">[!code-vb[VbVbalrOOP&5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-113">[!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdb3b-114">Können Sie die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code-Editor** so dem Startformular eine Klasse hinzu, durch Eingabe der `Class` -Schlüsselwort, gefolgt vom Namen der neuen Klasse.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-114">You can use the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="bdb3b-115">Die **Code-Editor** bietet eine entsprechende `End Class` -Anweisung für Sie.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="bdb3b-116">Definieren Sie ein privates Feld für die Klasse, indem Sie den folgenden Code zwischen die `Class` und `End Class` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="bdb3b-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     <span data-ttu-id="bdb3b-117">[!code-vb[VbVbalrOOP&#7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-117">[!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span></span>  
  
     <span data-ttu-id="bdb3b-118">Deklaration des Felds als `Private` bedeutet, dass es nur innerhalb der Klasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-118">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="bdb3b-119">Sie können Felder mit verfügbar machen von außerhalb einer Klasse Zugriffsmodifizierer `Public` , die mehr Zugriff bieten.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-119">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="bdb3b-120">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3b-120">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="bdb3b-121">Definieren Sie eine Eigenschaft für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bdb3b-121">Define a property for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="bdb3b-122">[!code-vb[VbVbalrOOP&#8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-122">[!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span></span>  
  
8.  <span data-ttu-id="bdb3b-123">Definieren Sie eine Methode für die Klasse, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bdb3b-123">Define a method for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="bdb3b-124">[!code-vb[VbVbalrOOP&#9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-124">[!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span></span>  
  
9. <span data-ttu-id="bdb3b-125">Definieren Sie einen parametrisierten Konstruktor für die neue Klasse durch Hinzufügen einer Prozedur namens `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="bdb3b-125">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     <span data-ttu-id="bdb3b-126">[!code-vb[VbVbalrOOP&#10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-126">[!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span></span>  
  
     <span data-ttu-id="bdb3b-127">Die `Sub New` Konstruktor wird automatisch aufgerufen, wenn ein Objekt auf Grundlage dieser Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-127">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="bdb3b-128">Dieser Konstruktor legt den Wert des Felds, das den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-128">This constructor sets the value of the field that holds the user name.</span></span>  
  
### <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="bdb3b-129">Zum Erstellen einer Schaltfläche, um die Klasse zu testen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-129">To create a button to test the class</span></span>  
  
1.  <span data-ttu-id="bdb3b-130">Ändern des Startformulars in den Entwurfsmodus per Rechtsklick auf seinen Namen im **Projektmappen-Explorer** , und klicken Sie dann auf **Ansicht-Designer**.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-130">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="bdb3b-131">Standardmäßig ist das Startformular für Windows-Anwendungsprojekte Form1.vb benannt.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-131">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="bdb3b-132">Das Hauptformular wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-132">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="bdb3b-133">Das Hauptformular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um den Code anzuzeigen der `Button1_Click` -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-133">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="bdb3b-134">Fügen Sie den folgenden Code zum Aufrufen der Testprozedur:</span><span class="sxs-lookup"><span data-stu-id="bdb3b-134">Add the following code to call the test procedure:</span></span>  
  
     <span data-ttu-id="bdb3b-135">[!code-vb[VbVbalrOOP&#12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdb3b-135">[!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span></span>  
  
### <a name="to-run-your-application"></a><span data-ttu-id="bdb3b-136">So führen Sie Ihre Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="bdb3b-136">To run your application</span></span>  
  
1.  <span data-ttu-id="bdb3b-137">Führen Sie die Anwendung durch Drücken von F5.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-137">Run your application by pressing F5.</span></span> <span data-ttu-id="bdb3b-138">Klicken Sie auf die Schaltfläche im Formular an die Testprozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-138">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="bdb3b-139">Es wird eine Meldung, die besagt, dass die ursprüngliche `UserName` "MOORE, BOBBY" ist, da die Prozedur aufgerufen der `Capitalize` -Methode des Objekts.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-139">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="bdb3b-140">Klicken Sie auf **OK** um das Meldungsfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-140">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="bdb3b-141">Die `Button1 Click` Prozedur ändert den Wert der `UserName` -Eigenschaft und zeigt eine Meldung, die besagt, dass den neuen Wert des `UserName` "Worden, Joe" ist.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-141">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb3b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdb3b-142">See Also</span></span>  
 <span data-ttu-id="bdb3b-143">[Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span><span class="sxs-lookup"><span data-stu-id="bdb3b-143">[Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span></span>  
<span data-ttu-id="bdb3b-144"> [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="bdb3b-144"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>

