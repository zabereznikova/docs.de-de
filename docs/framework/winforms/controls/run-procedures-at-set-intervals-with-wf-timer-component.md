---
title: Prozeduren in festgelegten Intervallen mit Timer-Komponente ausführen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: dcc88beee947e2a83b426dcd2f3fd9d70c20fb67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743110"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="cc802-102">Gewusst wie: Ausführen von Prozeduren in festgelegten Abständen mit der Timer-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc802-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="cc802-103">In einigen Fällen möchten Sie möglicherweise eine Prozedur erstellen, die entweder in bestimmten Zeitintervallen bis zum Ende einer Schleife oder nach Ablauf eines festgelegten Zeitintervalls ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc802-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="cc802-104">Die <xref:System.Windows.Forms.Timer>-Komponente ermöglicht eine solche Prozedur.</span><span class="sxs-lookup"><span data-stu-id="cc802-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="cc802-105">Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="cc802-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="cc802-106">Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="cc802-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc802-107">Die Verwendung der <xref:System.Windows.Forms.Timer>-Komponente unterliegt einigen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="cc802-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="cc802-108">Weitere Informationen finden Sie unter [Einschränkungen der Interval-Eigenschaft der Windows Forms Timer-Komponente](limitations-of-the-timer-component-interval-property.md).</span><span class="sxs-lookup"><span data-stu-id="cc802-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="cc802-109">So führen Sie eine Prozedur in festgelegten Intervallen mit der Timer-Komponente aus</span><span class="sxs-lookup"><span data-stu-id="cc802-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="cc802-110">Fügen Sie Ihrem Formular einen <xref:System.Windows.Forms.Timer> hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc802-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="cc802-111">Im folgenden Beispielabschnitt finden Sie eine Abbildung zur entsprechenden programmgesteuerten Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="cc802-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="cc802-112">Visual Studio unterstützt auch das Hinzufügen von Komponenten zu einem Formular.</span><span class="sxs-lookup"><span data-stu-id="cc802-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="cc802-113">Siehe auch Gewusst [wie: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cc802-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="cc802-114">Legen Sie die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft (in Millisekunden) für den Timer fest.</span><span class="sxs-lookup"><span data-stu-id="cc802-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="cc802-115">Diese Eigenschaft bestimmt, in welchem Zeitabstand die Prozedur erneut ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc802-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cc802-116">Je öfter ein Timerereignis auftritt, desto mehr Prozessorzeit wird für die Reaktion auf das Ereignis aufgewendet.</span><span class="sxs-lookup"><span data-stu-id="cc802-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="cc802-117">Dadurch kann sich die Gesamtleistung verringern.</span><span class="sxs-lookup"><span data-stu-id="cc802-117">This can slow down overall performance.</span></span> <span data-ttu-id="cc802-118">Legen Sie kein kleineres Intervall als erforderlich fest.</span><span class="sxs-lookup"><span data-stu-id="cc802-118">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="cc802-119">Schreiben Sie den entsprechenden Code in den <xref:System.Windows.Forms.Timer.Tick> Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="cc802-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="cc802-120">Der in dieses Ereignis geschriebene Code wird in dem in der <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft angegebenen Intervall ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc802-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="cc802-121">Legen Sie die <xref:System.Windows.Forms.Timer.Enabled%2A>-Eigenschaft auf `true` fest, um den Timer zu starten.</span><span class="sxs-lookup"><span data-stu-id="cc802-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="cc802-122">Das <xref:System.Windows.Forms.Timer.Tick>-Ereignis tritt nun ein und führt die Prozedur im festgelegten Intervall aus.</span><span class="sxs-lookup"><span data-stu-id="cc802-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="cc802-123">Legen Sie die <xref:System.Windows.Forms.Timer.Enabled%2A>-Eigenschaft zu gegebener Zeit auf `false` fest, um die weitere Ausführung der Prozedur zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="cc802-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="cc802-124">Das Festlegen des Intervalls auf `0` bewirkt nicht, dass der Timer angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="cc802-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc802-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc802-125">Example</span></span>  
 <span data-ttu-id="cc802-126">In diesem ersten Codebeispiel wird die Tageszeit in 1-Sekunden-Schritten erfasst.</span><span class="sxs-lookup"><span data-stu-id="cc802-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="cc802-127">Darin werden Komponenten vom Typ <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> und <xref:System.Windows.Forms.Timer> in einem Formular verwendet.</span><span class="sxs-lookup"><span data-stu-id="cc802-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="cc802-128">Die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft ist auf 1000 (entspricht einer Sekunde) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc802-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="cc802-129">Im <xref:System.Windows.Forms.Timer.Tick>-Ereignis ist die Beschriftung der Label-Komponente auf die aktuelle Zeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc802-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="cc802-130">Wenn Sie auf die Schaltfläche klicken, wird die <xref:System.Windows.Forms.Timer.Enabled%2A>-Eigenschaft auf `false` festgelegt, sodass der Zeitgeber die Beschriftung der Label-Komponente nicht mehr aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cc802-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="cc802-131">Das folgende Codebeispiel erfordert, dass Sie über ein Formular mit einem <xref:System.Windows.Forms.Button>-Steuerelement namens `Button1`, ein <xref:System.Windows.Forms.Timer>-Steuerelement mit dem Namen `Timer1`und ein <xref:System.Windows.Forms.Label>-Steuerelement namens `Label1`verfügen.</span><span class="sxs-lookup"><span data-stu-id="cc802-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="cc802-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc802-132">Example</span></span>  
 <span data-ttu-id="cc802-133">In diesem zweiten Codebeispiel wird eine Prozedur alle 600 Millisekunden bis zum Ende einer Schleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cc802-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="cc802-134">Das folgende Codebeispiel erfordert, dass Sie über ein Formular mit einem <xref:System.Windows.Forms.Button>-Steuerelement namens `Button1`, ein <xref:System.Windows.Forms.Timer>-Steuerelement mit dem Namen `Timer1`und ein <xref:System.Windows.Forms.Label>-Steuerelement namens `Label1`verfügen.</span><span class="sxs-lookup"><span data-stu-id="cc802-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc802-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc802-135">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="cc802-136">Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="cc802-136">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="cc802-137">Übersicht über die Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="cc802-137">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
