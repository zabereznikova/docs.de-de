---
title: 'Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: f2716db441380138e6058ec45d9ae9c07f0e21a7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869382"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="788c6-102">Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="788c6-102">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>

<span data-ttu-id="788c6-103">Bei Verwendung von Multithreading zur Verbesserung der Leistung von Windows Forms-Anwendungen müssen Sie sicherstellen, dass Sie die Steuerelemente auf threadsichere Weise aufrufen.</span><span class="sxs-lookup"><span data-stu-id="788c6-103">If you use multithreading to improve the performance of your Windows Forms applications, you must make sure that you make calls to your controls in a thread-safe way.</span></span>

<span data-ttu-id="788c6-104">Zugriff auf Windows Forms-Steuerelemente ist nicht grundsätzlich threadsicher.</span><span class="sxs-lookup"><span data-stu-id="788c6-104">Access to Windows Forms controls is not inherently thread safe.</span></span> <span data-ttu-id="788c6-105">Wenn Sie mit zwei oder mehr Threads den Zustand eines Steuerelements verändern, ist es möglich, das Steuerelement in eine inkonsistenten Zustand zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="788c6-105">If you have two or more threads manipulating the state of a control, it is possible to force the control into an inconsistent state.</span></span> <span data-ttu-id="788c6-106">Andere Fehler in Bezug auf Threads sind möglich, z. B. Racebedingungen und Deadlocks.</span><span class="sxs-lookup"><span data-stu-id="788c6-106">Other thread-related bugs are possible, such as race conditions and deadlocks.</span></span> <span data-ttu-id="788c6-107">Es ist wichtig, sicherzustellen, dass der Zugriff auf die Steuerelemente auf threadsichere Weise erfolgt.</span><span class="sxs-lookup"><span data-stu-id="788c6-107">It is important to make sure that access to your controls is performed in a thread-safe way.</span></span>

<span data-ttu-id="788c6-108">Es ist unsicher, ein Steuerelement von einem anderen Thread als dem aufzurufen, der das Steuerelement erstellt hat, ohne die <xref:System.Windows.Forms.Control.Invoke%2A> -Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="788c6-108">It is unsafe to call a control from a thread other than the one that created the control without using the <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span> <span data-ttu-id="788c6-109">Es folgt ein Beispiel für einen Aufruf, der nicht threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="788c6-109">The following is an example of a call that is not thread safe.</span></span>

```csharp
// This event handler creates a thread that calls a
// Windows Forms control in an unsafe way.
private void setTextUnsafeBtn_Click(
    object sender,
    EventArgs e)
{
    this.demoThread =
        new Thread(new ThreadStart(this.ThreadProcUnsafe));

    this.demoThread.Start();
}

// This method is executed on the worker thread and makes
// an unsafe call on the TextBox control.
private void ThreadProcUnsafe()
{
    this.textBox1.Text = "This text was set unsafely.";
}
```

```vb
' This event handler creates a thread that calls a
' Windows Forms control in an unsafe way.
 Private Sub setTextUnsafeBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextUnsafeBtn.Click

     Me.demoThread = New Thread( _
     New ThreadStart(AddressOf Me.ThreadProcUnsafe))

     Me.demoThread.Start()
 End Sub

' This method is executed on the worker thread and makes
' an unsafe call on the TextBox control.
Private Sub ThreadProcUnsafe()
   Me.textBox1.Text = "This text was set unsafely."
End Sub
```

```cpp
// This event handler creates a thread that calls a
    // Windows Forms control in an unsafe way.
private:
    void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->demoThread =
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));

        this->demoThread->Start();
    }

    // This method is executed on the worker thread and makes
    // an unsafe call on the TextBox control.
private:
    void ThreadProcUnsafe()
    {
        this->textBox1->Text = "This text was set unsafely.";
    }
```

<span data-ttu-id="788c6-110">Mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] können Sie feststellen, wann Sie auf die Steuerelemente auf nicht threadsichere Weise zugreifen.</span><span class="sxs-lookup"><span data-stu-id="788c6-110">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] helps you detect when you are accessing your controls in a manner that is not thread safe.</span></span> <span data-ttu-id="788c6-111">Wenn Sie die Anwendung im Debugger ausführen und ein anderer Thread als der, der ein Steuerelement erstellt hat, versucht, das Steuerelement aufzurufen, löst der Debugger eine <xref:System.InvalidOperationException> mit einer Meldung wie "Zugriff auf Steuerelement *Steuerelementname* von einem anderen Thread als dem Erstellungsthread" aus.</span><span class="sxs-lookup"><span data-stu-id="788c6-111">When you are running your application in the debugger, and a thread other than the one which created a control tries to call that control, the debugger raises an <xref:System.InvalidOperationException> with the message, "Control *control name* accessed from a thread other than the thread it was created on."</span></span>

