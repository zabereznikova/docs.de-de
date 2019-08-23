---
title: 'Vorgehensweise: Hinzufügen von Bereichen zu einem StatusBar-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: 27d65c07f0a6ec4a25d057e2c16a8b59933bb8fd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925109"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a>Vorgehensweise: Hinzufügen von Bereichen zu einem StatusBar-Steuerelement
> [!IMPORTANT]
> Das <xref:System.Windows.Forms.StatusStrip> - <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelement und das-Steuerelement <xref:System.Windows.Forms.StatusBar> ersetzen und fügen Funktionen zu den <xref:System.Windows.Forms.StatusBar> Steuer <xref:System.Windows.Forms.StatusBarPanel> Elementen und <xref:System.Windows.Forms.StatusBarPanel> hinzu. die Steuerelemente und werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, St.  
  
 Der programmierbare Bereich in einem [StatusBar-Steuer](statusbar-control-windows-forms.md) Element besteht aus Instanzen <xref:System.Windows.Forms.StatusBarPanel> der-Klasse. Diese werden durch Ergänzungen zur <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> -Klasse hinzugefügt.  
  
### <a name="to-add-panels-to-a-status-bar"></a>So fügen Sie einer Statusleiste Panels hinzu  
  
1. Erstellen Sie in einer-Prozedur Status leisten Panels, indem Sie Sie der <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>hinzufügen. Geben Sie die Eigenschafts Einstellungen für einzelne Panels mithilfe des Indexes an <xref:System.Windows.Forms.StatusBar.Panels%2A> , der durch die-Eigenschaft geleitet wird.  
  
     Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Symbols festgelegt wurde, der Ordner " **eigene** Dateien". Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer unter dem Windows-Betriebssystem diesen Ordner enthalten. Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen System Zugriffsebenen die Anwendung sicher ausführen. Das folgende Beispiel erfordert ein Formular mit einem <xref:System.Windows.Forms.StatusBar> bereits hinzugefügten-Steuerelement.  
  
    > [!NOTE]
    > Bei <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> handelt es sich um eine Null basierte Auflistung, daher sollte der Code entsprechend fortgesetzt werden.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Dialog Feld "Sammlungs-Editor"](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))
- [Vorgehensweise: Festlegen der Größe von Status leisten Panels](how-to-set-the-size-of-status-bar-panels.md)
- [Exemplarische Vorgehensweise: Aktualisieren von Status leisten Informationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Vorgehensweise: Legen Sie fest, auf welchem Bereich im Windows Forms StatusBar-Steuerelement geklickt wurde.](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
