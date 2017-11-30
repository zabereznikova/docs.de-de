---
title: "Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4aa22b011b895a20cefdcc5a7c9e6c1cd0531923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms
In Ihrem Datenbankentwurf vielleicht Sie finden es notwendig, einen einzelnen Ereignishandler für mehrere Ereignisse bzw. mehrere Ereignisse, die die gleiche Prozedur ausführen. Beispielsweise ist es oft eine leistungsstarke Zeitersparnis haben einen Menübefehl, lösen Sie das gleiche Ereignis, wie eine Schaltfläche auf dem Formular wird, wenn sie die gleiche Funktionalität verfügbar machen. Hierzu können Sie mithilfe der Ereignisansicht des Eigenschaftenfensters in c# oder mit der `Handles` Schlüsselwort und die **Klassenname** und **Methodennamen** Dropdownfelder in Visual Basic-Code-Editor.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>So verbinden mehrere Ereignisse mit einem einzelnen Ereignishandler in Visual Basic  
  
1.  Mit der rechten Maustaste in des Formulars, und wählen Sie **Code anzeigen**.  
  
2.  Aus der **Klassenname** Dropdown-Feld, wählen Sie eines der Steuerelemente, die vom Ereignishandler verarbeitet werden sollen.  
  
3.  Aus der **Methodennamen** Dropdown-Feld, wählen Sie eine der Ereignisse, die Sie den Ereignishandler behandeln möchten.  
  
4.  Der Code-Editor fügt den passenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode. Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Click> -Ereignis für die <xref:System.Windows.Forms.Button> Steuerelement.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Fügen Sie die anderen Ereignisse möchten behandelt die `Handles` Klausel.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Fügen Sie den entsprechenden Code an den Ereignishandler an.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>So verbinden mehrere Ereignisse mit einem einzelnen Ereignishandler in c#  
  
1.  Wählen Sie das Steuerelement, das Sie einen Ereignishandler eine Verbindung herstellen möchten.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche (![Schaltfläche "Ereignisse"](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "VxEventsButton_PropertiesWindow")).  
  
3.  Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.  
  
4.  Klicken Sie auf die Dropdown-Schaltfläche, um eine Liste der vorhandenen Ereignishandler anzuzeigen, die die Methodensignatur des Ereignisses entsprechen, die Sie behandeln möchten, klicken Sie im Bereich Wert neben dem Ereignisnamen.  
  
5.  Wählen Sie aus der Liste den passenden Ereignishandler ein.  
  
     Code wird dem Formular so binden Sie das Ereignis an dem vorhandenen Ereignishandler hinzugefügt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
