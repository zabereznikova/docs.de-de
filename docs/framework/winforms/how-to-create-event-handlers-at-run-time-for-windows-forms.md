---
title: 'Gewusst wie: Erstellen von Ereignis Handlern zur Laufzeit'
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
ms.openlocfilehash: 0b496a3da77c5bcf7a08c435edba468a7c5809cb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739497"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Gewusst wie: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit

Zusätzlich zum Erstellen von Ereignissen mithilfe des Windows Forms-Designer in Visual Studio können Sie auch einen Ereignishandler zur Laufzeit erstellen. Durch diese Aktion können Sie Ereignishandler basierend auf Bedingungen in Code zur Laufzeit miteinander verknüpfen, statt sie beim ersten Start des Programms miteinander zu verknüpfen.

## <a name="create-an-event-handler-at-run-time"></a>Erstellen eines Ereignis Handlers zur Laufzeit

1. Öffnen Sie das Formular, dem Sie einen Ereignishandler hinzufügen möchten.

2. Fügen Sie eine Methode zu Ihrem Formular hinzu. Verwenden Sie hierfür die Methodensignatur für das Ereignis, das Sie bearbeiten möchten.

     Wenn Sie z. b. das <xref:System.Windows.Forms.Control.Click>-Ereignis eines <xref:System.Windows.Forms.Button> Steuer Elements behandelt haben, würden Sie eine Methode wie die folgende erstellen:

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

5. Fügen Sie in einer Methode innerhalb der Formularklasse einen Code hinzu, der den zu bearbeitenden Ereignishandler angibt. Der folgende Code gibt z. b. den Ereignishandler an `button1_Click` der das <xref:System.Windows.Forms.Control.Click>-Ereignis eines <xref:System.Windows.Forms.Button>-Steuer Elements behandelt:

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     Mit der im obigen Visual Basic Code dargestellten <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>-Methode wird ein Click-Ereignishandler für die Schaltfläche festgelegt.

## <a name="see-also"></a>Weitere Informationen

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)
- [Problembehandlung für geerbte Ereignishandler in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
