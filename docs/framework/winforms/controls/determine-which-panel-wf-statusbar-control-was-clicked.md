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
ms.openlocfilehash: 1c28f8eaba5c35f762d6fc57ebbddbbb71769c81
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304284"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Hinzufügen von Funktionen, die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> -Steuerelemente jedoch die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Programm die [StatusBar-Steuerelement](statusbar-control-windows-forms.md) Steuerelement auf Mausklicks reagiert, verwenden Sie eine Case-Anweisung innerhalb der <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignis. Das Ereignis enthält ein Argument (das Panel-Argument) enthält einen Verweis auf das geklickt wurde <xref:System.Windows.Forms.StatusBarPanel>. Verwenden diesen Verweis, können Sie den Index des betreffenden Bereichs bestimmen, und Programmieren.  
  
> [!NOTE]
>  Sicherstellen, dass die <xref:System.Windows.Forms.StatusBar> des Steuerelements <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> -Eigenschaftensatz auf `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Um zu bestimmen, welchen Bereich geklickt wurde  
  
1. In der <xref:System.Windows.Forms.StatusBar.PanelClick> -Ereignishandler ein `Select Case` (in Visual Basic) oder `switch case` (Visual C# oder [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Anweisung, um zu bestimmen, welchen Bereich geklickt wurde, indem Sie den Index des betreffenden Bereichs in der Ereignisargumente überprüfen.  
  
     Im folgenden Codebeispiel wird benötigt, auf dem Formular von einem <xref:System.Windows.Forms.StatusBar> -Steuerelement, `StatusBar1`, und zwei <xref:System.Windows.Forms.StatusBarPanel> Objekte `StatusBarPanel1` und `StatusBarPanel2`.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
- [Vorgehensweise: Festlegen der Größe eines Statusleistenbereichs](how-to-set-the-size-of-status-bar-panels.md)
- [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
