---
title: 'Vorgehensweise: Simulieren von Maus- und Tastaturereignissen in Code'
description: Erfahren Sie, wie Sie die Windows Forms bereitgestellten Optionen zum programmgesteuerten simulieren von Maus-und Tastatureingaben verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 9b453787f7fa7f5041f75e04d65557a0a3838bee
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904363"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="5ea8d-103">Vorgehensweise: Simulieren von Maus- und Tastaturereignissen in Code</span><span class="sxs-lookup"><span data-stu-id="5ea8d-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="5ea8d-104">Windows Forms stellt mehrere Optionen zur programmgesteuerten Simulation von Maus- und Tastatureingaben bereit.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="5ea8d-105">Dieses Thema enthält eine Übersicht über diese Optionen.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="5ea8d-106">Simulieren von Mauseingaben</span><span class="sxs-lookup"><span data-stu-id="5ea8d-106">Simulating Mouse Input</span></span>

<span data-ttu-id="5ea8d-107">Die beste Möglichkeit, Mauseingaben zu simulieren, ist ein Aufruf der `On`*Ereignisname* -Methode, die das Mausereignis auslöst, die Sie simulieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="5ea8d-108">Diese Option wird normalerweise nur in benutzerdefinierten Steuerelementen und Formularen unterstützt, weil die Methoden, die Ereignisse auslösen, geschützt sind und außerhalb des Steuerelements oder Formulars nicht aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="5ea8d-109">Die folgenden Schritte veranschaulichen beispielsweise, wie ein Klicken mit der rechten Maustaste in Code simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="5ea8d-110">So klicken Sie programmgesteuert mit der rechten Maustaste</span><span class="sxs-lookup"><span data-stu-id="5ea8d-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="5ea8d-111">Erstellen Sie eine <xref:System.Windows.Forms.MouseEventArgs> -Instanz, deren <xref:System.Windows.Forms.MouseEventArgs.Button%2A> -Eigenschaft auf den Wert <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="5ea8d-112">Rufen Sie die <xref:System.Windows.Forms.Control.OnMouseClick%2A> -Methode mit dieser <xref:System.Windows.Forms.MouseEventArgs> -Instanz als Argument auf.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="5ea8d-113">Weitere Informationen zu benutzerdefinierten Steuerelementen finden Sie unter [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](./controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="5ea8d-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="5ea8d-114">Es gibt weitere Möglichkeiten, Mauseingaben zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="5ea8d-115">Beispielsweise können Sie programmgesteuert eine Steuerelementeigenschaft festlegen, die einen Zustand darstellt, der normalerweise per Mauseingabe festgelegt wird (etwa die <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft des <xref:System.Windows.Forms.CheckBox> -Steuerelements). Sie können aber auch direkt den Delegaten aufrufen, der mit dem Ereignis verknüpft ist, das Sie simulieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="5ea8d-116">Simulieren von Tastatureingaben</span><span class="sxs-lookup"><span data-stu-id="5ea8d-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="5ea8d-117">Tastatureingaben können mit denselben Strategien simuliert werden, die hier für Mauseingaben erläutert sind. Zusätzlich stellt Windows Forms aber die <xref:System.Windows.Forms.SendKeys> -Klasse bereit, um Tastatureingaben an die aktive Anwendung senden zu können.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="5ea8d-118">Wenn Ihre Anwendung für internationale Verwendung mit unterschiedlichen Tastaturen vorgesehen ist, kann ein Verwenden von <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> zu unvorhersehbaren Ergebnissen führen und sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="5ea8d-119">Die <xref:System.Windows.Forms.SendKeys> -Klasse wurde für .NET Framework 3.0 aktualisiert, damit sie in Anwendungen verwendet werden kann, die unter Windows Vista ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="5ea8d-120">Die verbesserte Sicherheit von Windows Vista (Stichwort Benutzerkontensteuerung) verhindert, dass die vorherige Implementierung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="5ea8d-121">Die <xref:System.Windows.Forms.SendKeys> -Klasse ist anfällig für Probleme hinsichtlich der zeitlichen Steuerung, sodass einige Entwickler gezwungen waren, Umgehungslösungen zu finden.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="5ea8d-122">Die aktualisierte Implementierung ist immer noch anfällig für Probleme hinsichtlich der zeitlichen Steuerung, ist jedoch etwas schneller und erfordert möglicherweise Änderungen an den Umgehungslösungen.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="5ea8d-123">Die <xref:System.Windows.Forms.SendKeys> -Klasse versucht zunächst, die vorherige Implementierung zu verwenden. Schlägt dies fehl, wird die neue Implementierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="5ea8d-124">Infolgedessen verhält sich die <xref:System.Windows.Forms.SendKeys> -Klasse unter verschiedenen Betriebssystemen möglicherweise unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="5ea8d-125">Verwendet die <xref:System.Windows.Forms.SendKeys> -Klasse die neue Implementierung, wartet die <xref:System.Windows.Forms.SendKeys.SendWait%2A> -Methode nicht auf zu verarbeitende Nachrichten, wenn diese an einen anderen Prozess gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="5ea8d-126">Ist für Ihre Anwendung ein einheitliches, vom Betriebssystem unabhängiges Verhalten erforderlich, können Sie für die <xref:System.Windows.Forms.SendKeys> -Klasse das Verwenden der neuen Implementierung erzwingen, indem Sie die folgende Anwendungseinstellung in Ihre "app.config"-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="5ea8d-127">Soll die <xref:System.Windows.Forms.SendKeys> -Klasse gezwungen werden, die vorherige Implementierung zu verwenden, geben Sie stattdessen den Wert `"JournalHook"` an.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="5ea8d-128">So senden Sie eine Tastatureingabe an dieselbe Anwendung</span><span class="sxs-lookup"><span data-stu-id="5ea8d-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="5ea8d-129">Rufen Sie die <xref:System.Windows.Forms.SendKeys.Send%2A> - oder die <xref:System.Windows.Forms.SendKeys.SendWait%2A> -Methode der <xref:System.Windows.Forms.SendKeys> -Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="5ea8d-130">Die angegebenen Tastatureingaben werden vom aktiven Steuerelement der Anwendung empfangen.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="5ea8d-131">Im folgenden Codebeispiel wird <xref:System.Windows.Forms.SendKeys.Send%2A> verwendet, um ein Drücken der EINGABETASTE zu simulieren, wenn der Benutzer auf die Oberfläche des Formulars doppelklickt.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="5ea8d-132">Für dieses Beispiel wird ein <xref:System.Windows.Forms.Form> -Objekt mit einem einzelnen <xref:System.Windows.Forms.Button> -Steuerelement angenommen, dessen Aktivierreihenfolge (TabIndex) gleich 0 ist.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="5ea8d-133">So senden Sie eine Tastatureingabe an eine andere Anwendung</span><span class="sxs-lookup"><span data-stu-id="5ea8d-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="5ea8d-134">Aktivieren Sie das Anwendungsfenster, das die Tastatureingaben empfängt, und rufen Sie dann die <xref:System.Windows.Forms.SendKeys.Send%2A> - oder die <xref:System.Windows.Forms.SendKeys.SendWait%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="5ea8d-135">Da keine verwaltete Methode zum Aktivieren einer anderen Anwendung vorhanden ist, müssen Sie systemeigene Windows-Methoden verwenden, um den Fokus auf andere Anwendungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="5ea8d-136">Im folgenden Codebeispiel wird ein Plattformaufruf dazu verwendet, die Methoden `FindWindow` und `SetForegroundWindow` aufzurufen, um das Anwendungsfenster Rechner zu aktivieren, und dann wird <xref:System.Windows.Forms.SendKeys.SendWait%2A> aufgerufen, um einige Berechnungselemente an Rechner zu senden.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ea8d-137">Die richtigen Parameter des `FindWindow` -Aufrufs, der nach der Anwendung Rechner sucht, können je nach Windows-Version unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="5ea8d-138">Der folgende Code ermittelt die Rechner Anwendung unter Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="5ea8d-139">Ändern Sie unter Windows Vista den ersten Parameter in "SciCalc".</span><span class="sxs-lookup"><span data-stu-id="5ea8d-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="5ea8d-140">Sie können das zu Visual Studio gehörende Tool Spy++ verwenden, um die richtigen Parameter zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="5ea8d-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ea8d-141">Example</span></span>

<span data-ttu-id="5ea8d-142">Das folgende Codebeispiel ist die vollständige Anwendung für die vorherigen Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="5ea8d-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="5ea8d-143">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5ea8d-143">Compiling the Code</span></span>

<span data-ttu-id="5ea8d-144">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ea8d-144">This example requires:</span></span>

- <span data-ttu-id="5ea8d-145">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="5ea8d-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ea8d-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ea8d-146">See also</span></span>

- [<span data-ttu-id="5ea8d-147">Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ea8d-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
