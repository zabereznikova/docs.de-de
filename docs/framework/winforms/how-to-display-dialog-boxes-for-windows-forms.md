---
title: 'Vorgehensweise: Anzeigen von Dialogfeldern für Windows Forms'
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
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773817"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Vorgehensweise: Anzeigen von Dialogfeldern für Windows Forms
Sie anzeigen ein Dialogfeld, auf die gleiche Weise, die Sie eine andere Form in einer Anwendung anzeigen. Das Startformular lädt automatisch auf, wenn die Anwendung ausgeführt wird. Damit wird ein zweites Formular oder Dialogfeld in der Anwendung angezeigt werden, Schreiben Sie Code zum Laden und anzeigen. Auf ähnliche Weise, um das Formular oder Dialogfeld auszublenden, Schreiben Sie Code zum Entladen oder auszublenden.  
  
### <a name="to-display-a-dialog-box"></a>Um ein Dialogfeld anzuzeigen.  
  
1. Navigieren Sie an den Ereignishandler mit dem Sie das Dialogfeld öffnen möchten. Dies kann vorkommen, wenn ein Menübefehl aktiviert ist, wenn auf eine Schaltfläche geklickt wird, oder jedes andere Ereignis auftritt.  
  
2. Fügen Sie im Ereignishandler Code, um das Dialogfeld zu öffnen. In diesem Beispiel wird eine Schaltfläche – Click-Ereignis verwendet, um das Dialogfeld anzuzeigen:  
  
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
