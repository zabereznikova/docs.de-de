---
title: "Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f827e9052260c1b836246d38c55e2cb2a9e5cc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms
Ein Dialogfeld wird angezeigt, auf die gleiche Weise, die Sie in einer Anwendung eine andere Art anzeigen. Die Startformular lädt automatisch auf, wenn die Anwendung ausgeführt wird. Stellen Sie ein zweites Formular oder Dialogfeld in der Anwendung angezeigt, Schreiben Sie Code geladen und angezeigt wird. Auf ähnliche Weise, um das Formular oder Dialogfeld auszublenden, Schreiben Sie Code zum Entfernen oder ausblenden.  
  
### <a name="to-display-a-dialog-box"></a>Um ein Dialogfeld anzuzeigen.  
  
1.  Navigieren Sie zu der Ereignishandler mit dem Öffnen des Dialogfelds werden soll. Dies kann geschehen, wenn Sie ein Menübefehl ausgewählt ist, wenn auf eine Schaltfläche geklickt wird, oder wenn alle anderen Ereignisse auftreten.  
  
2.  Fügen Sie im Ereignishandler Code hinzu, um das Dialogfeld zu öffnen. In diesem Beispiel wird eine Schaltfläche – Click-Ereignis verwendet, um das Dialogfeld anzuzeigen:  
  
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
