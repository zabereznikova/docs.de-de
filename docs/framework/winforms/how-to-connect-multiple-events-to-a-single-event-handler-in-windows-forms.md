---
title: 'Vorgehensweise: Verbinden Sie mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 527e2c594f236f94ce23e4fd21238b8605af308c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502442"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="2e825-102">Vorgehensweise: Verbinden Sie mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e825-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="2e825-103">In Ihrem Datenbankentwurf möglicherweise finden Sie es auf einen einzelnen Ereignishandler mehrere Ereignisse oder bei mehreren Ereignissen führen Sie das gleiche Verfahren erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e825-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="2e825-104">Beispielsweise ist es oft eine leistungsstarke Zeitersparnis haben Sie einen Menübefehl, der das gleiche Ereignis auslösen, wie eine Schaltfläche im Formular ausgeführt werden, wenn sie die gleiche Funktionalität verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="2e825-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="2e825-105">Sie erreichen dies, indem Sie die Ansicht "Ereignisse" im Eigenschaftenfenster in C# oder mithilfe der `Handles` Schlüsselwort und die **Klassenname** und **Methodenname** Dropdownfelder in Visual Basic-Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="2e825-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="2e825-106">Zum Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e825-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="2e825-107">Mit der rechten Maustaste in des Formulars, und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="2e825-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="2e825-108">Von der **Klassenname** Dropdown-Feld, wählen Sie eines der Steuerelemente, die die Ereignishandler, die verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e825-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="2e825-109">Von der **Methodenname** Dropdown-Feld, wählen Sie eines der Ereignisse, die Sie den Ereignishandler behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2e825-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="2e825-110">Code-Editor fügt den passenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode.</span><span class="sxs-lookup"><span data-stu-id="2e825-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="2e825-111">Im folgenden Beispiel ist es die <xref:System.Windows.Forms.Control.Click> -Ereignis für die <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e825-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="2e825-112">Fügen Sie die anderen Ereignisse werden soll behandelt der `Handles` Klausel.</span><span class="sxs-lookup"><span data-stu-id="2e825-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="2e825-113">Fügen Sie den entsprechenden Code zum Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e825-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="2e825-114">Zum Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler inC#</span><span class="sxs-lookup"><span data-stu-id="2e825-114">To connect multiple events to a single event handler in C#</span></span>  
  
1.  <span data-ttu-id="2e825-115">Wählen Sie das Steuerelement, das Sie einen Ereignishandler eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e825-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="2e825-116">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Schaltfläche (![Schaltfläche "Ereignisse"](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "VxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="2e825-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="2e825-117">Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2e825-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="2e825-118">Klicken Sie im Abschnitt Value neben dem Ereignisnamen auf die Dropdown-Schaltfläche, um eine Liste der vorhandenen Ereignishandler anzuzeigen, die die Signatur der Methode des Ereignisses zu entsprechen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="2e825-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="2e825-119">Wählen Sie den entsprechenden Ereignishandler aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2e825-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="2e825-120">Code wird das Formular, um das Ereignis zu binden, auf dem vorhandenen Ereignishandler hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2e825-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e825-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e825-121">See also</span></span>
- [<span data-ttu-id="2e825-122">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e825-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="2e825-123">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="2e825-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
