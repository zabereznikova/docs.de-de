---
title: Reagieren auf Button-Klicks
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
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735716"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms
Die grundlegende Verwendung eines Windows Forms <xref:System.Windows.Forms.Button> Steuer Elements ist das Ausführen von Code, wenn auf die Schaltfläche geklickt wird.  
  
 Wenn Sie auf ein <xref:System.Windows.Forms.Button> Steuerelement klicken, werden auch eine Reihe weiterer Ereignisse generiert, z. b. die Ereignisse <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>und <xref:System.Windows.Forms.Control.MouseUp>. Wenn Sie beabsichtigen, Ereignishandler für diese verknüpften Ereignisse anzufügen, stellen Sie sicher, dass Ihre Aktionen nicht in Konflikt stehen. Wenn Sie beispielsweise auf die Schaltfläche klicken, um die Informationen zu löschen, die der Benutzer in ein Textfeld eingegeben hat, sollte mit dem Mauszeiger auf die Schaltfläche keine QuickInfo mit den jetzt nicht vorhandenen Informationen angezeigt werden.  
  
 Wenn der Benutzer versucht, auf das <xref:System.Windows.Forms.Button>-Steuerelement zu doppelklicken, wird jeder Klick separat verarbeitet. Das heißt, das-Steuerelement unterstützt das Double-Click-Ereignis nicht.  
  
### <a name="to-respond-to-a-button-click"></a>So reagieren Sie auf einen Klick auf eine Schaltfläche  
  
- Schreiben Sie im `Click` der Schaltfläche <xref:System.EventHandler> den Code, der ausgeführt werden soll. `Button1_Click` müssen an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