<span data-ttu-id="788c6-112">Diese Ausnahme tritt zuverlässig beim Debuggen und unter bestimmten Bedingungen zur Laufzeit auf.</span><span class="sxs-lookup"><span data-stu-id="788c6-112">This exception occurs reliably during debugging and, under some circumstances, at run time.</span></span> <span data-ttu-id="788c6-113">Diese Ausnahme wird möglicherweise angezeigt, wenn Sie Anwendungen debuggen, die Sie mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] vor [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="788c6-113">You might see this exception when you debug applications that you wrote with the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] prior to the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="788c6-114">Es wird dringend empfohlen, dieses Problem ggf. zu beheben. Sie können es aber deaktivieren, indem Sie die <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> -Eigenschaft auf `false`festlegen.</span><span class="sxs-lookup"><span data-stu-id="788c6-114">You are strongly advised to fix this problem when you see it, but you can disable it by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> property to `false`.</span></span> <span data-ttu-id="788c6-115">Dies bewirkt, dass das Steuerelement wie unter Visual Studio .NET 2003 und [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="788c6-115">This causes your control to run like it would run under Visual Studio .NET 2003 and the [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="788c6-116">Wenn Sie ActiveX-Steuerelemente in einem Formular verwenden, erhalten Sie möglicherweise die threadübergreifende <xref:System.InvalidOperationException> beim Ausführen im Debugger.</span><span class="sxs-lookup"><span data-stu-id="788c6-116">If you are using ActiveX controls on a form, you may receive the cross-thread <xref:System.InvalidOperationException> when you run under the debugger.</span></span> <span data-ttu-id="788c6-117">In diesem Fall unterstützt das ActiveX-Steuerelement kein Multithreading.</span><span class="sxs-lookup"><span data-stu-id="788c6-117">When this occurs, the ActiveX control does not support multithreading.</span></span> <span data-ttu-id="788c6-118">Weitere Informationen zum Verwenden von ActiveX-Steuerelementen mit Windows Forms finden Sie unter [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md).</span><span class="sxs-lookup"><span data-stu-id="788c6-118">For more information about using ActiveX controls with Windows Forms, see [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md).</span></span>

## <a name="making-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="788c6-119">Threadsichere Aufrufe von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="788c6-119">Making Thread-Safe Calls to Windows Forms Controls</span></span>

### <a name="to-make-a-thread-safe-call-to-a-windows-forms-control"></a><span data-ttu-id="788c6-120">So führen Sie einen threadsicheren Aufruf des Windows Forms-Steuerelements aus</span><span class="sxs-lookup"><span data-stu-id="788c6-120">To make a thread-safe call to a Windows Forms control</span></span>

1.  <span data-ttu-id="788c6-121">Fragen Sie die <xref:System.Windows.Forms.Control.InvokeRequired%2A> -Eigenschaft des Steuerelements ab.</span><span class="sxs-lookup"><span data-stu-id="788c6-121">Query the control's <xref:System.Windows.Forms.Control.InvokeRequired%2A> property.</span></span>

2.  <span data-ttu-id="788c6-122">Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true`zurückgibt, rufen Sie <xref:System.Windows.Forms.Control.Invoke%2A> mit einem Delegaten auf, der den eigentlichen Aufruf des Steuerelements übernimmt.</span><span class="sxs-lookup"><span data-stu-id="788c6-122">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, call <xref:System.Windows.Forms.Control.Invoke%2A> with a delegate that makes the actual call to the control.</span></span>

3.  <span data-ttu-id="788c6-123">Wenn <xref:System.Windows.Forms.Control.InvokeRequired%2A> `false`zurückgibt, rufen Sie das Steuerelement direkt auf.</span><span class="sxs-lookup"><span data-stu-id="788c6-123">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, call the control directly.</span></span>

<span data-ttu-id="788c6-124">Im folgenden Codebeispiel wird ein threadsicherer Aufruf in der `ThreadProcSafe` -Methode implementiert, die vom Hintergrundthread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="788c6-124">In the following code example, a thread-safe call is implemented in the `ThreadProcSafe` method, which is executed by the background thread.</span></span> <span data-ttu-id="788c6-125">Wenn das <xref:System.Windows.Forms.TextBox> des <xref:System.Windows.Forms.Control.InvokeRequired%2A> -Steuerelements `true`zurückgibt, erstellt die `ThreadProcSafe` -Methode eine Instanz von `StringArgReturningVoidDelegate` und übergibt sie an die <xref:System.Windows.Forms.Control.Invoke%2A> -Methode des Formulars.</span><span class="sxs-lookup"><span data-stu-id="788c6-125">If the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, the `ThreadProcSafe` method creates an instance of `StringArgReturningVoidDelegate` and passes that to the form's <xref:System.Windows.Forms.Control.Invoke%2A> method.</span></span> <span data-ttu-id="788c6-126">Dies bewirkt, dass die `SetText` -Methode in dem Thread aufgerufen wird, der das <xref:System.Windows.Forms.TextBox> -Steuerelement erstellt hat, und in diesem Threadkontext wird die <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft direkt festgelegt.</span><span class="sxs-lookup"><span data-stu-id="788c6-126">This causes the `SetText` method to be called on the thread that created the <xref:System.Windows.Forms.TextBox> control, and in this thread context the <xref:System.Windows.Forms.Control.Text%2A> property is set directly.</span></span>

```csharp
// This event handler creates a thread that calls a
// Windows Forms control in a thread-safe way.
private void setTextSafeBtn_Click(
    object sender,
    EventArgs e)
{
    this.demoThread =
        new Thread(new ThreadStart(this.ThreadProcSafe));

    this.demoThread.Start();
}

// This method is executed on the worker thread and makes
// a thread-safe call on the TextBox control.
private void ThreadProcSafe()
{
    this.SetText("This text was set safely.");
}
```

```vb
' This event handler creates a thread that calls a
' Windows Forms control in a thread-safe way.
 Private Sub setTextSafeBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextSafeBtn.Click

     Me.demoThread = New Thread( _
     New ThreadStart(AddressOf Me.ThreadProcSafe))

     Me.demoThread.Start()
 End Sub

' This method is executed on the worker thread and makes
' a thread-safe call on the TextBox control.
Private Sub ThreadProcSafe()
   Me.SetText("This text was set safely.")
 End Sub
```

```cpp
// This event handler creates a thread that calls a
    // Windows Forms control in a thread-safe way.
private:
    void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->demoThread =
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));

        this->demoThread->Start();
    }

    // This method is executed on the worker thread and makes
    // a thread-safe call on the TextBox control.
private:
    void ThreadProcSafe()
    {
        this->SetText("This text was set safely.");
    }
