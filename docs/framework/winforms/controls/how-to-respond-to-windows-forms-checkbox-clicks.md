---
title: "Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe7826d1081f69bae1d220c22447886511cf58e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="ec6d5-102">Gewusst wie: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec6d5-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="ec6d5-103">Wenn ein Benutzer einer Windows Forms klickt <xref:System.Windows.Forms.CheckBox> -Steuerelement, das <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="ec6d5-104">Programmieren Sie Ihre Anwendung eine Aktion, die je nach Zustand des Kontrollkästchens auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="ec6d5-105">So reagieren Sie auf das Klicken auf Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="ec6d5-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="ec6d5-106">In der <xref:System.Windows.Forms.Control.Click> -Ereignishandler der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft zum Bestimmen der Zustand des Steuerelements, und führen alle erforderlichen Aktionen.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="ec6d5-107">Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.CheckBox> -Steuerelement, jedem Mausklick wird separat verarbeitet werden, d. h., die <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt nicht das Doppelklickereignis.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec6d5-108">Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> Eigenschaft ist `true` (Standard), die <xref:System.Windows.Forms.CheckBox> automatisch aktiviert oder deaktiviert werden, wenn darauf geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="ec6d5-109">Andernfalls müssen Sie manuell festlegen der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft bei der <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="ec6d5-110">Sie können auch die <xref:System.Windows.Forms.CheckBox> Steuerelement um eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="ec6d5-111">Um zu bestimmen, Aktion, wenn Sie das Kontrollkästchen geklickt wird</span><span class="sxs-lookup"><span data-stu-id="ec6d5-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="ec6d5-112">Eine Case-Anweisung den Wert der Abfragen verwenden die <xref:System.Windows.Forms.CheckBox.CheckState%2A> -Eigenschaft können Sie eine Vorgehensweise zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="ec6d5-113">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft gelegten drei mögliche Werten, die das zu überprüfende Feld darstellen, Feld deaktiviert wird, oder eine dritte unbestimmten Zustand, in dem Feld angezeigt wird, mit einem abgeblendet Darstellung an, dass die Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="ec6d5-114">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft gibt `true` für beide <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="ec6d5-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec6d5-115">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="ec6d5-116">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ec6d5-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="ec6d5-117">Gewusst wie: Festlegen von Optionen mit CheckBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec6d5-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="ec6d5-118">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ec6d5-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
