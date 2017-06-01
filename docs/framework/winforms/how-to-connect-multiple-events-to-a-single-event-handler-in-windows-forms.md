---
title: "Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Ereignishandler [Windows Forms], Verbinden mit Ereignissen"
  - "Ereignisse [Windows Forms], Verbinden mehrerer mit einem einzelnen Ereignishandler"
  - "Menüelemente, Multicasting-Ereignisbehandlungsmethoden"
  - "Menüs, Ereignisbehandlungsmethoden für mehrere Menüelemente"
  - "Windows Forms-Steuerelemente, Ereignisse"
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows&#160;Forms
Bei der Anwendungsentwicklung kann es erforderlich sein, dass ein einzelner Ereignishandler für mehrere Ereignisse verwendet wird oder mehrere Ereignisse dieselbe Prozedur ausführen.  Beispielsweise ist es oft wesentlich zeitsparender, wenn ein Menübefehl und eine Schaltfläche dasselbe Ereignis im Formular auslösen, vorausgesetzt, beide verfügen über dieselbe Funktion.  Verwenden Sie dazu die Ereignisansicht des Eigenschaftenfensters in C\# oder das `Handles` \-Schlüsselwort und die Dropdown\-Listenfelder **Klassenname** und **Methodenname** im Code\-Editor von Visual Basic.  
  
### So verbinden Sie in Visual Basic mehrere Ereignisse mit einem einzigen Ereignishandler  
  
1.  Klicken Sie mit der rechten Maustaste auf das Formular, und wählen Sie **Code anzeigen**.  
  
2.  Wählen Sie aus dem Dropdown\-Listenfeld **Klassenname** eines der Steuerelemente aus, das vom Ereignishandler verarbeitet werden soll.  
  
3.  Wählen Sie aus dem Dropdown\-Listenfeld **Methodenname** eines der Ereignisse aus, das vom Ereignishandler verarbeitet werden soll.  
  
4.  Der Code\-Editor fügt den entsprechenden Ereignishandler ein und positioniert die Einfügemarke in der Methode.  Im Beispiel unten ist dies das <xref:System.Windows.Forms.Control.Click>\-Ereignis für das <xref:System.Windows.Forms.Button>\-Steuerelement.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Hängen Sie die anderen Ereignisse, die bearbeitet werden sollen, an die `Handles` \-Klausel an.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Fügen Sie dem Ereignishandler den entsprechenden Code hinzu.  
  
### So verbinden Sie in C\# mehrere Ereignisse mit einem einzigen Ereignishandler  
  
1.  Wählen Sie das Steuerelement aus, das mit einem Ereignishandler verbunden werden soll.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Ereignisse** \(![Schaltfläche "Ereignisse"](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton\_PropertiesWindow")\).  
  
3.  Klicken Sie auf den Namen des Ereignisses, das verarbeitet werden soll.  
  
4.  Klicken Sie im Wertebereich neben dem Ereignisnamen auf die Dropdown\-Schaltfläche, um eine Liste vorhandener Ereignishandler anzuzeigen, die der Methodensignatur des zu verarbeitenden Ereignisses entsprechen.  
  
5.  Wählen Sie den geeigneten Ereignishandler aus der Liste aus.  
  
     Dem Formular wird Code hinzugefügt, durch den das Ereignis an den vorhandenen Ereignishandler gebunden wird.  
  
## Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)