```

```csharp
// This delegate enables asynchronous calls for setting
// the text property on a TextBox control.
delegate void StringArgReturningVoidDelegate(string text);
```

```vb
' This delegate enables asynchronous calls for setting
' the text property on a TextBox control.
Delegate Sub StringArgReturningVoidDelegate([text] As String)
```

```cpp
// This delegate enables asynchronous calls for setting
// the text property on a TextBox control.
delegate void StringArgReturningVoidDelegate(String^ text);
```

```csharp
// This method demonstrates a pattern for making thread-safe
// calls on a Windows Forms control.
//
// If the calling thread is different from the thread that
// created the TextBox control, this method creates a
// StringArgReturningVoidDelegate and calls itself asynchronously using the
// Invoke method.
//
// If the calling thread is the same as the thread that created
// the TextBox control, the Text property is set directly.

private void SetText(string text)
{
    // InvokeRequired required compares the thread ID of the
    // calling thread to the thread ID of the creating thread.
    // If these threads are different, it returns true.
    if (this.textBox1.InvokeRequired)
    {
        StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);
        this.Invoke(d, new object[] { text });
    }
    else
    {
        this.textBox1.Text = text;
    }
}
```

```vb
' This method demonstrates a pattern for making thread-safe
' calls on a Windows Forms control.
'
' If the calling thread is different from the thread that
' created the TextBox control, this method creates a
' StringArgReturningVoidDelegate and calls itself asynchronously using the
' Invoke method.
'
' If the calling thread is the same as the thread that created
 ' the TextBox control, the Text property is set directly.

 Private Sub SetText(ByVal [text] As String)

     ' InvokeRequired required compares the thread ID of the
     ' calling thread to the thread ID of the creating thread.
     ' If these threads are different, it returns true.
     If Me.textBox1.InvokeRequired Then
         Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)
         Me.Invoke(d, New Object() {[text]})
     Else
         Me.textBox1.Text = [text]
     End If
 End Sub
```

```cpp
// This method demonstrates a pattern for making thread-safe
    // calls on a Windows Forms control.
    //
    // If the calling thread is different from the thread that
    // created the TextBox control, this method creates a
    // StringArgReturningVoidDelegate and calls itself asynchronously using the
    // Invoke method.
    //
    // If the calling thread is the same as the thread that created
    // the TextBox control, the Text property is set directly.

private:
    void SetText(String^ text)
    {
        // InvokeRequired required compares the thread ID of the
        // calling thread to the thread ID of the creating thread.
        // If these threads are different, it returns true.
        if (this->textBox1->InvokeRequired)
        {
            StringArgReturningVoidDelegate^ d =
                gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);
            this->Invoke(d, gcnew array<Object^> { text });
        }
        else
        {
            this->textBox1->Text = text;
        }
    }
```

## <a name="making-thread-safe-calls-by-using-backgroundworker"></a><span data-ttu-id="788c6-127">threadsichere Aufrufe mit BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="788c6-127">Making Thread-Safe Calls by using BackgroundWorker</span></span>
 <span data-ttu-id="788c6-128">Das bevorzugte Verfahren zum Implementieren von Multithreading in der Anwendung ist die Verwendung der <xref:System.ComponentModel.BackgroundWorker> -Komponente.</span><span class="sxs-lookup"><span data-stu-id="788c6-128">The preferred way to implement multithreading in your application is to use the <xref:System.ComponentModel.BackgroundWorker> component.</span></span> <span data-ttu-id="788c6-129">Die <xref:System.ComponentModel.BackgroundWorker> -Komponente verwendet ein ereignisgesteuertes Modell für Multithreading.</span><span class="sxs-lookup"><span data-stu-id="788c6-129">The <xref:System.ComponentModel.BackgroundWorker> component uses an event-driven model for multithreading.</span></span> <span data-ttu-id="788c6-130">Der Hintergrundthread führt den <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler aus, und der Thread, der die Steuerelemente erstellt, führt die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> - und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler aus.</span><span class="sxs-lookup"><span data-stu-id="788c6-130">The background thread runs your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, and the thread that creates your controls runs your <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handlers.</span></span> <span data-ttu-id="788c6-131">Sie können die Steuerelemente von den <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> - und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandlern aus aufrufen.</span><span class="sxs-lookup"><span data-stu-id="788c6-131">You can call your controls from your <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handlers.</span></span>

#### <a name="to-make-thread-safe-calls-by-using-backgroundworker"></a><span data-ttu-id="788c6-132">So führen Sie threadsichere Aufrufe mit BackgroundWorker durch</span><span class="sxs-lookup"><span data-stu-id="788c6-132">To make thread-safe calls by using BackgroundWorker</span></span>

1.  <span data-ttu-id="788c6-133">Erstellen Sie eine Methode zur Ausführung der Arbeit, die im Hintergrundthread ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="788c6-133">Create a method to do the work that you want done in the background thread.</span></span> <span data-ttu-id="788c6-134">Rufen Sie keine Steuerelemente auf, die vom Hauptthread in dieser Methode erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="788c6-134">Do not call controls created by the main thread in this method.</span></span>

2.  <span data-ttu-id="788c6-135">Erstellen Sie eine Methode, um die Ergebnisse der Hintergrundverarbeitung nach Abschluss zu melden.</span><span class="sxs-lookup"><span data-stu-id="788c6-135">Create a method to report the results of your background work after it finishes.</span></span> <span data-ttu-id="788c6-136">Sie können durch den Hauptthread in dieser Methode erstellte Steuerelemente aufrufen.</span><span class="sxs-lookup"><span data-stu-id="788c6-136">You can call controls created by the main thread in this method.</span></span>

3.  <span data-ttu-id="788c6-137">Binden Sie die in Schritt 1 erstellte Methode an das <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignis einer Instanz von <xref:System.ComponentModel.BackgroundWorker>, und binden Sie die in Schritt 2 erstellte Methode an das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignis der gleichen Instanz.</span><span class="sxs-lookup"><span data-stu-id="788c6-137">Bind the method created in step 1 to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event of an instance of <xref:System.ComponentModel.BackgroundWorker>, and bind the method created in step 2 to the same instance’s <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>

4.  <span data-ttu-id="788c6-138">Um den Hintergrundthread zu starten, rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> -Methode der <xref:System.ComponentModel.BackgroundWorker> -Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="788c6-138">To start the background thread, call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of the <xref:System.ComponentModel.BackgroundWorker> instance.</span></span>

<span data-ttu-id="788c6-139">Im folgenden Codebeispiel verwendet der <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler <xref:System.Threading.Thread.Sleep%2A> , um Arbeit zu simulieren, die einige Zeit dauert.</span><span class="sxs-lookup"><span data-stu-id="788c6-139">In the following code example, the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler uses <xref:System.Threading.Thread.Sleep%2A> to simulate work that takes some time.</span></span> <span data-ttu-id="788c6-140">Das <xref:System.Windows.Forms.TextBox> -Steuerelement des Formulars wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="788c6-140">It does not call the form’s <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="788c6-141">Die <xref:System.Windows.Forms.TextBox> -Eigenschaft des <xref:System.Windows.Forms.Control.Text%2A> -Steuerelements wird direkt im <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler festgelegt.</span><span class="sxs-lookup"><span data-stu-id="788c6-141">The <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.Text%2A> property is set directly in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

```csharp
// This BackgroundWorker is used to demonstrate the
// preferred way of performing asynchronous operations.
private BackgroundWorker backgroundWorker1;
```

```vb
' This BackgroundWorker is used to demonstrate the
' preferred way of performing asynchronous operations.
Private WithEvents backgroundWorker1 As BackgroundWorker
```

```cpp
// This BackgroundWorker is used to demonstrate the
    // preferred way of performing asynchronous operations.
