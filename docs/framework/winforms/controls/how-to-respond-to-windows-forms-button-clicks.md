---
title: 'Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms'
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
ms.openlocfilehash: 14a880c34f163dc6fece44c24d377822a741b0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms
Die grundlegendste Verwendung von Windows Forms <xref:System.Windows.Forms.Button> Steuerelement ist, um Code auszuführen, auf die Schaltfläche geklickt wird.  
  
 Klicken auf eine <xref:System.Windows.Forms.Button> Steuerelement generiert auch eine Anzahl von anderen Ereignissen, z. B. die <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse. Wenn Sie beabsichtigen, fügen Sie Ereignishandler für diese verwandten Ereignisse, achten Sie darauf, dass ihre Aktionen nicht in Konflikt stehen. Z. B. Wenn Sie auf die Schaltfläche Informationen gelöscht werden, die der Benutzer in einem Textfeld eingegeben hat, durch das Anhalten des Mauszeigers über der Schaltfläche keine QuickInfo mit dieser Information jetzt nicht vorhandene angezeigt werden sollen.  
  
 Wenn der Benutzer versucht, doppelklicken Sie auf die <xref:System.Windows.Forms.Button> -Steuerelement, jedem Mausklick wird separat verarbeitet werden; d. h. das Steuerelement nicht das Doppelklickereignis unterstützt.  
  
### <a name="to-respond-to-a-button-click"></a>So reagieren Sie auf einem Schaltflächen-Klickereignis  
  
-   In der Schaltfläche `Click` <xref:System.EventHandler> schreiben Sie den Code ausführen. `Button1_Click` muss an das Steuerelement gebunden werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern an Zeit für Windows Forms führen](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
 [Übersicht über das Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Button-Steuerelement](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
