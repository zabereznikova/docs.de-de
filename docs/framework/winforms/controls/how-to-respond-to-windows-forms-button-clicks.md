---
title: Reagieren auf Button-Klicks
description: Erfahren Sie, wie Sie auf Windows Forms Schaltflächen Klicks reagieren. Die grundlegendste Verwendung eines Windows Forms Button-Steuer Elements ist das Ausführen von Code, wenn auf die Schaltfläche geklickt wird.
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
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619727"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms
Die grundlegende Verwendung eines Windows Forms <xref:System.Windows.Forms.Button> Steuer Elements ist das Ausführen von Code, wenn auf die Schaltfläche geklickt wird.  
  
 Wenn Sie <xref:System.Windows.Forms.Button> auf ein Steuerelement klicken, werden auch einige andere Ereignisse generiert, z <xref:System.Windows.Forms.Control.MouseEnter> . b. die <xref:System.Windows.Forms.Control.MouseDown> Ereignisse, und <xref:System.Windows.Forms.Control.MouseUp> . Wenn Sie beabsichtigen, Ereignishandler für diese verknüpften Ereignisse anzufügen, stellen Sie sicher, dass Ihre Aktionen nicht in Konflikt stehen. Wenn Sie beispielsweise auf die Schaltfläche klicken, um die Informationen zu löschen, die der Benutzer in ein Textfeld eingegeben hat, sollte mit dem Mauszeiger auf die Schaltfläche keine QuickInfo mit den jetzt nicht vorhandenen Informationen angezeigt werden.  
  
 Wenn der Benutzer versucht, auf das Steuerelement zu doppelklicken <xref:System.Windows.Forms.Button> , wird jeder Klick separat verarbeitet, d. h., das Steuerelement unterstützt das Doppelklick Ereignis nicht.  
  
### <a name="to-respond-to-a-button-click"></a>So reagieren Sie auf einen Klick auf eine Schaltfläche  
  
- Schreiben Sie in der Schaltfläche `Click` <xref:System.EventHandler> den Code, der ausgeführt werden soll. `Button1_Click`muss an das-Steuerelement gebunden werden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das Button-Steuerelement](button-control-overview-windows-forms.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Button-Steuerelement](button-control-windows-forms.md)
