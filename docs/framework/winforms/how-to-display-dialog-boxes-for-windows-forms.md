---
title: 'Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms'
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
ms.openlocfilehash: a25fe86c4dde1fed69e192956d77615bf2a70402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537423"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="d053d-102">Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d053d-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="d053d-103">Ein Dialogfeld wird angezeigt, auf die gleiche Weise, die Sie in einer Anwendung eine andere Art anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d053d-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="d053d-104">Die Startformular lädt automatisch auf, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d053d-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="d053d-105">Stellen Sie ein zweites Formular oder Dialogfeld in der Anwendung angezeigt, Schreiben Sie Code geladen und angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d053d-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="d053d-106">Auf ähnliche Weise, um das Formular oder Dialogfeld auszublenden, Schreiben Sie Code zum Entfernen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="d053d-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="d053d-107">Um ein Dialogfeld anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d053d-107">To display a dialog box</span></span>  
  
1.  <span data-ttu-id="d053d-108">Navigieren Sie zu der Ereignishandler mit dem Öffnen des Dialogfelds werden soll.</span><span class="sxs-lookup"><span data-stu-id="d053d-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="d053d-109">Dies kann geschehen, wenn Sie ein Menübefehl ausgewählt ist, wenn auf eine Schaltfläche geklickt wird, oder wenn alle anderen Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="d053d-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2.  <span data-ttu-id="d053d-110">Fügen Sie im Ereignishandler Code hinzu, um das Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d053d-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="d053d-111">In diesem Beispiel wird eine Schaltfläche – Click-Ereignis verwendet, um das Dialogfeld anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d053d-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