private:
    BackgroundWorker^ backgroundWorker1;
```

```csharp
// This event handler starts the form's
// BackgroundWorker by calling RunWorkerAsync.
//
// The Text property of the TextBox control is set
// when the BackgroundWorker raises the RunWorkerCompleted
// event.
private void setTextBackgroundWorkerBtn_Click(
    object sender,
    EventArgs e)
{
    this.backgroundWorker1.RunWorkerAsync();
}

// This event handler sets the Text property of the TextBox
// control. It is called on the thread that created the
// TextBox control, so the call is thread-safe.
//
// BackgroundWorker is the preferred way to perform asynchronous
// operations.

private void backgroundWorker1_RunWorkerCompleted(
    object sender,
    RunWorkerCompletedEventArgs e)
{
    this.textBox1.Text =
        "This text was set safely by BackgroundWorker.";
}
```

```vb
' This event handler starts the form's
' BackgroundWorker by calling RunWorkerAsync.
'
' The Text property of the TextBox control is set
' when the BackgroundWorker raises the RunWorkerCompleted
' event.
 Private Sub setTextBackgroundWorkerBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click
     Me.backgroundWorker1.RunWorkerAsync()
 End Sub

' This event handler sets the Text property of the TextBox
' control. It is called on the thread that created the
' TextBox control, so the call is thread-safe.
'
' BackgroundWorker is the preferred way to perform asynchronous
' operations.
 Private Sub backgroundWorker1_RunWorkerCompleted( _
 ByVal sender As Object, _
 ByVal e As RunWorkerCompletedEventArgs) _
 Handles backgroundWorker1.RunWorkerCompleted
     Me.textBox1.Text = _
     "This text was set safely by BackgroundWorker."
 End Sub
```

```cpp
// This event handler starts the form's
    // BackgroundWorker by calling RunWorkerAsync.
    //
    // The Text property of the TextBox control is set
    // when the BackgroundWorker raises the RunWorkerCompleted
    // event.
private:
    void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->backgroundWorker1->RunWorkerAsync();
    }

    // This event handler sets the Text property of the TextBox
    // control. It is called on the thread that created the
    // TextBox control, so the call is thread-safe.
    //
    // BackgroundWorker is the preferred way to perform asynchronous
    // operations.

private:
    void backgroundWorker1_RunWorkerCompleted(
        Object^ sender,
        RunWorkerCompletedEventArgs^ e)
    {
        this->textBox1->Text =
            "This text was set safely by BackgroundWorker.";
    }
```

 <span data-ttu-id="788c6-142">Sie können auch den Fortschritt einer Hintergrundaufgabe mithilfe des <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> -Ereignisses melden.</span><span class="sxs-lookup"><span data-stu-id="788c6-142">You can also report the progress of a background task by using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="788c6-143">Ein Beispiel, das das Ereignis enthält, finden Sie unter <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="788c6-143">For an example that incorporates that event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span>

## <a name="example"></a><span data-ttu-id="788c6-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="788c6-144">Example</span></span>
 <span data-ttu-id="788c6-145">Das folgende Codebeispiel stellt eine vollständige Windows Forms-Anwendung dar, die aus einem Formular mit drei Schaltflächen und einem Textfeld besteht.</span><span class="sxs-lookup"><span data-stu-id="788c6-145">The following code example is a complete Windows Forms application that consists of a form with three buttons and one text box.</span></span> <span data-ttu-id="788c6-146">Die erste Schaltfläche zeigt den unsicheren threadübergreifenden Zugriff, die zweite Schaltfläche zeigt den sicheren Zugriff mithilfe von <xref:System.Windows.Forms.Control.Invoke%2A>, und die dritte Schaltfläche zeigt den sicheren Zugriff mithilfe von <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="788c6-146">The first button demonstrates unsafe cross-thread access, the second button demonstrates safe access by using <xref:System.Windows.Forms.Control.Invoke%2A>, and the third button demonstrates safe access by using <xref:System.ComponentModel.BackgroundWorker>.</span></span>

> [!NOTE]
> <span data-ttu-id="788c6-147">Anleitungen zum Ausführen des Beispiels finden Sie unter [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/cc447f7e-4c3b-4397-9d05-aeba3ca49416).</span><span class="sxs-lookup"><span data-stu-id="788c6-147">For instructions on how to run the example, see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/cc447f7e-4c3b-4397-9d05-aeba3ca49416).</span></span> <span data-ttu-id="788c6-148">Dieses Beispiel erfordert Verweise auf die Assemblys "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="788c6-148">This example requires references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

```csharp
using System;
using System.ComponentModel;
using System.Threading;
using System.Windows.Forms;

