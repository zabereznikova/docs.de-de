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
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde
> [!IMPORTANT]
> Die <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> und Steuerelemente ersetzen <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> fügen Funktionen zu den und Steuerelementen hinzu. Die <xref:System.Windows.Forms.StatusBar> und-Steuerelemente <xref:System.Windows.Forms.StatusBarPanel> werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie dies wünschen.  
  
 Um das [Statusleistensteuerelement](statusbar-control-windows-forms.md) so zu programmieren, dass es <xref:System.Windows.Forms.StatusBar.PanelClick> auf Benutzerklicks reagiert, verwenden Sie eine Fallanweisung innerhalb des Ereignisses. Das Ereignis enthält ein Argument (das Panelargument), das <xref:System.Windows.Forms.StatusBarPanel>einen Verweis auf die angeklickte enthält. Mit dieser Referenz können Sie den Index des angeklickten Bedienfelds bestimmen und entsprechend programmieren.  
  
> [!NOTE]
> Stellen Sie <xref:System.Windows.Forms.StatusBar> sicher, <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> dass die `true`Eigenschaft des Steuerelements auf festgelegt ist.  
  
### <a name="to-determine-which-panel-was-clicked"></a>So bestimmen Sie, auf welches Bedienfeld geklickt wurde  
  
1. Verwenden <xref:System.Windows.Forms.StatusBar.PanelClick> Sie im Ereignishandler eine `Select Case` (in `switch case` Visual Basic) oder (Visual C- oder Visual C++)-Anweisung, um zu bestimmen, auf welchen Bereich geklickt wurde, indem Sie den Index des angeklickten Bedienfelds in den Ereignisargumenten untersuchen.  
  
     Das folgende Codebeispiel erfordert das Vorhandensein eines <xref:System.Windows.Forms.StatusBar> `StatusBar1`Steuerelements, <xref:System.Windows.Forms.StatusBarPanel> von `StatusBarPanel1` , `StatusBarPanel2`und zwei Objekten im Formular.  
  
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
  
     (Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Gewusst wie: Festlegen der Größe eines Statusleistenbereichs](how-to-set-the-size-of-status-bar-panels.md)
- [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
