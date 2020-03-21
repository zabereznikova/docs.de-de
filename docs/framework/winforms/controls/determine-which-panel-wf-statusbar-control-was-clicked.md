---
title: Bestimmen, auf welches Bedienfeld im Statusleistensteuerelement geklickt wurde
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182365"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="1415d-102">Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="1415d-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1415d-103">Die <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> und Steuerelemente ersetzen <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> fügen Funktionen zu den und Steuerelementen hinzu. Die <xref:System.Windows.Forms.StatusBar> und-Steuerelemente <xref:System.Windows.Forms.StatusBarPanel> werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie dies wünschen.</span><span class="sxs-lookup"><span data-stu-id="1415d-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="1415d-104">Um das [Statusleistensteuerelement](statusbar-control-windows-forms.md) so zu programmieren, dass es <xref:System.Windows.Forms.StatusBar.PanelClick> auf Benutzerklicks reagiert, verwenden Sie eine Fallanweisung innerhalb des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="1415d-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="1415d-105">Das Ereignis enthält ein Argument (das Panelargument), das <xref:System.Windows.Forms.StatusBarPanel>einen Verweis auf die angeklickte enthält.</span><span class="sxs-lookup"><span data-stu-id="1415d-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="1415d-106">Mit dieser Referenz können Sie den Index des angeklickten Bedienfelds bestimmen und entsprechend programmieren.</span><span class="sxs-lookup"><span data-stu-id="1415d-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1415d-107">Stellen Sie <xref:System.Windows.Forms.StatusBar> sicher, <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> dass die `true`Eigenschaft des Steuerelements auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1415d-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="1415d-108">So bestimmen Sie, auf welches Bedienfeld geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="1415d-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="1415d-109">Verwenden <xref:System.Windows.Forms.StatusBar.PanelClick> Sie im Ereignishandler eine `Select Case` (in `switch case` Visual Basic) oder (Visual C- oder Visual C++)-Anweisung, um zu bestimmen, auf welchen Bereich geklickt wurde, indem Sie den Index des angeklickten Bedienfelds in den Ereignisargumenten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1415d-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="1415d-110">Das folgende Codebeispiel erfordert das Vorhandensein eines <xref:System.Windows.Forms.StatusBar> `StatusBar1`Steuerelements, <xref:System.Windows.Forms.StatusBarPanel> von `StatusBarPanel1` , `StatusBarPanel2`und zwei Objekten im Formular.</span><span class="sxs-lookup"><span data-stu-id="1415d-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="1415d-111">(Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="1415d-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1415d-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1415d-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="1415d-113">Gewusst wie: Festlegen der Größe eines Statusleistenbereichs</span><span class="sxs-lookup"><span data-stu-id="1415d-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="1415d-114">Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1415d-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="1415d-115">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1415d-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