namespace CrossThreadDemo
{
    public class Form1 : Form
    {
        // This delegate enables asynchronous calls for setting
        // the text property on a TextBox control.
        delegate void StringArgReturningVoidDelegate(string text);

        // This thread is used to demonstrate both thread-safe and
        // unsafe ways to call a Windows Forms control.
        private Thread demoThread = null;

        // This BackgroundWorker is used to demonstrate the
        // preferred way of performing asynchronous operations.
        private BackgroundWorker backgroundWorker1;

        private TextBox textBox1;
        private Button setTextUnsafeBtn;
        private Button setTextSafeBtn;
        private Button setTextBackgroundWorkerBtn;

        private System.ComponentModel.IContainer components = null;

        public Form1()
        {
            InitializeComponent();
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null))
            {
                components.Dispose();
            }
            base.Dispose(disposing);
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in an unsafe way.
        private void setTextUnsafeBtn_Click(
            object sender,
            EventArgs e)
        {
            this.demoThread =
                new Thread(new ThreadStart(this.ThreadProcUnsafe));

            this.demoThread.Start();
        }

        // This method is executed on the worker thread and makes
        // an unsafe call on the TextBox control.
        private void ThreadProcUnsafe()
        {
            this.textBox1.Text = "This text was set unsafely.";
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in a thread-safe way.
        private void setTextSafeBtn_Click(
            object sender,
            EventArgs e)
        {
            this.demoThread =
                new Thread(new ThreadStart(this.ThreadProcSafe));

            this.demoThread.Start();
        }

        // This method is executed on the worker thread and makes
        // a thread-safe call on the TextBox control.
        private void ThreadProcSafe()
        {
            this.SetText("This text was set safely.");
        }

        // This method demonstrates a pattern for making thread-safe
        // calls on a Windows Forms control.
        //
        // If the calling thread is different from the thread that
        // created the TextBox control, this method creates a
        // StringArgReturningVoidDelegate and calls itself asynchronously using the
        // Invoke method.
        //
        // If the calling thread is the same as the thread that created
        // the TextBox control, the Text property is set directly.

        private void SetText(string text)
        {
            // InvokeRequired required compares the thread ID of the
            // calling thread to the thread ID of the creating thread.
            // If these threads are different, it returns true.
            if (this.textBox1.InvokeRequired)
            {
                StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);
                this.Invoke(d, new object[] { text });
            }
            else
            {
                this.textBox1.Text = text;
            }
        }

        // This event handler starts the form's
        // BackgroundWorker by calling RunWorkerAsync.
        //
        // The Text property of the TextBox control is set
        // when the BackgroundWorker raises the RunWorkerCompleted
        // event.
        private void setTextBackgroundWorkerBtn_Click(
            object sender,
            EventArgs e)
        {
            this.backgroundWorker1.RunWorkerAsync();
        }

        // This event handler sets the Text property of the TextBox
        // control. It is called on the thread that created the
        // TextBox control, so the call is thread-safe.
        //
        // BackgroundWorker is the preferred way to perform asynchronous
        // operations.

        private void backgroundWorker1_RunWorkerCompleted(
            object sender,
            RunWorkerCompletedEventArgs e)
        {
            this.textBox1.Text =
                "This text was set safely by BackgroundWorker.";
        }

        #region Windows Form Designer generated code

        private void InitializeComponent()
        {
            this.textBox1 = new System.Windows.Forms.TextBox();
            this.setTextUnsafeBtn = new System.Windows.Forms.Button();
            this.setTextSafeBtn = new System.Windows.Forms.Button();
            this.setTextBackgroundWorkerBtn = new System.Windows.Forms.Button();
            this.backgroundWorker1 = new System.ComponentModel.BackgroundWorker();
            this.SuspendLayout();
            //
            // textBox1
            //
            this.textBox1.Location = new System.Drawing.Point(12, 12);
            this.textBox1.Name = "textBox1";
            this.textBox1.Size = new System.Drawing.Size(240, 20);
            this.textBox1.TabIndex = 0;
            //
            // setTextUnsafeBtn
            //
            this.setTextUnsafeBtn.Location = new System.Drawing.Point(15, 55);
            this.setTextUnsafeBtn.Name = "setTextUnsafeBtn";
            this.setTextUnsafeBtn.TabIndex = 1;
            this.setTextUnsafeBtn.Text = "Unsafe Call";
            this.setTextUnsafeBtn.Click += new System.EventHandler(this.setTextUnsafeBtn_Click);
            //
            // setTextSafeBtn
            //
            this.setTextSafeBtn.Location = new System.Drawing.Point(96, 55);
            this.setTextSafeBtn.Name = "setTextSafeBtn";
            this.setTextSafeBtn.TabIndex = 2;
            this.setTextSafeBtn.Text = "Safe Call";
            this.setTextSafeBtn.Click += new System.EventHandler(this.setTextSafeBtn_Click);
            //
            // setTextBackgroundWorkerBtn
            //
            this.setTextBackgroundWorkerBtn.Location = new System.Drawing.Point(177, 55);
            this.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn";
            this.setTextBackgroundWorkerBtn.TabIndex = 3;
            this.setTextBackgroundWorkerBtn.Text = "Safe BW Call";
            this.setTextBackgroundWorkerBtn.Click += new System.EventHandler(this.setTextBackgroundWorkerBtn_Click);
            //
            // backgroundWorker1
            //
            this.backgroundWorker1.RunWorkerCompleted += new System.ComponentModel.RunWorkerCompletedEventHandler(this.backgroundWorker1_RunWorkerCompleted);
            //
            // Form1
            //
            this.ClientSize = new System.Drawing.Size(268, 96);
            this.Controls.Add(this.setTextBackgroundWorkerBtn);
            this.Controls.Add(this.setTextSafeBtn);
            this.Controls.Add(this.setTextUnsafeBtn);
            this.Controls.Add(this.textBox1);
            this.Name = "Form1";
            this.Text = "Form1";
            this.ResumeLayout(false);
            this.PerformLayout();

        }

