---
title: "Gewusst wie: Anzeigen von Dialogfeldern f&#252;r Windows&#160;Forms | Microsoft Docs"
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
  - "Dialogfelder, Anzeigen für Windows Forms"
  - "Windows Forms-Dialogfelder, Anzeigen"
  - "Windows Forms, Aufrufen eines Formulars aus einem anderen"
  - "Windows Forms, Anzeigen"
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Anzeigen von Dialogfeldern f&#252;r Windows&#160;Forms
Ein Dialogfeld wird auf dieselbe Weise wie andere Formulare in einer Anwendung angezeigt.  Sobald die Anwendung ausgeführt wird, wird das Startformular automatisch gestartet.  Um ein zweites Formular oder Dialogfeld in der Anwendung anzuzeigen, schreiben Sie Code, durch den es geladen und angezeigt wird.  Um das Formular oder Dialogfeld auszublenden, schreiben Sie Code, durch den es entladen bzw. verborgen wird.  
  
### So zeigen Sie ein Dialogfeld an  
  
1.  Navigieren Sie zu dem Ereignishandler, mit dem das Dialogfeld geöffnet werden soll.  Der Handler wird z. B. ausgelöst, wenn ein Menübefehl ausgewählt oder auf eine Schaltfläche geklickt wird bzw. wenn ein anderes Ereignis eintritt.  
  
2.  Fügen Sie dem Ereignishandler Code zum Öffnen des Dialogfelds hinzu.  In diesem Beispiel wird ein **Click**\-Ereignis für eine Schaltfläche verwendet, um das Dialogfeld anzuzeigen:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```