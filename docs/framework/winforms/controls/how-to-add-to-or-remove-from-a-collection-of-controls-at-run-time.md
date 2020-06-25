---
title: 'Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit'
description: Erfahren Sie, wie Sie Steuerelemente zu einem beliebigen Container Steuerelement in Ihren Formularen hinzufügen und entfernen, z. b. das Panel-Steuerelement oder das GroupBox-Steuerelement oder sogar das Formular selbst.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 6c3f2d1f42b130de4d808871265b50510cfb8f47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325867"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="1b091-103">Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1b091-103">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="1b091-104">Häufige Aufgaben bei der Anwendungsentwicklung sind das Hinzufügen von Steuerelementen zu und das Entfernen von Steuerelementen aus einem beliebigen Container Steuerelement in Ihren Formularen (z. b. das- <xref:System.Windows.Forms.Panel> Steuerelement oder <xref:System.Windows.Forms.GroupBox> das-Steuerelement)</span><span class="sxs-lookup"><span data-stu-id="1b091-104">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="1b091-105">Zur Entwurfszeit können Steuerelemente direkt auf ein Panel oder Gruppenfeld gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1b091-105">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="1b091-106">Zur Laufzeit verwalten diese Steuerelemente eine `Controls`-Auflistung, die protokolliert, welche Steuerelemente darauf platziert werden.</span><span class="sxs-lookup"><span data-stu-id="1b091-106">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b091-107">Das folgende Codebeispiel gilt für jedes Steuerelement, das eine Auflistung von Steuerelementen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1b091-107">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="1b091-108">So fügen Sie ein Steuerelement programmgesteuert zu einer Auflistung hinzu</span><span class="sxs-lookup"><span data-stu-id="1b091-108">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="1b091-109">Erstellen Sie eine Instanz des Steuerelements, das hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b091-109">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="1b091-110">Legen Sie die Eigenschaften des neuen Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="1b091-110">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="1b091-111">Fügen Sie der `Controls`-Auflistung des übergeordneten Elements das Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="1b091-111">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="1b091-112">Im folgenden Codebeispiel wird gezeigt, wie eine Instanz des-Steuer Elements erstellt wird <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="1b091-112">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="1b091-113">Hierfür ist ein Formular mit einem <xref:System.Windows.Forms.Panel> -Steuerelement erforderlich, und die Ereignis Behandlungsmethode für die Schaltfläche, die erstellt wird, `NewPanelButton_Click` ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1b091-113">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="1b091-114">So entfernen Sie Steuerelemente programmgesteuert aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="1b091-114">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="1b091-115">Entfernen Sie den Ereignishandler aus dem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1b091-115">Remove the event handler from the event.</span></span> <span data-ttu-id="1b091-116">Verwenden Sie in Visual Basic das [RemoveHandler-Anweisungs](../../../visual-basic/language-reference/statements/removehandler-statement.md) Schlüsselwort. Verwenden Sie in c# den [Operator-=](../../../csharp/language-reference/operators/subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1b091-116">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="1b091-117">Verwenden Sie die Methode `Remove`, um das gewünschte Steuerelement aus der `Controls`-Auflistung des Panels zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1b091-117">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="1b091-118">Ruft die- <xref:System.Windows.Forms.Control.Dispose%2A> Methode auf, um alle vom-Steuerelement verwendeten Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="1b091-118">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b091-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b091-119">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="1b091-120">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1b091-120">Panel Control</span></span>](panel-control-windows-forms.md)
