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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311083"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="545da-102">Vorgehensweise: Anzeigen von Dialogfeldern für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545da-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="545da-103">Sie anzeigen ein Dialogfeld, auf die gleiche Weise, die Sie eine andere Form in einer Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="545da-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="545da-104">Das Startformular lädt automatisch auf, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="545da-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="545da-105">Damit wird ein zweites Formular oder Dialogfeld in der Anwendung angezeigt werden, Schreiben Sie Code zum Laden und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="545da-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="545da-106">Auf ähnliche Weise, um das Formular oder Dialogfeld auszublenden, Schreiben Sie Code zum Entladen oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="545da-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="545da-107">Um ein Dialogfeld anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="545da-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="545da-108">Navigieren Sie an den Ereignishandler mit dem Sie das Dialogfeld öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="545da-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="545da-109">Dies kann vorkommen, wenn ein Menübefehl aktiviert ist, wenn auf eine Schaltfläche geklickt wird, oder jedes andere Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="545da-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="545da-110">Fügen Sie im Ereignishandler Code, um das Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="545da-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="545da-111">In diesem Beispiel wird eine Schaltfläche – Click-Ereignis verwendet, um das Dialogfeld anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="545da-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
