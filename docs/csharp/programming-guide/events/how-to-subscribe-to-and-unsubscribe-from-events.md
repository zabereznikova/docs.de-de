---
title: "Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5555cc8913bff953601c54aa7430143dc22173c0
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="aba49-102">Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="aba49-102">How to: Subscribe to and Unsubscribe from Events (C# Programming Guide)</span></span>
<span data-ttu-id="aba49-103">Wenn Sie benutzerdefinierten Code schreiben möchten, der aufgerufen wird, wenn dieses Ereignis ausgelöst wird, können Sie ein Ereignis abonnieren, das von einer anderen Klasse veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="aba49-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="aba49-104">Sie können z.B. das `click`-Ereignis einer Schaltfläche abonnieren, damit Ihre Anwendung etwas nützliches macht, wenn ein Benutzer auf die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="aba49-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="aba49-105">So abonnieren Sie Ereignisse mit der Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="aba49-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="aba49-106">Wenn Sie in der Ansicht **Entwurf** das Fenster **Eigenschaften** nicht sehen können, klicken Sie mit der rechten Maustaste auf das Formular oder das Kontrollelement, für das Sie einen Ereignishandler erstellen möchten, und wählen Sie anschließen **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="aba49-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="aba49-107">Klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="aba49-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3.  <span data-ttu-id="aba49-108">Doppelklicken Sie auf das Ereignis, das Sie erstellen möchten, z.B. das `Load`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="aba49-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     [!INCLUDE[csprcs](~/includes/csprcs-md.md)]<span data-ttu-id="aba49-109"> erstellt eine leere Ereignishandlermethode, und fügt diese in den Code ein.</span><span class="sxs-lookup"><span data-stu-id="aba49-109"> creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="aba49-110">Alternativ können Sie den Code auch manuell in der **Codeansicht** einfügen.</span><span class="sxs-lookup"><span data-stu-id="aba49-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="aba49-111">Die folgenden Codezeilen deklarieren beispielsweise eine Eventhandlermethode, die aufgerufen wird, wenn die Klasse `Form` das `Load`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="aba49-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-subscribe-to-and-unsubscribe-from-events_1.cs)]  
  
     <span data-ttu-id="aba49-112">Die Codezeile, die für das Abonnement des Ereignisses erforderlich ist, wird auch automatisch in der `InitializeComponent`-Methode in der Datei „Form1.Designer.cs“ in Ihrem Projekt generiert.</span><span class="sxs-lookup"><span data-stu-id="aba49-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="aba49-113">Sie sieht ungefähr so aus:</span><span class="sxs-lookup"><span data-stu-id="aba49-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="aba49-114">So abonnieren Sie Ereignisse programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="aba49-114">To subscribe to events programmatically</span></span>  
  
