---
title: Deklarieren und Auslösen von Ereignissen
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 07ef611b50cfa13f77fa168d58dd3b43e97eeec6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057987"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="b6504-102">Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6504-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>

<span data-ttu-id="b6504-103">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie Ereignisse für eine Klasse mit dem Namen deklarieren und Auswerfen `Widget` .</span><span class="sxs-lookup"><span data-stu-id="b6504-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="b6504-104">Nachdem Sie die Schritte ausgeführt haben, können Sie das Begleit Thema Exemplarische Vorgehensweise [: Behandeln von Ereignissen](walkthrough-handling-events.md)lesen, in dem gezeigt wird, wie Ereignisse aus Objekten verwendet werden, `Widget` um Statusinformationen in einer Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b6504-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="b6504-105">Die widgeklasse</span><span class="sxs-lookup"><span data-stu-id="b6504-105">The Widget Class</span></span>  

 <span data-ttu-id="b6504-106">Angenommen, Sie haben eine- `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="b6504-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="b6504-107">Die `Widget` -Klasse verfügt über eine-Methode, die für die Ausführung viel Zeit in Anspruch nehmen kann, und Sie möchten, dass Ihre Anwendung in der Lage ist, einen beliebigen Abschluss Indikator zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6504-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="b6504-108">Natürlich könnten Sie das `Widget` Objekt mit dem Dialogfeld "Prozentsatz vervollständigen" anzeigen lassen, aber dann würden Sie in jedem Projekt, in dem Sie die Klasse verwendet haben, an diesem Dialogfeld hängen bleiben `Widget` .</span><span class="sxs-lookup"><span data-stu-id="b6504-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="b6504-109">Ein gutes Prinzip des Objekt Entwurfs besteht darin, dass die Anwendung, die ein Objekt verwendet, die Benutzeroberfläche verarbeitet – es sei denn, der gesamte Zweck des Objekts besteht darin, ein Formular oder Dialogfeld zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b6504-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="b6504-110">Der Zweck von `Widget` ist das Ausführen weiterer Aufgaben, daher ist es besser, ein `PercentDone` -Ereignis hinzuzufügen und die Prozedur, die Methoden aufruft, `Widget` Dieses Ereignis zu behandeln und Statusaktualisierungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b6504-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="b6504-111">Das `PercentDone` Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b6504-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="b6504-112">So erstellen Sie das Codebeispiel für dieses Thema</span><span class="sxs-lookup"><span data-stu-id="b6504-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="b6504-113">Öffnen Sie ein neues Visual Basic Windows-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1` .</span><span class="sxs-lookup"><span data-stu-id="b6504-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="b6504-114">Fügen Sie zwei Schaltflächen und eine Bezeichnung hinzu `Form1` .</span><span class="sxs-lookup"><span data-stu-id="b6504-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="b6504-115">Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6504-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b6504-116">Object</span><span class="sxs-lookup"><span data-stu-id="b6504-116">Object</span></span>|<span data-ttu-id="b6504-117">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b6504-117">Property</span></span>|<span data-ttu-id="b6504-118">Einstellung</span><span class="sxs-lookup"><span data-stu-id="b6504-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="b6504-119">Startaufgabe</span><span class="sxs-lookup"><span data-stu-id="b6504-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="b6504-120">Abbrechen</span><span class="sxs-lookup"><span data-stu-id="b6504-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="b6504-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b6504-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="b6504-122">lblprozentudone, 0</span><span class="sxs-lookup"><span data-stu-id="b6504-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="b6504-123">Wählen Sie im Menü **Projekt** die Option **Klasse hinzufügen** aus, um `Widget.vb` dem Projekt eine Klasse mit dem Namen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b6504-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="b6504-124">So deklarieren Sie ein Ereignis für die Widget-Klasse</span><span class="sxs-lookup"><span data-stu-id="b6504-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="b6504-125">Verwenden Sie das- `Event` Schlüsselwort zum Deklarieren eines Ereignisses in der- `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="b6504-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="b6504-126">Beachten Sie, dass ein Ereignis über `ByVal` -und `ByRef` -Argumente verfügen kann, wie `Widget` das- `PercentDone` Ereignis veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b6504-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="b6504-127">Wenn das aufrufenden Objekt ein- `PercentDone` Ereignis empfängt, enthält das- `Percent` Argument den Prozentsatz der abgeschlossenen Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="b6504-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="b6504-128">Das- `Cancel` Argument kann auf festgelegt werden, `True` um die Methode abzubrechen, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b6504-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6504-129">Sie können Ereignis Argumente genau wie Argumente von Prozeduren deklarieren, mit den folgenden Ausnahmen: Ereignisse können `Optional` keine `ParamArray` -oder-Argumente aufweisen, und Ereignisse haben keine Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="b6504-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="b6504-130">Das- `PercentDone` Ereignis wird von der- `LongTask` Methode der-Klasse ausgelöst `Widget` .</span><span class="sxs-lookup"><span data-stu-id="b6504-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="b6504-131">`LongTask` erfordert zwei Argumente: die Zeitdauer, die die Methode vor dem Ausführen der Arbeit vornimmt, und das minimale Zeitintervall vor dem Anhalten, `LongTask` um das Ereignis zu erhöhen `PercentDone` .</span><span class="sxs-lookup"><span data-stu-id="b6504-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="b6504-132">So heben Sie das Ereignis "" vom</span><span class="sxs-lookup"><span data-stu-id="b6504-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="b6504-133">Wenn Sie den Zugriff auf die `Timer` von dieser Klasse verwendete Eigenschaft vereinfachen möchten, fügen Sie eine- `Imports` Anweisung oberhalb der-Anweisung am Anfang des Deklarations Abschnitts des Klassen Moduls hinzu `Class Widget` .</span><span class="sxs-lookup"><span data-stu-id="b6504-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="b6504-134">Fügen Sie der `Widget`-Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b6504-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="b6504-135">Wenn die Anwendung die- `LongTask` Methode aufruft, löst die- `Widget` Klasse das- `PercentDone` Ereignis alle `MinimumInterval` Sekunden aus.</span><span class="sxs-lookup"><span data-stu-id="b6504-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="b6504-136">Wenn das Ereignis zurückgibt, `LongTask` prüft, ob das- `Cancel` Argument auf festgelegt wurde `True` .</span><span class="sxs-lookup"><span data-stu-id="b6504-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="b6504-137">Hier sind einige Haftungsausschlüsse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6504-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="b6504-138">Der Einfachheit halber wird `LongTask` bei der Vorgehensweise davon ausgegangen, dass Sie im Voraus wissen, wie lange die Aufgabe dauert.</span><span class="sxs-lookup"><span data-stu-id="b6504-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="b6504-139">Dies ist fast nie der Fall.</span><span class="sxs-lookup"><span data-stu-id="b6504-139">This is almost never the case.</span></span> <span data-ttu-id="b6504-140">Das Aufteilen von Aufgaben in Blöcke mit gleichmäßiger Größe kann schwierig sein, und häufig ist das, was für Benutzer am wichtigsten ist, einfach die Zeitspanne, die verstrichen ist, bevor Sie einen Hinweis darauf erhalten, dass etwas passiert.</span><span class="sxs-lookup"><span data-stu-id="b6504-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="b6504-141">Möglicherweise haben Sie in diesem Beispiel einen weiteren Fehler erkannt.</span><span class="sxs-lookup"><span data-stu-id="b6504-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="b6504-142">Die- `Timer` Eigenschaft gibt die Anzahl der Sekunden zurück, die seit Mitternacht vergangen sind. Daher bleibt die Anwendung hängen, wenn Sie unmittelbar vor Mitternacht gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b6504-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="b6504-143">Ein sorgfältiger Ansatz zum Messen der Zeit würde Grenzbedingungen wie diese berücksichtigen oder die Verwendung von Eigenschaften wie z `Now` . b. vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b6504-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="b6504-144">Nachdem die `Widget` Klasse nun Ereignisse aufhebt, können Sie mit der nächsten exemplarischen Vorgehensweise fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b6504-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="b6504-145">Exemplarische Vorgehensweise [: Behandeln von Ereignissen](walkthrough-handling-events.md) veranschaulicht, wie verwendet wird, `WithEvents` um dem-Ereignis einen Ereignishandler zuzuordnen `PercentDone` .</span><span class="sxs-lookup"><span data-stu-id="b6504-145">[Walkthrough: Handling Events](walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6504-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6504-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="b6504-147">Exemplarische Vorgehensweise: Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b6504-147">Walkthrough: Handling Events</span></span>](walkthrough-handling-events.md)
- [<span data-ttu-id="b6504-148">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b6504-148">Events</span></span>](index.md)
