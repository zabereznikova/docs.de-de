---
title: 'Vorgehensweise: Festlegen der Größe eines Statusleistenbereichs'
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
ms.openlocfilehash: 4ba0f7f02b548a5d9ea1a99605a668f449b3e4a9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923627"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Vorgehensweise: Festlegen der Größe eines Statusleistenbereichs
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement das <xref:System.Windows.Forms.StatusBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Jede Instanz der <xref:System.Windows.Forms.StatusBarPanel> -Klasse in einem [StatusBar-Steuer](statusbar-control-windows-forms.md) Element verfügt über eine Reihe dynamischer Eigenschaften, die das Verhalten der Breite und Größenänderung zur Laufzeit bestimmen.  
  
### <a name="to-set-the-size-of-a-panel"></a>So legen Sie die Größe eines Panels fest  
  
1. Legen Sie in einer Prozedur die <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>Eigenschaften <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, und <xref:System.Windows.Forms.StatusBarPanel.Width%2A> (oder eine beliebige Teilmenge darin) für die Status leisten Bereiche fest, indem Sie <xref:System.Windows.Forms.StatusBarPanel> ihren Index verwenden <xref:System.Windows.Forms.StatusBar.Panels%2A> , der durch die-Eigenschaft der-Auflistung geleitet wird.  
  
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

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Exemplarische Vorgehensweise: Aktualisieren von Status leisten Informationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Vorgehensweise: Legen Sie fest, auf welchem Bereich im Windows Forms StatusBar-Steuerelement geklickt wurde.](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
