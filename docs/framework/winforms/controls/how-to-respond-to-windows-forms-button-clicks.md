---
title: 'Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: a10eaa3ea62df9301a53f5609b503bfabcb50a46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110070"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms
Die grundlegende Verwendung von einer Windows Forms <xref:System.Windows.Forms.Button> Steuerelement ist, Code ausführen, wenn die Schaltfläche geklickt wird.  
  
 Klicken auf eine <xref:System.Windows.Forms.Button> Steuerelement generiert auch eine Reihe anderer Ereignisse, z. B. die <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse. Wenn Sie beabsichtigen, fügen Sie Ereignishandler für diese verwandten Ereignisse, achten Sie darauf, dass ihre Aktionen nicht in Konflikt stehen. Z. B. wenn die Informationen, die der Benutzer in einem Textfeld eingegeben hat, auf die Schaltfläche gelöscht werden, sollen durch das Anhalten des Mauszeigers über der Schaltfläche keine QuickInfo mit diesen jetzt nicht werden vorhandene Informationen angezeigt werden.  
  
 Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.Button> -Steuerelement, jedem Klick wird separat verarbeitet werden; d. h. das Steuerelement nicht das Doppelklickereignis unterstützt.  
  
### <a name="to-respond-to-a-button-click"></a>Zum Antworten auf eine Schaltfläche klicken.  
  
-   In der Schaltfläche `Click` <xref:System.EventHandler> Ausführung des Codes zu schreiben. `Button1_Click` muss auf das Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Button-Steuerelement](button-control-windows-forms.md)
