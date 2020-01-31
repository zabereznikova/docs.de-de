---
title: 'Vorgehensweise: Anzeigen von Dialog Feldern'
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
ms.openlocfilehash: dd04a06eaa0dd7583ef2f72edb4cffa99aaaa60c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739464"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms
Sie können ein Dialogfeld auf die gleiche Weise wie andere Formulare in einer Anwendung anzeigen. Das Start Formular wird automatisch geladen, wenn die Anwendung ausgeführt wird. Damit ein zweites Formular oder Dialogfeld in der Anwendung angezeigt wird, schreiben Sie Code, um ihn zu laden und anzuzeigen. Wenn Sie das Formular oder Dialogfeld ausblenden möchten, schreiben Sie den Code, um ihn zu entladen oder auszublenden.  
  
### <a name="to-display-a-dialog-box"></a>So zeigen Sie ein Dialogfeld an  
  
1. Navigieren Sie zu dem Ereignishandler, mit dem Sie das Dialogfeld öffnen möchten. Dies kann vorkommen, wenn ein Menübefehl ausgewählt wird, wenn auf eine Schaltfläche geklickt wird oder wenn ein beliebiges anderes Ereignis auftritt.  
  
2. Fügen Sie im-Ereignishandler Code hinzu, um das Dialogfeld zu öffnen. In diesem Beispiel wird ein Button-Click-Ereignis verwendet, um das Dialogfeld anzuzeigen:  
  
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
