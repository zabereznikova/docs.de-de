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
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="2047c-102">Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2047c-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="2047c-103">In Ihrem Datenbankentwurf vielleicht Sie finden es notwendig, einen einzelnen Ereignishandler für mehrere Ereignisse bzw. mehrere Ereignisse, die die gleiche Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="2047c-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="2047c-104">Beispielsweise ist es oft eine leistungsstarke Zeitersparnis haben einen Menübefehl, lösen Sie das gleiche Ereignis, wie eine Schaltfläche auf dem Formular wird, wenn sie die gleiche Funktionalität verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="2047c-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="2047c-105">Hierzu können Sie mithilfe der Ereignisansicht des Eigenschaftenfensters in c# oder mit der `Handles` Schlüsselwort und die **Klassenname** und **Methodennamen** Dropdownfelder in Visual Basic-Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="2047c-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="2047c-106">So verbinden mehrere Ereignisse mit einem einzelnen Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2047c-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="2047c-107">Mit der rechten Maustaste in des Formulars, und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2047c-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="2047c-108">Aus der **Klassenname** Dropdown-Feld, wählen Sie eines der Steuerelemente, die vom Ereignishandler verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2047c-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="2047c-109">Aus der **Methodennamen** Dropdown-Feld, wählen Sie eine der Ereignisse, die Sie den Ereignishandler behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2047c-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="2047c-110">Der Code-Editor fügt den passenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode.</span><span class="sxs-lookup"><span data-stu-id="2047c-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="2047c-111">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Click> -Ereignis für die <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2047c-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="2047c-112">Fügen Sie die anderen Ereignisse möchten behandelt die `Handles` Klausel.</span><span class="sxs-lookup"><span data-stu-id="2047c-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="2047c-113">Fügen Sie den entsprechenden Code an den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="2047c-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="2047c-114">So verbinden mehrere Ereignisse mit einem einzelnen Ereignishandler in c#</span><span class="sxs-lookup"><span data-stu-id="2047c-114">To connect multiple events to a single event handler in C#</span></span>  
  
1.  <span data-ttu-id="2047c-115">Wählen Sie das Steuerelement, das Sie einen Ereignishandler eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2047c-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="2047c-116">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche (![Schaltfläche "Ereignisse"](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "VxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="2047c-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="2047c-117">Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2047c-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="2047c-118">Klicken Sie auf die Dropdown-Schaltfläche, um eine Liste der vorhandenen Ereignishandler anzuzeigen, die die Methodensignatur des Ereignisses entsprechen, die Sie behandeln möchten, klicken Sie im Bereich Wert neben dem Ereignisnamen.</span><span class="sxs-lookup"><span data-stu-id="2047c-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="2047c-119">Wählen Sie aus der Liste den passenden Ereignishandler ein.</span><span class="sxs-lookup"><span data-stu-id="2047c-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="2047c-120">Code wird dem Formular so binden Sie das Ereignis an dem vorhandenen Ereignishandler hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2047c-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2047c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2047c-121">See Also</span></span>  
 [<span data-ttu-id="2047c-122">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2047c-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="2047c-123">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="2047c-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
