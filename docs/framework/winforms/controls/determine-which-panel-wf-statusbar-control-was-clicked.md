---
title: "Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows&#160;Forms geklickt wurde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Panel-Steuerelement [Windows Forms], Feststellen von Klicks"
  - "PanelClick-Ereignis, Feststellen von Klicks auf einen Bereich"
  - "Bereiche, Feststellen von angeklickten"
  - "Statusleisten, Feststellen von Klicks auf einen Bereich"
  - "StatusBar-Steuerelement [Windows Forms], Codieren von Klickereignissen für einen Bereich"
  - "StatusBar-Steuerelement [Windows Forms], Feststellen von Klicks auf einen Bereich"
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows&#160;Forms geklickt wurde
> [!IMPORTANT]
>  Obwohl die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> durch die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzt und funktionell erweitert werden, werden die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Um das [StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)\-Steuerelement so zu programmieren, dass es auf Benutzerklicks reagiert, verwenden Sie die case\-Anweisung im <xref:System.Windows.Forms.StatusBar.PanelClick>\-Ereignis.  Das Ereignis enthält ein Argument \(das panel\-Argument\), das einen Verweis auf das <xref:System.Windows.Forms.StatusBarPanel>\-Objekt enthält, auf das geklickt wurde.  Mit diesem Verweis können Sie den Index der Fläche bestimmen, auf die geklickt wurde, und die Programmierung entsprechend anpassen.  
  
> [!NOTE]
>  Stellen Sie sicher, dass die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>\-Eigenschaft des <xref:System.Windows.Forms.StatusBar>\-Steuerelements auf `true` festgelegt ist.  
  
### So bestimmen Sie, auf welche Fläche geklickt wurde  
  
1.  Sie können im <xref:System.Windows.Forms.StatusBar.PanelClick>\-Ereignishandler mithilfe einer `Select Case`\-Anweisung \(in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) oder einer `switch case`\-Anweisung \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] oder [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) bestimmen, auf welchen Bereich geklickt wurde, indem Sie den Index des betreffenden Bereichs in den Ereignisargumenten überprüfen.  
  
     Im folgenden Codebeispiel wird davon ausgegangen, dass im Formular ein <xref:System.Windows.Forms.StatusBar>\-Steuerelement, `StatusBar1`, und zwei <xref:System.Windows.Forms.StatusBarPanel>\-Objekte, `StatusBarPanel1`  und `StatusBarPanel2`, vorhanden sind.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Gewusst wie: Festlegen der Größe eines Statusleistenbereichs](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Übersicht über das StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)