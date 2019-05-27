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
ms.openlocfilehash: a659de62965d17e965eee2f750337a08ae1801e0
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053722"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="dd366-102">Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="dd366-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="dd366-103">Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="dd366-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="dd366-104">Programm die [StatusBar-Steuerelement](statusbar-control-windows-forms.md) Steuerelement auf Mausklicks reagiert, verwenden Sie eine Case-Anweisung innerhalb der <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dd366-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="dd366-105">Das Ereignis enthält ein Argument (das Panel-Argument) enthält einen Verweis auf das geklickt wurde <xref:System.Windows.Forms.StatusBarPanel>.</span><span class="sxs-lookup"><span data-stu-id="dd366-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="dd366-106">Verwenden diesen Verweis, können Sie den Index des betreffenden Bereichs bestimmen, und Programmieren.</span><span class="sxs-lookup"><span data-stu-id="dd366-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd366-107">Sicherstellen, dass die <xref:System.Windows.Forms.StatusBar> des Steuerelements <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> -Eigenschaftensatz auf `true`.</span><span class="sxs-lookup"><span data-stu-id="dd366-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="dd366-108">Um zu bestimmen, welchen Bereich geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="dd366-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="dd366-109">In der <xref:System.Windows.Forms.StatusBar.PanelClick> -Ereignishandler ein `Select Case` (in Visual Basic) oder `switch case` (Visual C# oder visuellen C++) Anweisung, um zu bestimmen, welchen Bereich geklickt wurde, indem Sie den Index des betreffenden Bereichs in der Ereignisargumente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dd366-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="dd366-110">Im folgenden Codebeispiel wird benötigt, auf dem Formular von einem <xref:System.Windows.Forms.StatusBar> -Steuerelement, `StatusBar1`, und zwei <xref:System.Windows.Forms.StatusBarPanel> Objekte `StatusBarPanel1` und `StatusBarPanel2`.</span><span class="sxs-lookup"><span data-stu-id="dd366-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
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
  
     <span data-ttu-id="dd366-111">(Visual C#, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="dd366-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd366-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd366-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="dd366-113">Vorgehensweise: Festlegen der Größe eines Statusleistenbereichs</span><span class="sxs-lookup"><span data-stu-id="dd366-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="dd366-114">Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="dd366-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="dd366-115">Übersicht über das StatusBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dd366-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
