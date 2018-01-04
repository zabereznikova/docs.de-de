---
title: 'Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente'
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
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd04a44e6f6e3df26a643a8937e20e232e7471a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="8e1be-102">Gewusst wie: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="8e1be-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="8e1be-103">Die [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) Komponente ermöglicht Benutzern das Auswählen einer Schriftart sowie deren Anzeige ändern, z. B. Gewichtung und Größe.</span><span class="sxs-lookup"><span data-stu-id="8e1be-103">The [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="8e1be-104">Klicken Sie im Dialogfeld ausgewählte Schriftart wird zurückgegeben, der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8e1be-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="8e1be-105">Daher ist das Nutzen der vom Benutzer ausgewählten Schriftart so einfach wie eine Eigenschaft zu lesen.</span><span class="sxs-lookup"><span data-stu-id="8e1be-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="8e1be-106">Auswählen von Schriftarteigenschaften, die mit der FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="8e1be-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="8e1be-107">Anzeigen des Dialogfelds mit den <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8e1be-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="8e1be-108">Verwenden der <xref:System.Windows.Forms.DialogResult> -Eigenschaft können Sie bestimmen, wie das Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8e1be-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="8e1be-109">Verwenden der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft, um die gewünschte Schriftart fest.</span><span class="sxs-lookup"><span data-stu-id="8e1be-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="8e1be-110">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine <xref:System.Windows.Forms.FontDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="8e1be-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="8e1be-111">Wenn eine Schriftart ausgewählt wurde und der Benutzer klickt **OK**, die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft von einem <xref:System.Windows.Forms.TextBox> Steuerelement, das auf dem Formular auf die ausgewählte Schriftart festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8e1be-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="8e1be-112">Im Beispiel wird vorausgesetzt, das Formular verfügt über eine <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.TextBox> -Steuerelement, und ein <xref:System.Windows.Forms.FontDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="8e1be-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="8e1be-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="8e1be-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8e1be-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e1be-114">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="8e1be-115">FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="8e1be-115">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
