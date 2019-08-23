---
title: 'Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit'
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
ms.openlocfilehash: 87ad4c957ac5b99438684d398a0c5ad7d126c406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925047"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="12e1b-102">Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="12e1b-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="12e1b-103">Häufige Aufgaben bei der Anwendungsentwicklung sind das Hinzufügen von Steuerelementen zu und das Entfernen von Steuerelementen aus einem beliebigen <xref:System.Windows.Forms.Panel> Container <xref:System.Windows.Forms.GroupBox> Steuerelement in Ihren Formularen (z. b. das-Steuerelement oder das-Steuerelement)</span><span class="sxs-lookup"><span data-stu-id="12e1b-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="12e1b-104">Zur Entwurfszeit können Steuerelemente direkt auf ein Panel oder Gruppenfeld gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="12e1b-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="12e1b-105">Zur Laufzeit verwalten diese Steuerelemente eine `Controls`-Auflistung, die protokolliert, welche Steuerelemente darauf platziert werden.</span><span class="sxs-lookup"><span data-stu-id="12e1b-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12e1b-106">Das folgende Codebeispiel gilt für jedes Steuerelement, das eine Auflistung von Steuerelementen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="12e1b-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="12e1b-107">So fügen Sie ein Steuerelement programmgesteuert zu einer Auflistung hinzu</span><span class="sxs-lookup"><span data-stu-id="12e1b-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="12e1b-108">Erstellen Sie eine Instanz des Steuerelements, das hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="12e1b-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="12e1b-109">Legen Sie die Eigenschaften des neuen Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="12e1b-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="12e1b-110">Fügen Sie der `Controls`-Auflistung des übergeordneten Elements das Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="12e1b-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="12e1b-111">Im folgenden Codebeispiel wird gezeigt, wie eine Instanz des <xref:System.Windows.Forms.Button> -Steuer Elements erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="12e1b-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="12e1b-112">Hierfür ist ein Formular mit einem <xref:System.Windows.Forms.Panel> -Steuerelement erforderlich, und die Ereignis Behandlungsmethode für die Schalt `NewPanelButton_Click`Fläche, die erstellt wird, ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="12e1b-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="12e1b-113">So entfernen Sie Steuerelemente programmgesteuert aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="12e1b-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="12e1b-114">Entfernen Sie den Ereignishandler aus dem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="12e1b-114">Remove the event handler from the event.</span></span> <span data-ttu-id="12e1b-115">Verwenden Sie in Visual Basic das [RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) -Anweisungs Schlüsselwort. verwenden C#Sie in den [Operator-=](../../../csharp/language-reference/operators/subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="12e1b-115">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="12e1b-116">Verwenden Sie die Methode `Remove`, um das gewünschte Steuerelement aus der `Controls`-Auflistung des Panels zu löschen.</span><span class="sxs-lookup"><span data-stu-id="12e1b-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="12e1b-117">Ruft die <xref:System.Windows.Forms.Control.Dispose%2A> -Methode auf, um alle vom-Steuerelement verwendeten Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="12e1b-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12e1b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12e1b-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="12e1b-119">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="12e1b-119">Panel Control</span></span>](panel-control-windows-forms.md)