        #endregion

        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.Run(new Form1());
        }

    }
}
```

```vb
Imports System
Imports System.ComponentModel
Imports System.Threading
Imports System.Windows.Forms

Public Class Form1
   Inherits Form

   ' This delegate enables asynchronous calls for setting
   ' the text property on a TextBox control.
   Delegate Sub StringArgReturningVoidDelegate([text] As String)

   ' This thread is used to demonstrate both thread-safe and
   ' unsafe ways to call a Windows Forms control.
   Private demoThread As Thread = Nothing

   ' This BackgroundWorker is used to demonstrate the
   ' preferred way of performing asynchronous operations.
   Private WithEvents backgroundWorker1 As BackgroundWorker

   Private textBox1 As TextBox
   Private WithEvents setTextUnsafeBtn As Button
   Private WithEvents setTextSafeBtn As Button
   Private WithEvents setTextBackgroundWorkerBtn As Button

   Private components As System.ComponentModel.IContainer = Nothing

   Public Sub New()
      InitializeComponent()
    End Sub

   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposing AndAlso (components IsNot Nothing) Then
         components.Dispose()
      End If
      MyBase.Dispose(disposing)
    End Sub

   ' This event handler creates a thread that calls a
   ' Windows Forms control in an unsafe way.
    Private Sub setTextUnsafeBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextUnsafeBtn.Click

        Me.demoThread = New Thread( _
        New ThreadStart(AddressOf Me.ThreadProcUnsafe))

        Me.demoThread.Start()
    End Sub

   ' This method is executed on the worker thread and makes
   ' an unsafe call on the TextBox control.
   Private Sub ThreadProcUnsafe()
      Me.textBox1.Text = "This text was set unsafely."
   End Sub

   ' This event handler creates a thread that calls a
   ' Windows Forms control in a thread-safe way.
    Private Sub setTextSafeBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextSafeBtn.Click

        Me.demoThread = New Thread( _
        New ThreadStart(AddressOf Me.ThreadProcSafe))

        Me.demoThread.Start()
    End Sub

   ' This method is executed on the worker thread and makes
   ' a thread-safe call on the TextBox control.
   Private Sub ThreadProcSafe()
      Me.SetText("This text was set safely.")
    End Sub

   ' This method demonstrates a pattern for making thread-safe
   ' calls on a Windows Forms control.
   '
   ' If the calling thread is different from the thread that
   ' created the TextBox control, this method creates a
   ' StringArgReturningVoidDelegate and calls itself asynchronously using the
   ' Invoke method.
   '
   ' If the calling thread is the same as the thread that created
    ' the TextBox control, the Text property is set directly.

    Private Sub SetText(ByVal [text] As String)

        ' InvokeRequired required compares the thread ID of the
        ' calling thread to the thread ID of the creating thread.
        ' If these threads are different, it returns true.
        If Me.textBox1.InvokeRequired Then
            Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)
            Me.Invoke(d, New Object() {[text]})
        Else
            Me.textBox1.Text = [text]
        End If
    End Sub

   ' This event handler starts the form's
   ' BackgroundWorker by calling RunWorkerAsync.
   '
   ' The Text property of the TextBox control is set
   ' when the BackgroundWorker raises the RunWorkerCompleted
   ' event.
    Private Sub setTextBackgroundWorkerBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click
        Me.backgroundWorker1.RunWorkerAsync()
    End Sub

   ' This event handler sets the Text property of the TextBox
   ' control. It is called on the thread that created the
   ' TextBox control, so the call is thread-safe.
   '
   ' BackgroundWorker is the preferred way to perform asynchronous
   ' operations.
    Private Sub backgroundWorker1_RunWorkerCompleted( _
    ByVal sender As Object, _
    ByVal e As RunWorkerCompletedEventArgs) _
    Handles backgroundWorker1.RunWorkerCompleted
        Me.textBox1.Text = _
        "This text was set safely by BackgroundWorker."
    End Sub

   #Region "Windows Form Designer generated code"

   Private Sub InitializeComponent()
      Me.textBox1 = New System.Windows.Forms.TextBox()
      Me.setTextUnsafeBtn = New System.Windows.Forms.Button()
      Me.setTextSafeBtn = New System.Windows.Forms.Button()
      Me.setTextBackgroundWorkerBtn = New System.Windows.Forms.Button()
      Me.backgroundWorker1 = New System.ComponentModel.BackgroundWorker()
      Me.SuspendLayout()
      '
      ' textBox1
      '
      Me.textBox1.Location = New System.Drawing.Point(12, 12)
      Me.textBox1.Name = "textBox1"
      Me.textBox1.Size = New System.Drawing.Size(240, 20)
      Me.textBox1.TabIndex = 0
      '
      ' setTextUnsafeBtn
      '
      Me.setTextUnsafeBtn.Location = New System.Drawing.Point(15, 55)
      Me.setTextUnsafeBtn.Name = "setTextUnsafeBtn"
      Me.setTextUnsafeBtn.TabIndex = 1
      Me.setTextUnsafeBtn.Text = "Unsafe Call"
      '
      ' setTextSafeBtn
      '
      Me.setTextSafeBtn.Location = New System.Drawing.Point(96, 55)
      Me.setTextSafeBtn.Name = "setTextSafeBtn"
      Me.setTextSafeBtn.TabIndex = 2
      Me.setTextSafeBtn.Text = "Safe Call"
      '
      ' setTextBackgroundWorkerBtn
      '
      Me.setTextBackgroundWorkerBtn.Location = New System.Drawing.Point(177, 55)
      Me.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn"
      Me.setTextBackgroundWorkerBtn.TabIndex = 3
      Me.setTextBackgroundWorkerBtn.Text = "Safe BW Call"
      '
      ' backgroundWorker1
      '
      '
      ' Form1
      '
      Me.ClientSize = New System.Drawing.Size(268, 96)
      Me.Controls.Add(setTextBackgroundWorkerBtn)
      Me.Controls.Add(setTextSafeBtn)
      Me.Controls.Add(setTextUnsafeBtn)
      Me.Controls.Add(textBox1)
      Me.Name = "Form1"
      Me.Text = "Form1"
      Me.ResumeLayout(False)
      Me.PerformLayout()
   End Sub 'InitializeComponent

   #End Region

   <STAThread()>  _
   Shared Sub Main()
      Application.EnableVisualStyles()
      Application.Run(New Form1())
    End Sub
