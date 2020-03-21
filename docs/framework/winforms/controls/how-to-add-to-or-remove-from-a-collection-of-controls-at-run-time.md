---
title: 'Gewusst wie: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit'
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
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182287"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="745b5-102">Gewusst wie: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="745b5-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="745b5-103">Häufige Aufgaben in der Anwendungsentwicklung sind das Hinzufügen von Steuerelementen zu <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> steuerelementen und das Entfernen von Steuerelementen aus allen Containersteuerelementen in Ihren Formularen (z. B. das oder-Steuerelement oder sogar das Formular selbst).</span><span class="sxs-lookup"><span data-stu-id="745b5-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="745b5-104">Zur Entwurfszeit können Steuerelemente direkt auf ein Panel oder Gruppenfeld gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="745b5-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="745b5-105">Zur Laufzeit verwalten diese Steuerelemente eine `Controls`-Auflistung, die protokolliert, welche Steuerelemente darauf platziert werden.</span><span class="sxs-lookup"><span data-stu-id="745b5-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="745b5-106">Das folgende Codebeispiel gilt für jedes Steuerelement, das eine Auflistung von Steuerelementen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="745b5-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="745b5-107">So fügen Sie ein Steuerelement programmgesteuert zu einer Auflistung hinzu</span><span class="sxs-lookup"><span data-stu-id="745b5-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="745b5-108">Erstellen Sie eine Instanz des Steuerelements, das hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="745b5-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="745b5-109">Legen Sie die Eigenschaften des neuen Steuerelements fest.</span><span class="sxs-lookup"><span data-stu-id="745b5-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="745b5-110">Fügen Sie der `Controls`-Auflistung des übergeordneten Elements das Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="745b5-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="745b5-111">Das folgende Codebeispiel zeigt, wie <xref:System.Windows.Forms.Button> eine Instanz des Steuerelements erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="745b5-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="745b5-112">Es erfordert ein <xref:System.Windows.Forms.Panel> Formular mit einem Steuerelement und dass die `NewPanelButton_Click`Ereignisbehandlungsmethode für die zu erstellende Schaltfläche bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="745b5-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
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
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="745b5-113">So entfernen Sie Steuerelemente programmgesteuert aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="745b5-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="745b5-114">Entfernen Sie den Ereignishandler aus dem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="745b5-114">Remove the event handler from the event.</span></span> <span data-ttu-id="745b5-115">Verwenden Sie in Visual Basic das [Schlüsselwort RemoveHandler-Anweisung.](../../../visual-basic/language-reference/statements/removehandler-statement.md) verwenden Sie den [Operator -=](../../../csharp/language-reference/operators/subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="745b5-115">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="745b5-116">Verwenden Sie die Methode `Remove`, um das gewünschte Steuerelement aus der `Controls`-Auflistung des Panels zu löschen.</span><span class="sxs-lookup"><span data-stu-id="745b5-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="745b5-117">Rufen <xref:System.Windows.Forms.Control.Dispose%2A> Sie die Methode auf, um alle vom Steuerelement verwendeten Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="745b5-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="745b5-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="745b5-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="745b5-119">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="745b5-119">Panel Control</span></span>](panel-control-windows-forms.md)
