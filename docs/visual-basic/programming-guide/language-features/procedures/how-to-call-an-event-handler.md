---
title: Vorgehensweise beim aufzurufen eines Ereignis Handlers
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3762c79dd3d883ae2ccfe76b335cf98ac87d4246
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464960"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="2c816-102">Vorgehensweise beim aufzurufen eines Ereignis Handlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c816-102">How to call an event handler in Visual Basic</span></span>

<span data-ttu-id="2c816-103">Ein *Ereignis* ist eine Aktion oder ein Vorkommen – z. b. ein Mausklick oder ein Guthaben Limit überschritten –, das von einer Programm Komponente erkannt wird, und für das Sie Code schreiben können, um Antworten zu können.</span><span class="sxs-lookup"><span data-stu-id="2c816-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="2c816-104">Ein *Ereignishandler* ist der Code, den Sie schreiben, um auf ein Ereignis zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2c816-104">An *event handler* is the code you write to respond to an event.</span></span>

<span data-ttu-id="2c816-105">Ein Ereignishandler in Visual Basic ist eine `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2c816-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="2c816-106">Sie werden jedoch normalerweise nicht auf dieselbe Weise aufgerufen wie andere `Sub` Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="2c816-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="2c816-107">Stattdessen identifizieren Sie die Prozedur als Handler für das-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2c816-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="2c816-108">Hierfür können Sie eine [`Handles`](../../../language-reference/statements/handles-clause.md) -Klausel und eine- [`WithEvents`](../../../language-reference/modifiers/withevents.md) Variable oder eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c816-108">You can do this either with a [`Handles`](../../../language-reference/statements/handles-clause.md) clause and a [`WithEvents`](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="2c816-109">Die Verwendung einer- `Handles` Klausel ist die Standardmethode zum Deklarieren eines Ereignis Handlers in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2c816-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="2c816-110">Dies ist die Methode, mit der die Ereignishandler von den Designern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) programmieren.</span><span class="sxs-lookup"><span data-stu-id="2c816-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="2c816-111">Die- `AddHandler` Anweisung eignet sich zum dynamischen Ereignisse zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2c816-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

<span data-ttu-id="2c816-112">Wenn das Ereignis auftritt, ruft Visual Basic automatisch die Ereignishandlerprozedur auf.</span><span class="sxs-lookup"><span data-stu-id="2c816-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="2c816-113">Jeder Code, der Zugriff auf das Ereignis hat, kann dazu führen, dass er durch Ausführen einer [RaiseEvent-Anweisung](../../../language-reference/statements/raiseevent-statement.md)ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2c816-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

<span data-ttu-id="2c816-114">Sie können dem gleichen Ereignis mehr als einen Ereignishandler zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2c816-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="2c816-115">In einigen Fällen können Sie einen Handler von einem Ereignis trennen.</span><span class="sxs-lookup"><span data-stu-id="2c816-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="2c816-116">Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="2c816-116">For more information, see [Events](../events/index.md).</span></span>

## <a name="call-an-event-handler-using-no-loc-texthandles-and-no-locwithevents"></a><span data-ttu-id="2c816-117">Abrufen eines Ereignis Handlers mithilfe von :::no-loc text="Handles"::: und WithEvents</span><span class="sxs-lookup"><span data-stu-id="2c816-117">Call an event handler using :::no-loc text="Handles"::: and WithEvents</span></span>

1. <span data-ttu-id="2c816-118">Stellen Sie sicher, dass das Ereignis mit einer [Ereignis Anweisung](../../../language-reference/statements/event-statement.md)deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="2c816-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="2c816-119">Deklarieren Sie eine Objekt Variable auf Modul-oder Klassenebene mithilfe des [`WithEvents`](../../../language-reference/modifiers/withevents.md) Schlüssel Worts.</span><span class="sxs-lookup"><span data-stu-id="2c816-119">Declare an object variable at module or class level, using the [`WithEvents`](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="2c816-120">Die- `As` Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="2c816-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="2c816-121">Fügen Sie in der Deklaration der Ereignis Behandlungs `Sub` Prozedur eine [`Handles`](../../../language-reference/statements/handles-clause.md) -Klausel hinzu, die die `WithEvents` -Variable und den Ereignis Namen angibt.</span><span class="sxs-lookup"><span data-stu-id="2c816-121">In the declaration of the event-handling `Sub` procedure, add a [`Handles`](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="2c816-122">Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="2c816-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="2c816-123">Der Code kann eine- `RaiseEvent` Anweisung verwenden, um das-Ereignis zu treffen.</span><span class="sxs-lookup"><span data-stu-id="2c816-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="2c816-124">Im folgenden Beispiel wird ein Ereignis und eine `WithEvents` Variable definiert, die auf die-Klasse verweist, die das-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="2c816-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="2c816-125">Das Ereignis Behandlungs `Sub` Verfahren verwendet eine- `Handles` Klausel, um die Klasse und das Ereignis anzugeben, die es behandelt.</span><span class="sxs-lookup"><span data-stu-id="2c816-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a><span data-ttu-id="2c816-126">Abrufen eines Ereignis Handlers mithilfe von AddHandler</span><span class="sxs-lookup"><span data-stu-id="2c816-126">Call an event handler using AddHandler</span></span>

1. <span data-ttu-id="2c816-127">Stellen Sie sicher, dass das-Ereignis mit einer-Anweisung deklariert wird `Event` .</span><span class="sxs-lookup"><span data-stu-id="2c816-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="2c816-128">Führen Sie eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) aus, um die Ereignis Behandlungs `Sub` Prozedur dynamisch mit dem-Ereignis zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="2c816-128">Execute an [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="2c816-129">Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="2c816-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="2c816-130">Der Code kann eine- `RaiseEvent` Anweisung verwenden, um das-Ereignis zu treffen.</span><span class="sxs-lookup"><span data-stu-id="2c816-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

    <span data-ttu-id="2c816-131">Im folgenden Beispiel wird die-Prozedur mithilfe der [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) im-Konstruktor `OnFormClosing` als Ereignishandler für verknüpft <xref:System.Windows.Forms.Form.FormClosing> .</span><span class="sxs-lookup"><span data-stu-id="2c816-131">The following example uses the [AddHandler statement](../../../language-reference/statements/addhandler-statement.md) in the constructor to associate the `OnFormClosing` procedure as an event handler for <xref:System.Windows.Forms.Form.FormClosing>.</span></span>

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    <span data-ttu-id="2c816-132">Sie können einen Ereignishandler von einem Ereignis trennen, indem Sie die [RemoveHandler-Anweisung](../../../language-reference/statements/removehandler-statement.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c816-132">You can dissociate an event handler from an event by executing the [RemoveHandler statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c816-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c816-133">See also</span></span>

- [<span data-ttu-id="2c816-134">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2c816-134">Procedures</span></span>](index.md)
- [<span data-ttu-id="2c816-135">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2c816-135">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="2c816-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2c816-136">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2c816-137">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="2c816-137">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="2c816-138">Vorgehensweise: Erstellen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="2c816-138">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="2c816-139">Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="2c816-139">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
