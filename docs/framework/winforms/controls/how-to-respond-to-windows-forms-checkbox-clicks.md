---
title: 'Vorgehensweise: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms'
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
ms.openlocfilehash: ce616f45ceaa3db117c6981d2987ac09bba7b3fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319897"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="9ab0b-102">Vorgehensweise: Reagieren auf das Klicken auf Kontrollkästchen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab0b-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="9ab0b-103">Jedes Mal, wenn ein Benutzer klickt ein Windows Forms <xref:System.Windows.Forms.CheckBox> -Steuerelement, das <xref:System.Windows.Forms.Control.Click> Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="9ab0b-104">Sie können Ihre Anwendung zum Ausführen einer Aktion, die je nach Zustand des Kontrollkästchens programmieren.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="9ab0b-105">Um auf das Klicken auf Kontrollkästchen zu reagieren</span><span class="sxs-lookup"><span data-stu-id="9ab0b-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="9ab0b-106">In der <xref:System.Windows.Forms.Control.Click> -Ereignishandler der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft, um den Zustand des Steuerelements zu bestimmen, und führen Sie alle erforderlichen Aktionen.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="9ab0b-107">Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.CheckBox> -Steuerelement, jedem Klick wird separat verarbeitet werden, d. h. die <xref:System.Windows.Forms.CheckBox> Steuerelement unterstützt nicht das Doppelklickereignis.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ab0b-108">Wenn die <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> -Eigenschaft ist `true` (Standardeinstellung), die <xref:System.Windows.Forms.CheckBox> automatisch aktiviert oder deaktiviert werden, wenn darauf geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="9ab0b-109">Andernfalls müssen Sie manuell festlegen der <xref:System.Windows.Forms.CheckBox.Checked%2A> Eigenschaft bei der <xref:System.Windows.Forms.Control.Click> Ereignis tritt auf.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="9ab0b-110">Sie können auch die <xref:System.Windows.Forms.CheckBox> Steuerelement, um zu bestimmen, welche Aktion.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="9ab0b-111">Um zu bestimmen, Aktion, wenn das Kontrollkästchen geklickt wird</span><span class="sxs-lookup"><span data-stu-id="9ab0b-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="9ab0b-112">Eine Case-Anweisung den Wert der Abfragen verwenden die <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft, um eine Aktion zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="9ab0b-113">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> Eigenschaft kann drei mögliche Werte, die das Feld, das zu überprüfende darstellen, zurück Kontrollkästchen deaktiviert wird, oder ein Drittanbieterserver unbestimmten Zustand, in dem das Feld angezeigt wird, mit einem abgeblendet Darstellung an, dass die Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="9ab0b-114">Wenn die <xref:System.Windows.Forms.CheckBox.ThreeState%2A> -Eigenschaftensatz auf `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> -Eigenschaft gibt `true` für beide <xref:System.Windows.Forms.CheckState.Checked> und <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="9ab0b-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab0b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ab0b-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="9ab0b-116">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9ab0b-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="9ab0b-117">Vorgehensweise: Festlegen von Optionen mit CheckBox-Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab0b-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="9ab0b-118">CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9ab0b-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
