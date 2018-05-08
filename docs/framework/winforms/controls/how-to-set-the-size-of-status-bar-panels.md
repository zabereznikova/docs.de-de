---
title: 'Gewusst wie: Festlegen der Größe eines Statusleistenbereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: d708b94d02b4f1c1e2f00101e6e394043a6057ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Gewusst wie: Festlegen der Größe eines Statusleistenbereichs
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement das <xref:System.Windows.Forms.StatusBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Jede Instanz von der <xref:System.Windows.Forms.StatusBarPanel> -Klasse innerhalb einer [StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) Steuerelement verfügt über eine Reihe von dynamischen Eigenschaften, die bestimmen der Breite und Größe von Verhalten zur Laufzeit.  
  
### <a name="to-set-the-size-of-a-panel"></a>Zum Festlegen der Größe eines Bereichs  
  
1.  In einer Prozedur festgelegt die <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, und <xref:System.Windows.Forms.StatusBarPanel.Width%2A> Eigenschaften (oder eine beliebige Teilmenge Ergebnisauswahlfunktion) für die Statusleiste Bereiche, die Verwendung ihres Indexes übergeben der <xref:System.Windows.Forms.StatusBar.Panels%2A> Eigenschaft von der <xref:System.Windows.Forms.StatusBarPanel> Auflistung.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Übersicht über das StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
