---
title: 'Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde'
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
ms.openlocfilehash: b83dc7273c612e914840307bc749abef780284ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527973"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="fc5b0-102">Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="fc5b0-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="fc5b0-103">Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fc5b0-104">Programm den [StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) Steuerelement reagieren auf das Benutzer klicken, verwenden Sie eine Case-Anweisung innerhalb der <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-104">To program the [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="fc5b0-105">Das Ereignis enthält ein Argument (das Panel-Argument) enthält einen Verweis auf die geklickt wurde <xref:System.Windows.Forms.StatusBarPanel>.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="fc5b0-106">Mit diesem Verweis können Sie bestimmen den Index des Bereichs geklickt wurde, und Programmieren.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc5b0-107">Sicherstellen, dass die <xref:System.Windows.Forms.StatusBar> des Steuerelements <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> -Eigenschaftensatz auf `true`.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="fc5b0-108">Um zu bestimmen, welcher Bereich geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="fc5b0-108">To determine which panel was clicked</span></span>  
  
1.  <span data-ttu-id="fc5b0-109">In der <xref:System.Windows.Forms.StatusBar.PanelClick> -Ereignishandler ein `Select Case` (in Visual Basic) oder `switch case` (Visual C#- oder [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Anweisung, um festzustellen, welchen Bereich geklickt wurde, indem Sie den Index des betreffenden Bereichs in der Ereignisargumente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="fc5b0-110">Das folgende Codebeispiel erfordert das Vorhandensein, auf dem Formular eine <xref:System.Windows.Forms.StatusBar> -Steuerelement, `StatusBar1`, und zwei <xref:System.Windows.Forms.StatusBarPanel> Objekte `StatusBarPanel1` und `StatusBarPanel2`.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="fc5b0-111">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc5b0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc5b0-112">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="fc5b0-113">Gewusst wie: Festlegen der Größe eines Statusleistenbereichs</span><span class="sxs-lookup"><span data-stu-id="fc5b0-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [<span data-ttu-id="fc5b0-114">Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fc5b0-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [<span data-ttu-id="fc5b0-115">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fc5b0-115">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
