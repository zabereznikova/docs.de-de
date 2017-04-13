---
title: "Gewusst wie: Festlegen der Gr&#246;&#223;e eines Statusleistenbereichs | Microsoft Docs"
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
  - "Bereiche, Festlegen der Größe in Statusleisten"
  - "Statusleisten, Einstellen der Bereichsgröße"
  - "StatusBar-Steuerelement [Windows Forms], Bereichsgröße"
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen der Gr&#246;&#223;e eines Statusleistenbereichs
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>\-Steuerelement das <xref:System.Windows.Forms.StatusBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Jede Instanz der <xref:System.Windows.Forms.StatusBarPanel>\-Klasse in einem [StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)\-Steuerelement verfügt über eine Reihe von dynamischen Eigenschaften, die die Breite und das Verhalten bei Größenänderungen zur Laufzeit bestimmen.  
  
### So legen Sie die Größe eines Bereichs fest  
  
1.  Legen Sie in einer Prozedur die Eigenschaften <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A> und <xref:System.Windows.Forms.StatusBarPanel.Width%2A> \(oder eine darin enthaltene Teilmenge\) für die Statusleistenbereiche fest, indem Sie deren von der <xref:System.Windows.Forms.StatusBar.Panels%2A>\-Eigenschaft der <xref:System.Windows.Forms.StatusBarPanel>\-Auflistung übergebenen Index verwenden.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar\-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Übersicht über das StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)