---
title: 'Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 0a7a2475891488d1fdd60f0db4a483c144a73f0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947847"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="74969-102">Vorgehensweise: Senden von Daten an das aktive untergeordnete MDI-Element</span><span class="sxs-lookup"><span data-stu-id="74969-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="74969-103">Im Kontext von [MDI-Anwendungen (Multiple Document Interface)](multiple-document-interface-mdi-applications.md)müssen häufig Daten an das aktive untergeordnete Fenster gesendet werden, z. b., wenn der Benutzerdaten aus der Zwischenablage in eine MDI-Anwendung einfügt.</span><span class="sxs-lookup"><span data-stu-id="74969-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74969-104">Informationen zum Überprüfen, welches untergeordnete Fenster den Fokus besitzt und seinen Inhalt in die Zwischenablage sendet, finden Sie unter [bestimmen des aktiven untergeordneten MDI](how-to-determine-the-active-mdi-child.md)-Elements.</span><span class="sxs-lookup"><span data-stu-id="74969-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="74969-105">So senden Sie Daten aus der Zwischenablage an das aktive untergeordnete MDI-Fenster</span><span class="sxs-lookup"><span data-stu-id="74969-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="74969-106">Kopieren Sie den Text in der Zwischenablage in eine Methode in das aktive Steuerelement des aktiven untergeordneten Formulars.</span><span class="sxs-lookup"><span data-stu-id="74969-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="74969-107">In diesem Beispiel wird davon ausgegangen, dass ein übergeordnetes`Form1`MDI-Formular () vorhanden ist, das mindestens ein <xref:System.Windows.Forms.RichTextBox> untergeordnetes MDI-Fenster mit einem-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74969-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="74969-108">Weitere Informationen finden Sie unter [Erstellen von übergeordneten MDI-Formularen](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="74969-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="74969-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74969-109">See also</span></span>

- [<span data-ttu-id="74969-110">MDI-Anwendungen (Multiple Document Interface)</span><span class="sxs-lookup"><span data-stu-id="74969-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="74969-111">Vorgehensweise: Übergeordnete MDI-Formulare erstellen</span><span class="sxs-lookup"><span data-stu-id="74969-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="74969-112">Vorgehensweise: Erstellen von untergeordneten MDI-Formularen</span><span class="sxs-lookup"><span data-stu-id="74969-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="74969-113">Vorgehensweise: Festlegen des aktiven untergeordneten MDI-Elements</span><span class="sxs-lookup"><span data-stu-id="74969-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="74969-114">Vorgehensweise: Untergeordnete MDI-Formulare anordnen</span><span class="sxs-lookup"><span data-stu-id="74969-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
