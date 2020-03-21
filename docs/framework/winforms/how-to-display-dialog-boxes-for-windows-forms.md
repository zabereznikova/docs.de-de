---
title: 'Gewusst wie: Anzeigen von Dialogfeldern'
ms.date: 03/30/2017
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
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181971"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms
Sie zeigen ein Dialogfeld auf die gleiche Weise an, wie Sie jedes andere Formular in einer Anwendung anzeigen. Das Startformular wird automatisch geladen, wenn die Anwendung ausgeführt wird. Um ein zweites Formular oder Dialogfeld in der Anwendung anzuzeigen, schreiben Sie Code, um ihn zu laden und anzuzeigen. Wenn Sie das Formular oder Dialogfeld verschwinden lassen, schreiben Sie Code, um ihn zu entladen oder auszublenden.  
  
### <a name="to-display-a-dialog-box"></a>So zeigen Sie ein Dialogfeld an  
  
1. Navigieren Sie zu dem Ereignishandler, mit dem Sie das Dialogfeld öffnen möchten. Dies kann passieren, wenn ein Menübefehl ausgewählt ist, wenn auf eine Schaltfläche geklickt wird oder wenn ein anderes Ereignis eintritt.  
  
2. Fügen Sie im Ereignishandler Code hinzu, um das Dialogfeld zu öffnen. In diesem Beispiel wird ein Schaltflächenklick-Ereignis verwendet, um das Dialogfeld anzuzeigen:  
  
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
