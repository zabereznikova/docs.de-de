---
title: 'Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 98b52e914a891baec0b52dcc7b38d4f9f2198c90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539550"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="75968-102">Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt</span><span class="sxs-lookup"><span data-stu-id="75968-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="75968-103">Die grundlegende Verwendung von einer Windows Forms <xref:System.Windows.Forms.Button> Steuerelement ist, Code ausführen, wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="75968-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="75968-104">Klicken auf eine <xref:System.Windows.Forms.Button> Steuerelement generiert auch eine Reihe anderer Ereignisse, z. B. die <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="75968-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="75968-105">Wenn Sie beabsichtigen, fügen Sie Ereignishandler für diese verwandten Ereignisse, achten Sie darauf, dass ihre Aktionen nicht in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="75968-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="75968-106">Z. B. wenn die Informationen, die der Benutzer in einem Textfeld eingegeben hat, auf die Schaltfläche gelöscht werden, sollen durch das Anhalten des Mauszeigers über der Schaltfläche keine QuickInfo mit diesen jetzt nicht werden vorhandene Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75968-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="75968-107">Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.Button> -Steuerelement, jedem Klick wird separat verarbeitet werden; d. h. das Steuerelement nicht das Doppelklickereignis unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75968-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="75968-108">Zum Antworten auf eine Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="75968-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="75968-109">In der Schaltfläche `Click` <xref:System.EventHandler> Ausführung des Codes zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="75968-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="75968-110">`Button1_Click` muss auf das Steuerelement gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="75968-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="75968-111">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="75968-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="75968-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75968-112">See also</span></span>
- [<span data-ttu-id="75968-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="75968-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="75968-114">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75968-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="75968-115">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="75968-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
