---
title: 'Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 3df357cb15f7f77cefbf360dd9615ce246afe2ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705326"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="28300-102">Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="28300-102">How to subscribe to and unsubscribe from events (C# Programming Guide)</span></span>
<span data-ttu-id="28300-103">Wenn Sie benutzerdefinierten Code schreiben möchten, der aufgerufen wird, wenn dieses Ereignis ausgelöst wird, können Sie ein Ereignis abonnieren, das von einer anderen Klasse veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="28300-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="28300-104">Sie können z.B. das `click`-Ereignis einer Schaltfläche abonnieren, damit Ihre Anwendung etwas nützliches macht, wenn ein Benutzer auf die Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="28300-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="28300-105">So abonnieren Sie Ereignisse mit der Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="28300-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="28300-106">Wenn Sie in der Ansicht **Entwurf** das Fenster **Eigenschaften** nicht sehen können, klicken Sie mit der rechten Maustaste auf das Formular oder das Kontrollelement, für das Sie einen Ereignishandler erstellen möchten, und wählen Sie anschließen **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="28300-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="28300-107">Klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="28300-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="28300-108">Doppelklicken Sie auf das Ereignis, das Sie erstellen möchten, z.B. das `Load`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="28300-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="28300-109">Visual C# erstellt eine leere Ereignishandlermethode, und fügt diese in den Code ein.</span><span class="sxs-lookup"><span data-stu-id="28300-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="28300-110">Alternativ können Sie den Code auch manuell in der **Codeansicht** einfügen.</span><span class="sxs-lookup"><span data-stu-id="28300-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="28300-111">Die folgenden Codezeilen deklarieren beispielsweise eine Eventhandlermethode, die aufgerufen wird, wenn die Klasse `Form` das `Load`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="28300-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="28300-112">Die Codezeile, die für das Abonnement des Ereignisses erforderlich ist, wird auch automatisch in der `InitializeComponent`-Methode in der Datei „Form1.Designer.cs“ in Ihrem Projekt generiert.</span><span class="sxs-lookup"><span data-stu-id="28300-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="28300-113">Sie sieht ungefähr so aus:</span><span class="sxs-lookup"><span data-stu-id="28300-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="28300-114">So abonnieren Sie Ereignisse programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="28300-114">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="28300-115">Definieren Sie eine Ereignishandlermethode, deren Signatur mit der Delegatsignatur des Ereignisses übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="28300-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="28300-116">Wenn das Ereignis z.B. auf dem Delegattyp <xref:System.EventHandler> basiert, repräsentiert der folgende Code den Methodenstub:</span><span class="sxs-lookup"><span data-stu-id="28300-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="28300-117">Verwenden Sie den Additionszuweisungsoperator (`+=`), um Ihrem Ereignis einen Ereignishandler anzufügen.</span><span class="sxs-lookup"><span data-stu-id="28300-117">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="28300-118">Gehen Sie in folgendem Beispiel davon aus, dass ein Objekt mit dem Namen `publisher` ein Ereignis mit dem Namen `RaiseCustomEvent` aufweist.</span><span class="sxs-lookup"><span data-stu-id="28300-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="28300-119">Beachten Sie, dass die Abonnementklasse einen Verweis auf die Herausgeberklasse benötigt, um deren Ereignis abonnieren zu können.</span><span class="sxs-lookup"><span data-stu-id="28300-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="28300-120">Beachten Sie, dass die oben stehende Syntax in C# 2.0 neu ist.</span><span class="sxs-lookup"><span data-stu-id="28300-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="28300-121">Sie entsprechen der Syntax in C# 1.0, in der der kapselnde Delegat mithilfe des Schlüsselwort `new` explizit erstellt werden muss:</span><span class="sxs-lookup"><span data-stu-id="28300-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="28300-122">Sie können auch einen [Lambdaausdruck](../statements-expressions-operators/lambda-expressions.md) zum Angeben eines Ereignishandlers verwenden:</span><span class="sxs-lookup"><span data-stu-id="28300-122">You also can use a [lambda expression](../statements-expressions-operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="28300-123">So abonnieren Sie Ereignisse mit einer anonymen Methode</span><span class="sxs-lookup"><span data-stu-id="28300-123">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="28300-124">Wenn Sie das Abonnement eines Ereignisses später nicht kündigen müssen, können Sie den Additionszuweisungsoperator (`+=`) verwenden, um eine anonyme Methode an das Ereignis anzufügen.</span><span class="sxs-lookup"><span data-stu-id="28300-124">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="28300-125">Gehen Sie in folgendem Beispiel davon aus, dass ein Objekt mit dem Namen `publisher` ein Ereignis mit dem Namen `RaiseCustomEvent` aufweist, und dass eine `CustomEventArgs`-Klasse so definiert wurde, dass Sie eine Art von spezialisierter Ereignisinformation enthält.</span><span class="sxs-lookup"><span data-stu-id="28300-125">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="28300-126">Beachten Sie, dass die Abonnementklasse einen Verweis auf die `publisher` benötigt, um deren Ereignis abonnieren zu können.</span><span class="sxs-lookup"><span data-stu-id="28300-126">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="28300-127">Nehmen Sie auch zur Kenntnis, dass Sie das Abonnement eines Ereignisses nicht ohne Weiteres kündigen können, wenn Sie eine anonyme Funktion für das Abonnement verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="28300-127">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="28300-128">Um in einem derartigen Szenario das Abonnement kündigen zu können, müssen Sie zu dem Code zurückkehren, mit dem Sie das Ereignis abonniert haben; speichern Sie anschließend die anonyme Methode in einer Delegatvariablen, und fügen Sie dann den Delegaten in das Ereignis ein.</span><span class="sxs-lookup"><span data-stu-id="28300-128">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="28300-129">Grundsätzlich wird empfohlen, keine anonymen Funktionen für das Abonnieren von Ereignissen zu verwenden, wenn Sie das Abonnement an einer späteren Stelle in Ihrem Code noch einmal kündigen müssen.</span><span class="sxs-lookup"><span data-stu-id="28300-129">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="28300-130">Informationen zu anonymen Funktionen finden Sie unter [Anonyme Funktionen](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="28300-130">For more information about anonymous functions, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="28300-131">Kündigen des Abonnements</span><span class="sxs-lookup"><span data-stu-id="28300-131">Unsubscribing</span></span>  
 <span data-ttu-id="28300-132">Kündigen Sie das Ereignisabonnement, um ein Abrufen des Ereignishandlers beim Auslösen des Ereignisses zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="28300-132">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="28300-133">Sie sollten das Ereignisabonnement kündigen, bevor Sie ein Abonnentenobjekt verwerfen, um Ressourcenverluste zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="28300-133">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="28300-134">Bis zur Kündigung Ihres Ereignisabonnements verweist der Multicastdelegat, der dem Ereignis im Veröffentlichungsobjekt zugrunde liegt, auf einen Delegaten, der den Ereignishandler des Abonnenten einkapselt.</span><span class="sxs-lookup"><span data-stu-id="28300-134">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="28300-135">Solange das Veröffentlichungsobjekt diesen Verweis enthält, wird Ihr Abonnentenobjekt bei der automatische Speicherbereinigung nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="28300-135">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="28300-136">So kündigen Sie ein Ereignisabonnement</span><span class="sxs-lookup"><span data-stu-id="28300-136">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="28300-137">Verwenden Sie den Subtraktionszuweisungsoperator (`-=`), um ein Ereignisabonnement zu kündigen:</span><span class="sxs-lookup"><span data-stu-id="28300-137">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="28300-138">Wenn alle Abonnenten ihr Ereignisabonnement gekündigt haben, wird die Ereignisinstanz in der Herausgeberklasse auf `null` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28300-138">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28300-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28300-139">See also</span></span>

- [<span data-ttu-id="28300-140">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="28300-140">Events</span></span>](./index.md)
- [<span data-ttu-id="28300-141">event</span><span class="sxs-lookup"><span data-stu-id="28300-141">event</span></span>](../../language-reference/keywords/event.md)
- [<span data-ttu-id="28300-142">Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen</span><span class="sxs-lookup"><span data-stu-id="28300-142">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="28300-143">Operatoren „-“ und „-=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="28300-143">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="28300-144">Operatoren „+“ und „+=“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="28300-144">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
