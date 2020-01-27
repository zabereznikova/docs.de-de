---
title: Ermitteln, auf welchen Bereich im StatusBar-Steuerelement geklickt wurde
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746010"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="4f0ad-102">Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="4f0ad-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4f0ad-103">Die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzen und fügen Funktionen zum <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelementen hinzu. die <xref:System.Windows.Forms.StatusBar>-und <xref:System.Windows.Forms.StatusBarPanel>-Steuerelemente werden jedoch sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie sich entscheiden.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="4f0ad-104">Um das [StatusBar-Steuer](statusbar-control-windows-forms.md) Element für die Reaktion auf Benutzer Klicks zu programmieren, verwenden Sie eine Case-Anweisung innerhalb des <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="4f0ad-105">Das Ereignis enthält ein Argument (das Panel-Argument), das einen Verweis auf die <xref:System.Windows.Forms.StatusBarPanel>enthält, auf die geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="4f0ad-106">Mithilfe dieses Verweises können Sie den Index des angeklickten Panels ermitteln und entsprechend programmieren.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f0ad-107">Stellen Sie sicher, dass die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>-Eigenschaft des <xref:System.Windows.Forms.StatusBar> Steuer Elements auf `true`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="4f0ad-108">So bestimmen Sie den Bereich, auf den geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="4f0ad-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="4f0ad-109">Verwenden Sie im Ereignishandler <xref:System.Windows.Forms.StatusBar.PanelClick> eine `Select Case`-Anweisung (in Visual Basic) oder eine `switch case` C# (Visual C++oder Visual)-Anweisung, um zu bestimmen, auf welche Fläche geklickt wurde, indem Sie den Index des angeklickten Panels in den Ereignis Argumenten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="4f0ad-110">Für das folgende Codebeispiel ist es erforderlich, dass ein <xref:System.Windows.Forms.StatusBar> Steuerelement, `StatusBar1`und zwei <xref:System.Windows.Forms.StatusBarPanel>-Objekte, `StatusBarPanel1` und `StatusBarPanel2`, auf dem Formular vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="4f0ad-111">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4f0ad-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f0ad-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f0ad-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="4f0ad-113">Gewusst wie: Festlegen der Größe eines Statusleistenbereichs</span><span class="sxs-lookup"><span data-stu-id="4f0ad-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="4f0ad-114">Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4f0ad-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="4f0ad-115">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4f0ad-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
