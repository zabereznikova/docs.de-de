---
title: Deklarieren und Auslösen von Ereignissen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320690"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="64ea6-102">Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64ea6-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="64ea6-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie für das Deklarieren und Auslösen von Ereignissen für eine Klasse, die mit dem Namen `Widget`.</span><span class="sxs-lookup"><span data-stu-id="64ea6-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="64ea6-104">Nachdem Sie die Schritte abgeschlossen haben, Sie möchten das begleitthema lesen [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), erfahren, wie Sie Ereignisse aus `Widget` Objekte Statusinformationen in einer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="64ea6-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="64ea6-105">Die Widget-Klasse</span><span class="sxs-lookup"><span data-stu-id="64ea6-105">The Widget Class</span></span>  
 <span data-ttu-id="64ea6-106">Davon aus, die Sie derzeit eine `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="64ea6-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="64ea6-107">Ihre `Widget` -Klasse verfügt über eine Methode, die eine lange Ausführungszeit benötigt erreichen, und Sie möchten die Anwendung, um eine Art des Indikators für Abschluss erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="64ea6-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="64ea6-108">Natürlich könnten Sie machen die `Widget` Objekt anzuzeigen, ein Dialogfeld Fortschritt in Prozent, aber dann deklarieren Sie mit diesem Dialogfeld in jedem Projekt, in dem Sie verwendet, die `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="64ea6-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="64ea6-109">Ein gutes Prinzip des objektentwurfs besteht darin, die Anwendung, das ein Objekthandle der Benutzeroberfläche verwendet, es sei denn, die gesamte des Objekts dient zum Verwalten eines Felds zum Formular oder Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="64ea6-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="64ea6-110">Der Zweck der `Widget` besteht darin, andere Aufgaben auszuführen, daher ist es besser, hinzuzufügen, eine `PercentDone` Ereignis und die Prozedur verwendet, die aufruft `Widget`Methoden der behandelt werden, dass Ereignis und die Statusanzeige.</span><span class="sxs-lookup"><span data-stu-id="64ea6-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="64ea6-111">Die `PercentDone` Ereignis bieten auch einen Mechanismus zum Abbrechen der Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="64ea6-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="64ea6-112">Das Codebeispiel in diesem Thema erstellen</span><span class="sxs-lookup"><span data-stu-id="64ea6-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="64ea6-113">Öffnen Sie ein neues Visual Basic Windows-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="64ea6-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="64ea6-114">Fügen Sie zwei Schaltflächen und eine Bezeichnung für die `Form1`.</span><span class="sxs-lookup"><span data-stu-id="64ea6-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="64ea6-115">Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64ea6-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="64ea6-116">Objekt</span><span class="sxs-lookup"><span data-stu-id="64ea6-116">Object</span></span>|<span data-ttu-id="64ea6-117">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="64ea6-117">Property</span></span>|<span data-ttu-id="64ea6-118">Einstellung</span><span class="sxs-lookup"><span data-stu-id="64ea6-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="64ea6-119">Startaufgabe</span><span class="sxs-lookup"><span data-stu-id="64ea6-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="64ea6-120">Abbrechen</span><span class="sxs-lookup"><span data-stu-id="64ea6-120">Cancel</span></span>|  
    |`Label`|`(Name)`<span data-ttu-id="64ea6-121">,</span><span class="sxs-lookup"><span data-stu-id="64ea6-121">,</span></span> `Text`|<span data-ttu-id="64ea6-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="64ea6-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="64ea6-123">Auf der **Projekt** Menü wählen **Klasse hinzufügen** zum Hinzufügen der Klasse `Widget.vb` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="64ea6-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="64ea6-124">Um ein Ereignis für das Widget-Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="64ea6-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="64ea6-125">Verwenden der `Event` -Schlüsselwort zu deklarieren, ein Ereignis in der `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="64ea6-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="64ea6-126">Beachten Sie, dass ein Ereignis kann `ByVal` und `ByRef` Argumente als `Widget`des `PercentDone` Ereignis veranschaulicht wird:</span><span class="sxs-lookup"><span data-stu-id="64ea6-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="64ea6-127">Wenn das aufrufende Objekt empfängt ein `PercentDone` -Ereignis, das `Percent` Argument enthält den Prozentsatz der der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="64ea6-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="64ea6-128">Die `Cancel` Argument kann festgelegt werden, um `True` zum Abbrechen der Methode, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="64ea6-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64ea6-129">Sie können Ereignisargumente deklarieren, wie von Prozeduren mit den folgenden Ausnahmen Argumente: Ereignisse dürfen keine `Optional` oder `ParamArray` Argumente und Ereignisse haben keine Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="64ea6-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="64ea6-130">Die `PercentDone` Ereignis wird ausgelöst, durch die `LongTask` Methode der `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="64ea6-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> `LongTask` <span data-ttu-id="64ea6-131">akzeptiert zwei Argumente: die Zeitdauer zu arbeiten, und das minimale Zeitintervall vor dem Ausführen der Methode vorgegeben `LongTask` angehalten wird, um das Auslösen der `PercentDone` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="64ea6-131">takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="64ea6-132">Zum Auslösen des Ereignisses PercentDone</span><span class="sxs-lookup"><span data-stu-id="64ea6-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="64ea6-133">Zur Vereinfachung der Zugriff auf die `Timer` hinzufügen Eigenschaft, die von dieser Klasse verwendet eine `Imports` Anweisung am Anfang des Abschnitts Deklarationen Klassenmoduls über die `Class Widget` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="64ea6-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="64ea6-134">Fügen Sie der `Widget`-Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="64ea6-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="64ea6-135">Bei einem Aufruf der `LongTask` -Methode, die `Widget` löst die `PercentDone` Ereignis jedes `MinimumInterval` Sekunden.</span><span class="sxs-lookup"><span data-stu-id="64ea6-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="64ea6-136">Gibt das Ereignis `LongTask` überprüft, ob die `Cancel` -Argument wurde auf festgelegt `True`.</span><span class="sxs-lookup"><span data-stu-id="64ea6-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="64ea6-137">Hier sind einige Haftungsausschlüsse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64ea6-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="64ea6-138">Der Einfachheit halber die `LongTask` Verfahren wird vorausgesetzt, Sie wissen im voraus, wie lange der Vorgang dauert.</span><span class="sxs-lookup"><span data-stu-id="64ea6-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="64ea6-139">Dies ist fast nie der Fall.</span><span class="sxs-lookup"><span data-stu-id="64ea6-139">This is almost never the case.</span></span> <span data-ttu-id="64ea6-140">Unterteilen Aufgaben in Blöcke von gleichmäßiger Größe kann schwierig sein, und häufig was für Benutzer am wichtigsten ist einfach die Zeitspanne, die übergeben werden, bevor sie eine Angabe über das erhalten, dass etwas passiert ist.</span><span class="sxs-lookup"><span data-stu-id="64ea6-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="64ea6-141">Sie können in diesem Beispiel ein weiterer Nachteil entdeckt haben.</span><span class="sxs-lookup"><span data-stu-id="64ea6-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="64ea6-142">Die `Timer` Eigenschaft gibt die Anzahl der Sekunden an, die seit Mitternacht vergangenen; die Anwendung ruft daher hängen, wenn sie kurz vor Mitternacht gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="64ea6-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="64ea6-143">Ein sorgfältiger Ansatz zum Messen der Zeit begrenzungsbedingungen wie diese berücksichtigt werden würde, oder vermeiden Sie sie, wie z. B. mithilfe von Eigenschaften `Now`.</span><span class="sxs-lookup"><span data-stu-id="64ea6-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="64ea6-144">Nachdem die `Widget` Klasse Ereignisse auslösen kann, können Sie in der nächsten exemplarischen Vorgehensweise verschieben.</span><span class="sxs-lookup"><span data-stu-id="64ea6-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="64ea6-145">[Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` , ordnen Sie einen Ereignishandler mit dem `PercentDone` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="64ea6-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ea6-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64ea6-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="64ea6-147">Exemplarische Vorgehensweise: Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="64ea6-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="64ea6-148">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="64ea6-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
