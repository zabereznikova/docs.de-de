---
title: "Gewusst wie: Hinzuf&#252;gen von Bereichen zu einem StatusBar-Steuerelement | Microsoft Docs"
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
  - "Bereiche, Statusleisten"
  - "Statusleisten, Hinzufügen von Bereichen"
  - "StatusBar-Steuerelement [Windows Forms], Hinzufügen von Bereichen"
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Hinzuf&#252;gen von Bereichen zu einem StatusBar-Steuerelement
> [!IMPORTANT]
>  Obwohl die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> durch die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzt und funktionell erweitert werden, werden die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Der programmierbare Bereich innerhalb eines [StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)\-Steuerelements besteht aus Instanzen der <xref:System.Windows.Forms.StatusBarPanel>\-Klasse.  Diese werden der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>\-Klasse durch Zusätze hinzugefügt.  
  
### So fügen Sie einer Statusleiste Bereiche hinzu  
  
1.  Erstellen Sie in einer Prozedur Bereiche einer Statusleiste, indem Sie diese der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> hinzufügen.  Geben Sie die Einstellungen für die Eigenschaften der einzelnen Bereiche an, indem Sie den entsprechenden, durch die <xref:System.Windows.Forms.StatusBar.Panels%2A>\-Eigenschaft übergebenen Index verwenden.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Symbol der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit Windows als Betriebssystem über einen Ordner mit diesem Namen verfügen.  Dieser Speicherort ermöglicht auch Benutzern mit minimalen Systemzugriffsberechtigungen, die Anwendung sicher auszuführen.  Im folgenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.StatusBar>\-Steuerelement hinzugefügt wurde.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> ist eine nullbasierte Auflistung, sodass der Code entsprechend fortgesetzt werden sollte.  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Collection Editor Dialog Box](http://msdn.microsoft.com/de-de/53fb3aad-bffa-4da5-ac89-8438e6fc803c)   
 [Gewusst wie: Festlegen der Größe eines Statusleistenbereichs](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar\-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Übersicht über das StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)