1.  <span data-ttu-id="aba49-115">Definieren Sie eine Ereignishandlermethode, deren Signatur mit der Delegatsignatur des Ereignisses übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="aba49-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="aba49-116">Wenn das Ereignis z.B. auf dem Delegattyp <xref:System.EventHandler> basiert, repräsentiert der folgende Code den Methodenstub:</span><span class="sxs-lookup"><span data-stu-id="aba49-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  <span data-ttu-id="aba49-117">Verwenden Sie den Additionszuweisungsoperator (`+=`), um ihren Ereignishandler Ihrem Ereignis anzufügen.</span><span class="sxs-lookup"><span data-stu-id="aba49-117">Use the addition assignment operator (`+=`) to attach your event handler to the event.</span></span> <span data-ttu-id="aba49-118">Gehen Sie in folgendem Beispiel davon aus, dass ein Objekt mit dem Namen `publisher` ein Ereignis mit dem Namen `RaiseCustomEvent` aufweist.</span><span class="sxs-lookup"><span data-stu-id="aba49-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="aba49-119">Beachten Sie, dass die Abonnementklasse einen Verweis auf die Herausgeberklasse benötigt, um deren Ereignis abonnieren zu können.</span><span class="sxs-lookup"><span data-stu-id="aba49-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="aba49-120">Beachten Sie, dass die oben stehende Syntax in C# 2.0 neu ist.</span><span class="sxs-lookup"><span data-stu-id="aba49-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="aba49-121">Sie entsprechen der Syntax in C# 1.0, in der der kapselnde Delegat mithilfe des Schlüsselwort `new` explizit erstellt werden muss:</span><span class="sxs-lookup"><span data-stu-id="aba49-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="aba49-122">Ein Ereignishandler kann auch mithilfe eines Lambdaausdruckes hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="aba49-122">An event handler can also be added by using a lambda expression:</span></span>  
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     <span data-ttu-id="aba49-123">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von Lambdaausdrücken außerhalb von LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span><span class="sxs-lookup"><span data-stu-id="aba49-123">For more information, see [How to: Use Lambda Expressions Outside LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span></span>  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="aba49-124">So abonnieren Sie Ereignisse mit einer anonymen Methode</span><span class="sxs-lookup"><span data-stu-id="aba49-124">To subscribe to events by using an anonymous method</span></span>  
  
-   <span data-ttu-id="aba49-125">Wenn Sie das Abonnement eines Ereignisses später nicht kündigen müssen, können Sie den Additionszuweisungsoperator (`+=`) verwenden, um eine anonyme Methode an das Ereignis anzufügen.</span><span class="sxs-lookup"><span data-stu-id="aba49-125">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="aba49-126">Gehen Sie in folgendem Beispiel davon aus, dass ein Objekt mit dem Namen `publisher` ein Ereignis mit dem Namen `RaiseCustomEvent` aufweist, und dass eine `CustomEventArgs`-Klasse so definiert wurde, dass Sie eine Art von spezialisierter Ereignisinformation enthält.</span><span class="sxs-lookup"><span data-stu-id="aba49-126">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="aba49-127">Beachten Sie, dass die Abonnementklasse einen Verweis auf die `publisher` benötigt, um deren Ereignis abonnieren zu können.</span><span class="sxs-lookup"><span data-stu-id="aba49-127">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="aba49-128">Nehmen Sie auch zur Kenntnis, dass Sie das Abonnement eines Ereignisses nicht ohne Weiteres kündigen können, wenn Sie eine anonyme Funktion für das Abonnement verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="aba49-128">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="aba49-129">Um in einem derartigen Szenario das Abonnement kündigen zu können, müssen Sie zu dem Code zurückkehren, mit dem Sie das Ereignis abonniert haben; speichern Sie anschließend die anonyme Methode in einer Delegatvariablen, und fügen Sie dann den Delegaten in das Ereignis ein.</span><span class="sxs-lookup"><span data-stu-id="aba49-129">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="aba49-130">Grundsätzlich wird empfohlen, keine anonymen Funktionen für das Abonnieren von Ereignissen zu verwenden, wenn Sie das Abonnement an einer späteren Stelle in Ihrem Code noch einmal kündigen müssen.</span><span class="sxs-lookup"><span data-stu-id="aba49-130">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="aba49-131">Informationen zu anonymen Funktionen finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="aba49-131">For more information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="aba49-132">Kündigen des Abonnements</span><span class="sxs-lookup"><span data-stu-id="aba49-132">Unsubscribing</span></span>  
 <span data-ttu-id="aba49-133">Kündigen Sie das Ereignisabonnement, um ein Abrufen des Ereignishandlers beim Auslösen des Ereignisses zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="aba49-133">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="aba49-134">Sie sollten das Ereignisabonnement kündigen, bevor Sie ein Abonnentenobjekt verwerfen, um Ressourcenverluste zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="aba49-134">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="aba49-135">Bis zur Kündigung Ihres Ereignisabonnements verweist der Multicastdelegat, der dem Ereignis im Veröffentlichungsobjekt zugrunde liegt, auf einen Delegaten, der den Ereignishandler des Abonnenten einkapselt.</span><span class="sxs-lookup"><span data-stu-id="aba49-135">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="aba49-136">Solange das Veröffentlichungsobjekt diesen Verweis enthält, wird Ihr Abonnentenobjekt bei der automatische Speicherbereinigung nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="aba49-136">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="aba49-137">So kündigen Sie ein Ereignisabonnement</span><span class="sxs-lookup"><span data-stu-id="aba49-137">To unsubscribe from an event</span></span>  
  
-   <span data-ttu-id="aba49-138">Verwenden Sie den Subtraktionszuweisungsoperator (`-=`), um ein Ereignisabonnement zu kündigen:</span><span class="sxs-lookup"><span data-stu-id="aba49-138">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="aba49-139">Wenn alle Abonnenten ihr Ereignisabonnement gekündigt haben, wird die Ereignisinstanz in der Herausgeberklasse auf `null` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aba49-139">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba49-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aba49-140">See Also</span></span>  
 [<span data-ttu-id="aba49-141">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="aba49-141">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="aba49-142">event</span><span class="sxs-lookup"><span data-stu-id="aba49-142">event</span></span>](../../../csharp/language-reference/keywords/event.md)  
 [<span data-ttu-id="aba49-143">Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="aba49-143">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
 [<span data-ttu-id="aba49-144">-= Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="aba49-144">-= Operator (C# Reference)</span></span>](../../language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="aba49-145">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="aba49-145">+= Operator</span></span>](../../../csharp/language-reference/operators/addition-assignment-operator.md)