---
title: 'Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35dc392ed95a5dbe8182b1adbd05affea55d0baa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Programm den [StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) Steuerelement reagieren auf das Benutzer klicken, verwenden Sie eine Case-Anweisung innerhalb der <xref:System.Windows.Forms.StatusBar.PanelClick> Ereignis. Das Ereignis enthält ein Argument (das Panel-Argument) enthält einen Verweis auf die geklickt wurde <xref:System.Windows.Forms.StatusBarPanel>. Mit diesem Verweis können Sie bestimmen den Index des Bereichs geklickt wurde, und Programmieren.  
  
> [!NOTE]
>  Sicherstellen, dass die <xref:System.Windows.Forms.StatusBar> des Steuerelements <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> -Eigenschaftensatz auf `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Um zu bestimmen, welcher Bereich geklickt wurde  
  
1.  In der <xref:System.Windows.Forms.StatusBar.PanelClick> -Ereignishandler ein `Select Case` (in Visual Basic) oder `switch case` (Visual C#- oder [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Anweisung, um festzustellen, welchen Bereich geklickt wurde, indem Sie den Index des betreffenden Bereichs in der Ereignisargumente überprüfen.  
  
     Das folgende Codebeispiel erfordert das Vorhandensein, auf dem Formular eine <xref:System.Windows.Forms.StatusBar> -Steuerelement, `StatusBar1`, und zwei <xref:System.Windows.Forms.StatusBarPanel> Objekte `StatusBarPanel1` und `StatusBarPanel2`.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Gewusst wie: Festlegen der Größe eines Statusleistenbereichs](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Übersicht über das StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