End Class
```

```cpp
#using <System.dll>
#using <System.Windows.Forms.dll>
#using <System.Drawing.dll>

using namespace System;
using namespace System::ComponentModel;
using namespace System::Threading;
using namespace System::Windows::Forms;

namespace CrossThreadDemo
{
    public ref class Form1 : public Form
    {
        // This delegate enables asynchronous calls for setting
        // the text property on a TextBox control.
        delegate void StringArgReturningVoidDelegate(String^ text);

        // This thread is used to demonstrate both thread-safe and
        // unsafe ways to call a Windows Forms control.
    private:
        Thread^ demoThread;

        // This BackgroundWorker is used to demonstrate the
        // preferred way of performing asynchronous operations.
    private:
        BackgroundWorker^ backgroundWorker1;

    private:
        TextBox^ textBox1;
    private:
        Button^ setTextUnsafeBtn;
    private:
        Button^ setTextSafeBtn;
    private:
        Button^ setTextBackgroundWorkerBtn;

    private:
        System::ComponentModel::IContainer^ components;

    public:
        Form1()
        {
            components = nullptr;
            InitializeComponent();
        }

    protected:
        ~Form1()
        {
            if (components != nullptr)
            {
                delete components;
            }
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in an unsafe way.
    private:
        void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->demoThread =
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));

            this->demoThread->Start();
        }

        // This method is executed on the worker thread and makes
        // an unsafe call on the TextBox control.
    private:
        void ThreadProcUnsafe()
        {
            this->textBox1->Text = "This text was set unsafely.";
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in a thread-safe way.
    private:
        void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->demoThread =
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));

            this->demoThread->Start();
        }

        // This method is executed on the worker thread and makes
        // a thread-safe call on the TextBox control.
    private:
        void ThreadProcSafe()
        {
            this->SetText("This text was set safely.");
        }

        // This method demonstrates a pattern for making thread-safe
        // calls on a Windows Forms control.
        //
        // If the calling thread is different from the thread that
        // created the TextBox control, this method creates a
        // StringArgReturningVoidDelegate and calls itself asynchronously using the
        // Invoke method.
        //
        // If the calling thread is the same as the thread that created
        // the TextBox control, the Text property is set directly.

    private:
        void SetText(String^ text)
        {
            // InvokeRequired required compares the thread ID of the
            // calling thread to the thread ID of the creating thread.
            // If these threads are different, it returns true.
            if (this->textBox1->InvokeRequired)
            {
                StringArgReturningVoidDelegate^ d =
                    gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);
                this->Invoke(d, gcnew array<Object^> { text });
            }
            else
            {
                this->textBox1->Text = text;
            }
        }

        // This event handler starts the form's
        // BackgroundWorker by calling RunWorkerAsync.
        //
        // The Text property of the TextBox control is set
        // when the BackgroundWorker raises the RunWorkerCompleted
        // event.
    private:
        void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->backgroundWorker1->RunWorkerAsync();
        }

        // This event handler sets the Text property of the TextBox
        // control. It is called on the thread that created the
        // TextBox control, so the call is thread-safe.
        //
        // BackgroundWorker is the preferred way to perform asynchronous
        // operations.

    private:
        void backgroundWorker1_RunWorkerCompleted(
            Object^ sender,
            RunWorkerCompletedEventArgs^ e)
        {
            this->textBox1->Text =
                "This text was set safely by BackgroundWorker.";
        }

        #pragma region Windows Form Designer generated code

    private:
        void InitializeComponent()
        {
            this->textBox1 = gcnew System::Windows::Forms::TextBox();
            this->setTextUnsafeBtn = gcnew System::Windows::Forms::Button();
            this->setTextSafeBtn = gcnew System::Windows::Forms::Button();
            this->setTextBackgroundWorkerBtn =
                gcnew System::Windows::Forms::Button();
            this->backgroundWorker1 =
                gcnew System::ComponentModel::BackgroundWorker();
            this->SuspendLayout();
            //
            // textBox1
            //
            this->textBox1->Location = System::Drawing::Point(12, 12);
            this->textBox1->Name = "textBox1";
            this->textBox1->Size = System::Drawing::Size(240, 20);
            this->textBox1->TabIndex = 0;
            //
            // setTextUnsafeBtn
            //
            this->setTextUnsafeBtn->Location = System::Drawing::Point(15, 55);
            this->setTextUnsafeBtn->Name = "setTextUnsafeBtn";
            this->setTextUnsafeBtn->TabIndex = 1;
            this->setTextUnsafeBtn->Text = "Unsafe Call";
            this->setTextUnsafeBtn->Click +=
                gcnew System::EventHandler(
                this,&Form1::setTextUnsafeBtn_Click);
            //
            // setTextSafeBtn
            //
            this->setTextSafeBtn->Location = System::Drawing::Point(96, 55);
            this->setTextSafeBtn->Name = "setTextSafeBtn";
            this->setTextSafeBtn->TabIndex = 2;
            this->setTextSafeBtn->Text = "Safe Call";
            this->setTextSafeBtn->Click +=
                gcnew System::EventHandler(this,&Form1::setTextSafeBtn_Click);
            //
            // setTextBackgroundWorkerBtn
            //
            this->setTextBackgroundWorkerBtn->Location =
                System::Drawing::Point(177, 55);
            this->setTextBackgroundWorkerBtn->Name =
                "setTextBackgroundWorkerBtn";
            this->setTextBackgroundWorkerBtn->TabIndex = 3;
            this->setTextBackgroundWorkerBtn->Text = "Safe BW Call";
            this->setTextBackgroundWorkerBtn->Click +=
                gcnew System::EventHandler(
                this,&Form1::setTextBackgroundWorkerBtn_Click);
            //
            // backgroundWorker1
            //
            this->backgroundWorker1->RunWorkerCompleted +=
                gcnew System::ComponentModel::RunWorkerCompletedEventHandler(
                this,&Form1::backgroundWorker1_RunWorkerCompleted);
            //
            // Form1
            //
            this->ClientSize = System::Drawing::Size(268, 96);
            this->Controls->Add(this->setTextBackgroundWorkerBtn);
            this->Controls->Add(this->setTextSafeBtn);
            this->Controls->Add(this->setTextUnsafeBtn);
            this->Controls->Add(this->textBox1);
            this->Name = "Form1";
            this->Text = "Form1";
            this->ResumeLayout(false);
            this->PerformLayout();

        }

        #pragma endregion
    };
}

