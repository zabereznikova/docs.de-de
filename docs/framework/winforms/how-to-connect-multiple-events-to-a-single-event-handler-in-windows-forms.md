---
title: 'Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignis Handler'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739607"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms
Beim Anwendungs Entwurf ist es möglicherweise erforderlich, dass ein einzelner Ereignishandler für mehrere Ereignisse verwendet wird, oder dass mehrere Ereignisse dieselbe Prozedur ausführen. Beispielsweise ist es häufig ein leistungsfähiger Zeitersparnis, wenn ein Menübefehl dasselbe Ereignis wie eine Schaltfläche auf dem Formular aufhebt, wenn Sie die gleiche Funktionalität verfügbar machen. Hierzu können Sie die Ereignisansicht der Eigenschaftenfenster in C# oder das `Handles`-Schlüsselwort und die Dropdown Felder **Klassenname** und **Methodenname** im Visual Basic Code-Editor verwenden.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in Visual Basic  
  
1. Klicken Sie mit der rechten Maustaste, und wählen Sie **Code anzeigen**aus.  
  
2. Wählen Sie im Dropdown Feld **Klassen Name** eines der Steuerelemente aus, für das Sie den ereignishandlerhandle festlegen möchten.  
  
3. Wählen Sie im Dropdown Feld **Methoden Name** eines der Ereignisse aus, die vom Ereignishandler behandelt werden sollen.  
  
4. Der Code-Editor fügt den entsprechenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode. Im folgenden Beispiel ist es das <xref:System.Windows.Forms.Control.Click>-Ereignis für das <xref:System.Windows.Forms.Button>-Steuerelement.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. Fügen Sie die anderen Ereignisse, die Sie behandeln möchten, an die `Handles`-Klausel an.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. Fügen Sie dem-Ereignishandler den entsprechenden Code hinzu.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in C\#
  
1. Wählen Sie das Steuerelement aus, mit dem Sie einen Ereignishandler verbinden möchten.  
  
2. Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Ereignisse** (![Ereignis Schaltfläche](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3. Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.  
  
4. Klicken Sie im Abschnitt Wert neben dem Ereignis Namen auf die Dropdown Schaltfläche, um eine Liste mit den vorhandenen Ereignis Handlern anzuzeigen, die der Methoden Signatur des Ereignisses entsprechen, das Sie verarbeiten möchten.  
  
5. Wählen Sie den entsprechenden Ereignishandler aus der Liste aus.  
  
     Der Code wird dem Formular hinzugefügt, um das Ereignis an den vorhandenen Ereignishandler zu binden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)
