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
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde
> [!IMPORTANT]
> Das <xref:System.Windows.Forms.StatusStrip> - <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement und das-Steuerelement <xref:System.Windows.Forms.StatusBar> ersetzen und fügen Funktionen zu den <xref:System.Windows.Forms.StatusBar> Steuer <xref:System.Windows.Forms.StatusBarPanel> Elementen und <xref:System.Windows.Forms.StatusBarPanel> hinzu. die Steuerelemente und werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, St.  
  
 Um das [StatusBar-Steuer](statusbar-control-windows-forms.md) Element für die Reaktion auf Benutzer Klicks zu programmieren, verwenden Sie <xref:System.Windows.Forms.StatusBar.PanelClick> eine Case-Anweisung innerhalb des Ereignisses. Das Ereignis enthält ein Argument (das Panel-Argument), das einen Verweis auf die angeklickte <xref:System.Windows.Forms.StatusBarPanel>enthält. Mithilfe dieses Verweises können Sie den Index des angeklickten Panels ermitteln und entsprechend programmieren.  
  
> [!NOTE]
> Stellen Sie sicher <xref:System.Windows.Forms.StatusBar> , dass <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> die-Eigenschaft des `true`Steuer Elements auf gesetzt ist.  
  
### <a name="to-determine-which-panel-was-clicked"></a>So bestimmen Sie den Bereich, auf den geklickt wurde  
  
1. `switch case` `Select Case`VerwendenSie im-Ereignishandler eine-Anweisung (in Visual Basic) oder C# eine- C++Anweisung (Visual oder Visual), um zu bestimmen, auf welche Fläche geklickt wurde, indem Sie den Index des angeklickten Panels in den Ereignis Argumenten untersuchen. <xref:System.Windows.Forms.StatusBar.PanelClick>  
  
     Für das folgende Codebeispiel ist das vorhanden sein <xref:System.Windows.Forms.StatusBar> eines `StatusBarPanel2`- `StatusBar1`Steuer Elements, des-Steuer Elements, <xref:System.Windows.Forms.StatusBarPanel> des- `StatusBarPanel1` Objekts und des-Objekts erforderlich.  
  
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
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Vorgehensweise: Festlegen der Größe von Status leisten Panels](how-to-set-the-size-of-status-bar-panels.md)
- [Exemplarische Vorgehensweise: Aktualisieren von Status leisten Informationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