[STAThread]
int main()
{
    Application::EnableVisualStyles();
    Application::Run(gcnew CrossThreadDemo::Form1());
}
```

<span data-ttu-id="788c6-149">Wenn Sie die Anwendung ausführen und auf die Schaltfläche **Unsafe Call** klicken, wird sofort "Written by the main thread" im Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="788c6-149">When you run the application and click the **Unsafe Call** button, you immediately see "Written by the main thread" in the text box.</span></span> <span data-ttu-id="788c6-150">Wenn zwei Sekunden später der unsichere Aufruf versucht wird, gibt der Visual Studio-Debugger an, dass eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="788c6-150">Two seconds later, when the unsafe call is attempted, the Visual Studio debugger indicates that an exception occurred.</span></span> <span data-ttu-id="788c6-151">Der Debugger hält bei der Zeile im Hintergrundthread an, die versucht hat, direkt in das Textfeld zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="788c6-151">The debugger stops at the line in the background thread that attempted to write directly to the text box.</span></span> <span data-ttu-id="788c6-152">Sie müssen die Anwendung neu starten, um die anderen zwei Schaltflächen zu testen.</span><span class="sxs-lookup"><span data-stu-id="788c6-152">You will have to restart the application to test the other two buttons.</span></span> <span data-ttu-id="788c6-153">Wenn Sie auf die Schaltfläche **Safe Call** klicken, wird "Written by the main thread" im Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="788c6-153">When you click the **Safe Call** button, "Written by the main thread" appears in the text box.</span></span> <span data-ttu-id="788c6-154">Zwei Sekunden später wird das Textfeld auf "Written by the background thread (Invoke)" festgelegt. Dadurch wird angegeben, dass die <xref:System.Windows.Forms.Control.Invoke%2A> -Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="788c6-154">Two seconds later, the text box is set to "Written by the background thread (Invoke)", which indicates that the <xref:System.Windows.Forms.Control.Invoke%2A> method was called.</span></span> <span data-ttu-id="788c6-155">Wenn Sie auf die Schaltfläche **Safe BW Call** klicken, wird "Written by the main thread" im Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="788c6-155">When you click the **Safe BW Call** button, "Written by the main thread" appears in the text box.</span></span> <span data-ttu-id="788c6-156">Zwei Sekunden später wird das Textfeld auf "Written by the main thread after the background thread completed" festgelegt, Dadurch wird angegeben, dass der Handler für das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignis von <xref:System.ComponentModel.BackgroundWorker> aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="788c6-156">Two seconds later, the text box is set to "Written by the main thread after the background thread completed", which indicates that the handler for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event of <xref:System.ComponentModel.BackgroundWorker> was called.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="788c6-157">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="788c6-157">Robust Programming</span></span>

> [!CAUTION]
> <span data-ttu-id="788c6-158">Wenn Sie eine beliebige Art von Multithreading verwenden, kann Ihr Code sehr ernsthaften und komplexen Fehlern ausgesetzt sein.</span><span class="sxs-lookup"><span data-stu-id="788c6-158">When you use multithreading of any sort, your code can be exposed to very serious and complex bugs.</span></span> <span data-ttu-id="788c6-159">Weitere Informationen finden Sie unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../../docs/standard/threading/managed-threading-best-practices.md), bevor Sie eine Lösung implementieren, die Multithreading verwendet.</span><span class="sxs-lookup"><span data-stu-id="788c6-159">For more information, see [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before you implement any solution that uses multithreading.</span></span>

## <a name="see-also"></a><span data-ttu-id="788c6-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="788c6-160">See Also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="788c6-161">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="788c6-161">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="788c6-162">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="788c6-162">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="788c6-163">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="788c6-163">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="788c6-164">Windows Forms und nicht verwaltete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="788c6-164">Windows Forms and Unmanaged Applications</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
