---
title: Reagieren auf CheckBox-Klicks
description: Erfahren Sie, wie Sie Ihre Windows Forms Anwendung programmieren, um je nach Zustand des Kontrollkästchens Aktionen auszuführen.
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
ms.openlocfilehash: 58944bc421f990343b6c58484aaab3d79c8bda5e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174496"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="d131e-103">Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d131e-103">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="d131e-104">Wenn ein Benutzer auf ein Windows Forms-Steuerelement klickt <xref:System.Windows.Forms.CheckBox> , tritt das- <xref:System.Windows.Forms.Control.Click> Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="d131e-104">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="d131e-105">Sie können Ihre Anwendung so programmieren, dass je nach Zustand des Kontrollkästchens Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d131e-105">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="d131e-106">So reagieren Sie auf CheckBox-Klicks</span><span class="sxs-lookup"><span data-stu-id="d131e-106">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="d131e-107"><xref:System.Windows.Forms.Control.Click>Verwenden Sie im-Ereignishandler die <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft, um den Zustand des Steuer Elements zu bestimmen und alle notwendigen Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d131e-107">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="d131e-108">Wenn der Benutzer versucht, auf das Steuerelement zu doppelklicken <xref:System.Windows.Forms.CheckBox> , wird jeder Klick separat verarbeitet, d. h <xref:System.Windows.Forms.CheckBox> ., das Steuerelement unterstützt das Doppelklick Ereignis nicht.</span><span class="sxs-lookup"><span data-stu-id="d131e-108">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d131e-109">Wenn die- <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> Eigenschaft ist `true` (Standardeinstellung), <xref:System.Windows.Forms.CheckBox> wird automatisch ausgewählt oder gelöscht, wenn darauf geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="d131e-109">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="d131e-110">Andernfalls müssen Sie die-Eigenschaft manuell festlegen, <xref:System.Windows.Forms.CheckBox.Checked%2A> Wenn das- <xref:System.Windows.Forms.Control.Click> Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="d131e-110">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="d131e-111">Sie können auch das- <xref:System.Windows.Forms.CheckBox> Steuerelement verwenden, um eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d131e-111">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="d131e-112">So bestimmen Sie eine Vorgehensweise, wenn auf ein Kontrollkästchen geklickt wird</span><span class="sxs-lookup"><span data-stu-id="d131e-112">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="d131e-113">Verwenden Sie eine Case-Anweisung, um den Wert der-Eigenschaft abzufragen <xref:System.Windows.Forms.CheckBox.CheckState%2A> , um eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d131e-113">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="d131e-114">Wenn die- <xref:System.Windows.Forms.CheckBox.ThreeState%2A> Eigenschaft auf festgelegt ist `true` , gibt die- <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft möglicherweise drei mögliche Werte zurück, die das Kontrollkästchen darstellen, das Kontrollkästchen deaktiviert ist, oder einen dritten unbestimmten Zustand, in dem das Feld mit einer Abbild Darstellung angezeigt wird, um anzugeben, dass die Option nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d131e-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="d131e-115">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaft auf festgelegt ist `true` , <xref:System.Windows.Forms.CheckBox.Checked%2A> gibt die `true` -Eigenschaft sowohl für <xref:System.Windows.Forms.CheckState.Checked> als auch für zurück <xref:System.Windows.Forms.CheckState.Indeterminate> .</span><span class="sxs-lookup"><span data-stu-id="d131e-115">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d131e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d131e-116">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="d131e-117">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d131e-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d131e-118">Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d131e-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="d131e-119">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d131e-119">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
