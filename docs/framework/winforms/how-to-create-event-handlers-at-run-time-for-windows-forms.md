---
title: 'Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 09f090c6267093e3ad59266d8c77ea13b13b63d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801576"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit
Zusätzlich zum Erstellen von Ereignissen mit dem Windows Forms-Designer können Sie auch einen Ereignishandler zur Laufzeit erstellen. Durch diese Aktion können Sie Ereignishandler basierend auf Bedingungen in Code zur Laufzeit miteinander verknüpfen, statt sie beim ersten Start des Programms miteinander zu verknüpfen.  
  
### <a name="to-create-an-event-handler-at-run-time"></a>So erstellen Sie einen Ereignishandler zur Laufzeit  
  
1. Öffnen Sie das Formular im Code-Editor, das Sie zu einem Ereignishandler hinzufügen möchten.  
  
2. Fügen Sie eine Methode zu Ihrem Formular hinzu. Verwenden Sie hierfür die Methodensignatur für das Ereignis, das Sie bearbeiten möchten.  
  
     Angenommen, Sie bearbeiten die <xref:System.Windows.Forms.Control.Click> Ereignis eine <xref:System.Windows.Forms.Button> -Steuerelement, erstellen Sie eine Methode z. B. Folgendes:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3. Fügen Sie für Ihre Anwendung geeigneten Code zum Ereignishandler hinzu.  
  
4. Bestimmen Sie, für welches Formular oder Steuerelement Sie einen Ereignishandler erstellen möchten.  
  
5. Fügen Sie in einer Methode innerhalb der Formularklasse einen Code hinzu, der den zu bearbeitenden Ereignishandler angibt. Der folgende Code gibt beispielsweise den Ereignishandler `button1_Click` Handles der <xref:System.Windows.Forms.Control.Click> Ereignis eine <xref:System.Windows.Forms.Button> Steuerelement:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Die <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> -Methode in der oben genannten Visual Basic-Code wird einen Click-Ereignishandler für die Schaltfläche.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
