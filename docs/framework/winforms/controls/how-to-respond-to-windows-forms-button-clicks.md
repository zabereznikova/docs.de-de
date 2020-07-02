---
title: Reagieren auf Button-Klicks
description: Erfahren Sie, wie Sie auf Windows Forms Schaltflächen Klicks reagieren. Die grundlegendste Verwendung eines Windows Forms Button-Steuer Elements ist das Ausführen von Code, wenn auf die Schaltfläche geklickt wird.
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
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619727"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="80b9c-104">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80b9c-104">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="80b9c-105">Die grundlegende Verwendung eines Windows Forms <xref:System.Windows.Forms.Button> Steuer Elements ist das Ausführen von Code, wenn auf die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="80b9c-105">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="80b9c-106">Wenn Sie <xref:System.Windows.Forms.Button> auf ein Steuerelement klicken, werden auch einige andere Ereignisse generiert, z <xref:System.Windows.Forms.Control.MouseEnter> . b. die <xref:System.Windows.Forms.Control.MouseDown> Ereignisse, und <xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="80b9c-106">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="80b9c-107">Wenn Sie beabsichtigen, Ereignishandler für diese verknüpften Ereignisse anzufügen, stellen Sie sicher, dass Ihre Aktionen nicht in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="80b9c-107">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="80b9c-108">Wenn Sie beispielsweise auf die Schaltfläche klicken, um die Informationen zu löschen, die der Benutzer in ein Textfeld eingegeben hat, sollte mit dem Mauszeiger auf die Schaltfläche keine QuickInfo mit den jetzt nicht vorhandenen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="80b9c-108">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="80b9c-109">Wenn der Benutzer versucht, auf das Steuerelement zu doppelklicken <xref:System.Windows.Forms.Button> , wird jeder Klick separat verarbeitet, d. h., das Steuerelement unterstützt das Doppelklick Ereignis nicht.</span><span class="sxs-lookup"><span data-stu-id="80b9c-109">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="80b9c-110">So reagieren Sie auf einen Klick auf eine Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="80b9c-110">To respond to a button click</span></span>  
  
- <span data-ttu-id="80b9c-111">Schreiben Sie in der Schaltfläche `Click` <xref:System.EventHandler> den Code, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="80b9c-111">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="80b9c-112">`Button1_Click`muss an das-Steuerelement gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="80b9c-112">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="80b9c-113">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="80b9c-113">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80b9c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80b9c-114">See also</span></span>

- [<span data-ttu-id="80b9c-115">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="80b9c-115">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="80b9c-116">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80b9c-116">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="80b9c-117">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="80b9c-117">Button Control</span></span>](button-control-windows-forms.md)
