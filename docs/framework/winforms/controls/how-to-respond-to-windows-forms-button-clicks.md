---
title: "Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms"
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
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 923eb7d1b1b5b442ce897619253a958019b239a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="4cf74-102">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf74-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="4cf74-103">Die grundlegendste Verwendung von Windows Forms <xref:System.Windows.Forms.Button> Steuerelement ist, um Code auszuführen, auf die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="4cf74-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="4cf74-104">Klicken auf eine <xref:System.Windows.Forms.Button> Steuerelement generiert auch eine Anzahl von anderen Ereignissen, z. B. die <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="4cf74-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="4cf74-105">Wenn Sie beabsichtigen, fügen Sie Ereignishandler für diese verwandten Ereignisse, achten Sie darauf, dass ihre Aktionen nicht in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="4cf74-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="4cf74-106">Z. B. Wenn Sie auf die Schaltfläche Informationen gelöscht werden, die der Benutzer in einem Textfeld eingegeben hat, durch das Anhalten des Mauszeigers über der Schaltfläche keine QuickInfo mit dieser Information jetzt nicht vorhandene angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4cf74-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="4cf74-107">Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.Button> -Steuerelement, jedem Mausklick wird separat verarbeitet werden; d. h. das Steuerelement nicht das Doppelklickereignis unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4cf74-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="4cf74-108">So reagieren Sie auf einem Schaltflächen-Klickereignis</span><span class="sxs-lookup"><span data-stu-id="4cf74-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="4cf74-109">In der Schaltfläche `Click` <xref:System.EventHandler> schreiben Sie den Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="4cf74-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="4cf74-110">`Button1_Click`muss an das Steuerelement gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="4cf74-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="4cf74-111">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern an Zeit für Windows Forms führen](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4cf74-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4cf74-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cf74-112">See Also</span></span>  
 [<span data-ttu-id="4cf74-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4cf74-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="4cf74-114">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cf74-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="4cf74-115">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4cf74-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
