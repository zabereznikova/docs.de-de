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
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde
> [!IMPORTANT]
> Die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzen und fügen Funktionen zum <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelementen hinzu. die <xref:System.Windows.Forms.StatusBar>-und <xref:System.Windows.Forms.StatusBarPanel>-Steuerelemente werden jedoch sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie sich entscheiden.  
  
 Um das [StatusBar-Steuer](statusbar-control-windows-forms.md) Element für die Reaktion auf Benutzer Klicks zu programmieren, verwenden Sie eine Case-Anweisung innerhalb des <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignisses. Das Ereignis enthält ein Argument (das Panel-Argument), das einen Verweis auf die <xref:System.Windows.Forms.StatusBarPanel>enthält, auf die geklickt wurde. Mithilfe dieses Verweises können Sie den Index des angeklickten Panels ermitteln und entsprechend programmieren.  
  
> [!NOTE]
> Stellen Sie sicher, dass die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>-Eigenschaft des <xref:System.Windows.Forms.StatusBar> Steuer Elements auf `true`festgelegt ist.  
  
### <a name="to-determine-which-panel-was-clicked"></a>So bestimmen Sie den Bereich, auf den geklickt wurde  
  
1. Verwenden Sie im Ereignishandler <xref:System.Windows.Forms.StatusBar.PanelClick> eine `Select Case`-Anweisung (in Visual Basic) oder eine `switch case` C# (Visual C++oder Visual)-Anweisung, um zu bestimmen, auf welche Fläche geklickt wurde, indem Sie den Index des angeklickten Panels in den Ereignis Argumenten untersuchen.  
  
     Für das folgende Codebeispiel ist es erforderlich, dass ein <xref:System.Windows.Forms.StatusBar> Steuerelement, `StatusBar1`und zwei <xref:System.Windows.Forms.StatusBarPanel>-Objekte, `StatusBarPanel1` und `StatusBarPanel2`, auf dem Formular vorhanden ist.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Gewusst wie: Festlegen der Größe eines Statusleistenbereichs](how-to-set-the-size-of-status-bar-panels.md)
- [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
