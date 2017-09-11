---
title: "Deklarieren und Auslösen von Ereignissen (Visual Basic) | Microsoft-Dokumentation"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: eca112aca39bd998697d379a1705845e8f607367
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="4e092-102">Exemplarische Vorgehensweise: Deklarieren und Auslösen von Ereignissen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e092-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="4e092-103">Diese exemplarische Vorgehensweise veranschaulicht das Deklarieren und Auslösen von Ereignissen für eine Klasse mit dem Namen `Widget`.</span><span class="sxs-lookup"><span data-stu-id="4e092-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="4e092-104">Nachdem Sie die Schritte abgeschlossen haben, empfiehlt begleitthema, lesen [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), die zeigt, wie Ereignisse aus `Widget` Objekte zum Bereitstellen von Statusinformationen in einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e092-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="4e092-105">Die Widget-Klasse</span><span class="sxs-lookup"><span data-stu-id="4e092-105">The Widget Class</span></span>  
 <span data-ttu-id="4e092-106">Nehmen Sie für den Moment, die Sie an einer `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="4e092-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="4e092-107">Die `Widget` -Klasse verfügt über eine Methode, die zum Ausführen einer lange dauern kann, und Sie möchten die Anwendung einige Abschluss Indikator erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4e092-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="4e092-108">Natürlich, Sie können die `Widget` Objekt ein Statusanzeige-Dialogfeld anzeigen, jedoch hängen mit diesem Dialogfeld in jedem Projekt, in dem Sie verwendet, die `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="4e092-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="4e092-109">Verhaltensweise des Objektdesign stellt die Anwendung, die ein Objekthandle der Benutzeroberfläche verwendet, es sei denn, die gesamte des Objekts dient zum Verwalten von einem Formular oder das Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="4e092-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="4e092-110">Der Zweck der `Widget` werden weitere Aufgaben erledigen, daher ist es besser, Hinzufügen einer `PercentDone` Ereignis und die Prozedur, die aufgerufen `Widget`Methoden des behandelt werden, dass Ereignis und die Statusanzeige.</span><span class="sxs-lookup"><span data-stu-id="4e092-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="4e092-111">Die `PercentDone` -Ereignis kann auch einen Mechanismus zum Abbrechen der Aufgabe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e092-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="4e092-112">Das Codebeispiel in diesem Thema erstellen</span><span class="sxs-lookup"><span data-stu-id="4e092-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="4e092-113">Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows-Anwendung und erstellen Sie ein Formular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4e092-113">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="4e092-114">Fügen Sie zwei Schaltflächen und eine Bezeichnung, die `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4e092-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="4e092-115">Benennen Sie die Objekte, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4e092-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="4e092-116">Objekt</span><span class="sxs-lookup"><span data-stu-id="4e092-116">Object</span></span>|<span data-ttu-id="4e092-117">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4e092-117">Property</span></span>|<span data-ttu-id="4e092-118">Einstellung</span><span class="sxs-lookup"><span data-stu-id="4e092-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="4e092-119">Startaufgabe</span><span class="sxs-lookup"><span data-stu-id="4e092-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="4e092-120">Abbrechen</span><span class="sxs-lookup"><span data-stu-id="4e092-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="4e092-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="4e092-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="4e092-122">LblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="4e092-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="4e092-123">Auf der **Projekt** Menü wählen **Klasse hinzufügen** eine Klasse mit dem Namen `Widget.vb` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="4e092-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="4e092-124">Deklariert ein Ereignis für die Widget-Klasse</span><span class="sxs-lookup"><span data-stu-id="4e092-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="4e092-125">Verwenden der `Event` -Schlüsselwort zu deklarieren, ein Ereignis in der `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="4e092-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="4e092-126">Beachten Sie, dass ein Ereignis kann `ByVal` und `ByRef` Argumente als `Widget`des `PercentDone` Ereignis veranschaulicht wird:</span><span class="sxs-lookup"><span data-stu-id="4e092-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     <span data-ttu-id="4e092-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e092-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span></span>  
  
 <span data-ttu-id="4e092-128">Erhält das aufrufende Objekt ein `PercentDone` -Ereignis, das `Percent` -Argument enthält den Anteil der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4e092-128">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="4e092-129">Die `Cancel` Argument festgelegt werden kann, um `True` zum Abbrechen der Methode, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="4e092-129">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e092-130">Sie können Ereignisargumente deklarieren, wie Argumente von Prozeduren mit den folgenden Ausnahmen: Ereignisse dürfen keine `Optional` oder `ParamArray` -Argumente haben und keine Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4e092-130">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="4e092-131">Die `PercentDone` -Ereignis wird ausgelöst, indem die `LongTask` Methode der `Widget` Klasse.</span><span class="sxs-lookup"><span data-stu-id="4e092-131">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="4e092-132">`LongTask`akzeptiert zwei Argumente: die Zeitspanne zu arbeiten, und das minimale Zeitintervall vor dem Ausführen der Methode vorgegeben `LongTask` Pausen zum Auslösen der `PercentDone` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4e092-132">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="4e092-133">Zum Auslösen des Ereignisses PercentDone</span><span class="sxs-lookup"><span data-stu-id="4e092-133">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="4e092-134">Um Zugriff auf die `Timer` Eigenschaft, die von dieser Klasse verwendete hinzufügen ein `Imports` Anweisung am Anfang der Deklarationsabschnitt des Klassenmoduls, über die `Class Widget` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4e092-134">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     <span data-ttu-id="4e092-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e092-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span></span>  
  
2.  <span data-ttu-id="4e092-136">Fügen Sie der `Widget` -Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e092-136">Add the following code to the `Widget` class:</span></span>  
  
     <span data-ttu-id="4e092-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e092-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span></span>  
  
 <span data-ttu-id="4e092-138">Bei einem Aufruf der `LongTask` -Methode, die `Widget` -Klasse löst die `PercentDone` Ereignis jedes `MinimumInterval` Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4e092-138">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="4e092-139">Gibt das Ereignis `LongTask` überprüft, ob die `Cancel` Argument festgelegt wurde, um `True`.</span><span class="sxs-lookup"><span data-stu-id="4e092-139">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="4e092-140">Hier sind einige Haftungsausschlüsse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e092-140">A few disclaimers are necessary here.</span></span> <span data-ttu-id="4e092-141">Der Einfachheit halber die `LongTask` Verfahren wird vorausgesetzt, Sie wissen im voraus, wie lange der Vorgang dauert.</span><span class="sxs-lookup"><span data-stu-id="4e092-141">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="4e092-142">Dies ist fast nie der Fall.</span><span class="sxs-lookup"><span data-stu-id="4e092-142">This is almost never the case.</span></span> <span data-ttu-id="4e092-143">Unterteilen Aufgaben in Segmente gleicher Größe kann schwierig sein, und häufig an Benutzer verpassen wird einfach die Zeitspanne, die vergeht, bevor man ein Hinweis darauf, dass etwas geschieht.</span><span class="sxs-lookup"><span data-stu-id="4e092-143">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="4e092-144">Sie können einen anderen Fehler in diesem Beispiel erkannt haben.</span><span class="sxs-lookup"><span data-stu-id="4e092-144">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="4e092-145">Die `Timer` Eigenschaft gibt die Anzahl der seit Mitternacht vergangenen Sekunden zurück; aus diesem Grund bleibt die Anwendung hängen, wenn sie kurz vor Mitternacht gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4e092-145">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="4e092-146">Ein sorgfältiger Ansatz zum Messen der Zeit begrenzungsbedingungen wie diesem berücksichtigt werden würde, oder vermeiden Sie sie, wie mithilfe von Eigenschaften `Now`.</span><span class="sxs-lookup"><span data-stu-id="4e092-146">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="4e092-147">Nachdem die `Widget` -Klasse kann Ereignisse auslösen, können Sie in der nächsten exemplarischen Vorgehensweise verschieben.</span><span class="sxs-lookup"><span data-stu-id="4e092-147">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="4e092-148">[Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) veranschaulicht, wie `WithEvents` verknüpfen Sie einen Ereignishandler mit der `PercentDone` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4e092-148">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e092-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e092-149">See Also</span></span>  
 <span data-ttu-id="4e092-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span><span class="sxs-lookup"><span data-stu-id="4e092-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span></span>   
 <span data-ttu-id="4e092-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="4e092-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span></span>   
<span data-ttu-id="4e092-152"> [Exemplarische Vorgehensweise: Behandeln von Ereignissen](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span><span class="sxs-lookup"><span data-stu-id="4e092-152"> [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span></span>  
<span data-ttu-id="4e092-153"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="4e092-153"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
