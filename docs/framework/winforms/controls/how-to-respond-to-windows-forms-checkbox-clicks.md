---
title: Reagieren auf CheckBox-Klicks
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735660"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="a1412-102">Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1412-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="a1412-103">Wenn ein Benutzer auf eine Windows Forms <xref:System.Windows.Forms.CheckBox>-Steuerelement klickt, tritt das <xref:System.Windows.Forms.Control.Click>-Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="a1412-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="a1412-104">Sie können Ihre Anwendung so programmieren, dass je nach Zustand des Kontrollkästchens Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a1412-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="a1412-105">So reagieren Sie auf CheckBox-Klicks</span><span class="sxs-lookup"><span data-stu-id="a1412-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="a1412-106">Verwenden Sie im <xref:System.Windows.Forms.Control.Click>-Ereignishandler die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft, um den Zustand des Steuer Elements zu bestimmen und alle notwendigen Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a1412-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a1412-107">Wenn der Benutzer versucht, auf das <xref:System.Windows.Forms.CheckBox>-Steuerelement zu doppelklicken, wird jeder Klick separat verarbeitet. Das <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt das Doppelklick Ereignis also nicht.</span><span class="sxs-lookup"><span data-stu-id="a1412-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a1412-108">Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A>-Eigenschaft `true` (Standardeinstellung) ist, wird die <xref:System.Windows.Forms.CheckBox> automatisch ausgewählt oder gelöscht, wenn darauf geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="a1412-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="a1412-109">Andernfalls müssen Sie die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft manuell festlegen, wenn das <xref:System.Windows.Forms.Control.Click> Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="a1412-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="a1412-110">Sie können auch das <xref:System.Windows.Forms.CheckBox>-Steuerelement verwenden, um eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a1412-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="a1412-111">So bestimmen Sie eine Vorgehensweise, wenn auf ein Kontrollkästchen geklickt wird</span><span class="sxs-lookup"><span data-stu-id="a1412-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="a1412-112">Verwenden Sie eine Case-Anweisung, um den Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft abzufragen, um eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a1412-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="a1412-113">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>-Eigenschaft auf `true`festgelegt ist, gibt die <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft möglicherweise drei mögliche Werte zurück, die das Kontrollkästchen darstellen, das Kontrollkästchen deaktiviert ist, oder einen dritten unbestimmten Zustand, in dem das Feld mit einer Abbild Darstellung angezeigt wird, um anzugeben, dass die Option nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a1412-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a1412-114">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A>-Eigenschaft auf `true`festgelegt ist, gibt die <xref:System.Windows.Forms.CheckBox.Checked%2A>-Eigenschaft `true` für <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>zurück.</span><span class="sxs-lookup"><span data-stu-id="a1412-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1412-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1412-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="a1412-116">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a1412-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a1412-117">Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1412-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="a1412-118">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a1412-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
