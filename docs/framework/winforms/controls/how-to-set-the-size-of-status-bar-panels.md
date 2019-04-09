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
ms.openlocfilehash: c6c9d6570e9b5c2f6d4eee0262c3d90e29e4b493
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131053"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>Vorgehensweise: Festlegen der Größe eines Statusleistenbereichs
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStripStatusLabel>-Steuerelement das <xref:System.Windows.Forms.StatusBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Jede Instanz der <xref:System.Windows.Forms.StatusBarPanel> -Klasse innerhalb einer [StatusBar-Steuerelement](statusbar-control-windows-forms.md) Steuerelement hat eine Reihe von dynamischen Eigenschaften, die bestimmen die Breite und Größe von Verhalten zur Laufzeit.  
  
### <a name="to-set-the-size-of-a-panel"></a>Die Größe eines Bereichs festgelegt  
  
1.  Legen Sie in einer Prozedur die <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, und <xref:System.Windows.Forms.StatusBarPanel.Width%2A> Eigenschaften (oder eine beliebige Teilmenge darin) für die Statusleiste Bereiche, deren Index verwendet wird, die über übergeben die <xref:System.Windows.Forms.StatusBar.Panels%2A> Eigenschaft der <xref:System.Windows.Forms.StatusBarPanel> Auflistung.  
  
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
- [Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit](walkthrough-updating-status-bar-information-at-run-time.md)
- [Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Übersicht über das StatusBar-Steuerelement](statusbar-control-overview-windows-forms.md)
