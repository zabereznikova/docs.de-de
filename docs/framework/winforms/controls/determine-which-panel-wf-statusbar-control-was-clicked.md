---
title: 'Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde'
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
ms.openlocfilehash: 6229d8965949641105cd0e9708474c3249d52d1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965721"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="68055-102">Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="68055-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="68055-103">Das <xref:System.Windows.Forms.StatusStrip> - <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement und das-Steuerelement <xref:System.Windows.Forms.StatusBar> ersetzen und fügen Funktionen zu den <xref:System.Windows.Forms.StatusBar> Steuer <xref:System.Windows.Forms.StatusBarPanel> Elementen und <xref:System.Windows.Forms.StatusBarPanel> hinzu. die Steuerelemente und werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, St.</span><span class="sxs-lookup"><span data-stu-id="68055-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="68055-104">Um das [StatusBar-Steuer](statusbar-control-windows-forms.md) Element für die Reaktion auf Benutzer Klicks zu programmieren, verwenden Sie <xref:System.Windows.Forms.StatusBar.PanelClick> eine Case-Anweisung innerhalb des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="68055-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="68055-105">Das Ereignis enthält ein Argument (das Panel-Argument), das einen Verweis auf die angeklickte <xref:System.Windows.Forms.StatusBarPanel>enthält.</span><span class="sxs-lookup"><span data-stu-id="68055-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="68055-106">Mithilfe dieses Verweises können Sie den Index des angeklickten Panels ermitteln und entsprechend programmieren.</span><span class="sxs-lookup"><span data-stu-id="68055-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68055-107">Stellen Sie sicher <xref:System.Windows.Forms.StatusBar> , dass <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> die-Eigenschaft des `true`Steuer Elements auf gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="68055-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="68055-108">So bestimmen Sie den Bereich, auf den geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="68055-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="68055-109">`switch case` `Select Case`VerwendenSie im-Ereignishandler eine-Anweisung (in Visual Basic) oder C# eine- C++Anweisung (Visual oder Visual), um zu bestimmen, auf welche Fläche geklickt wurde, indem Sie den Index des angeklickten Panels in den Ereignis Argumenten untersuchen. <xref:System.Windows.Forms.StatusBar.PanelClick></span><span class="sxs-lookup"><span data-stu-id="68055-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="68055-110">Für das folgende Codebeispiel ist das vorhanden sein <xref:System.Windows.Forms.StatusBar> eines `StatusBarPanel2`- `StatusBar1`Steuer Elements, des-Steuer Elements, <xref:System.Windows.Forms.StatusBarPanel> des- `StatusBarPanel1` Objekts und des-Objekts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="68055-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="68055-111">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="68055-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68055-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68055-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="68055-113">Vorgehensweise: Festlegen der Größe von Status leisten Panels</span><span class="sxs-lookup"><span data-stu-id="68055-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="68055-114">Exemplarische Vorgehensweise: Aktualisieren von Status leisten Informationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="68055-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="68055-115">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68055-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
