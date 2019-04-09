---
title: 'Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms'
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
ms.openlocfilehash: d55ccc21efb92ba1e51f4ae88be5025f2f80905b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117961"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms
In Ihrem Datenbankentwurf möglicherweise finden Sie es auf einen einzelnen Ereignishandler mehrere Ereignisse oder bei mehreren Ereignissen führen Sie das gleiche Verfahren erforderlich. Beispielsweise ist es oft eine leistungsstarke Zeitersparnis haben Sie einen Menübefehl, der das gleiche Ereignis auslösen, wie eine Schaltfläche im Formular ausgeführt werden, wenn sie die gleiche Funktionalität verfügbar machen. Sie erreichen dies, indem Sie die Ansicht "Ereignisse" im Eigenschaftenfenster in C# oder mithilfe der `Handles` Schlüsselwort und die **Klassenname** und **Methodenname** Dropdownfelder in Visual Basic-Code-Editor.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Zum Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Visual Basic  
  
1.  Mit der rechten Maustaste in des Formulars, und wählen Sie **Ansichtscode**.  
  
2.  Von der **Klassenname** Dropdown-Feld, wählen Sie eines der Steuerelemente, die die Ereignishandler, die verarbeitet werden sollen.  
  
3.  Von der **Methodenname** Dropdown-Feld, wählen Sie eines der Ereignisse, die Sie den Ereignishandler behandeln möchten.  
  
4.  Code-Editor fügt den passenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode. Im folgenden Beispiel ist es die <xref:System.Windows.Forms.Control.Click> -Ereignis für die <xref:System.Windows.Forms.Button> Steuerelement.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Fügen Sie die anderen Ereignisse werden soll behandelt der `Handles` Klausel.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Fügen Sie den entsprechenden Code zum Ereignishandler hinzu.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>So verbinden mehrere Ereignisse mit einem einzelnen Ereignishandler in C\#
  
1.  Wählen Sie das Steuerelement, das Sie einen Ereignishandler eine Verbindung herstellen möchten.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche (![Schaltfläche "Ereignisse"](./media/vxeventsbutton-propertieswindow.png "VxEventsButton_PropertiesWindow")).  
  
3.  Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.  
  
4.  Klicken Sie im Abschnitt Value neben dem Ereignisnamen auf die Dropdown-Schaltfläche, um eine Liste der vorhandenen Ereignishandler anzuzeigen, die die Signatur der Methode des Ereignisses zu entsprechen, die Sie behandeln möchten.  
  
5.  Wählen Sie den entsprechenden Ereignishandler aus der Liste aus.  
  
     Code wird das Formular, um das Ereignis zu binden, auf dem vorhandenen Ereignishandler hinzugefügt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)
