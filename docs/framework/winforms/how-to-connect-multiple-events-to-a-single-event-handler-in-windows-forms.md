---
title: 'Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignis Handler'
description: Erfahren Sie, wie Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in Windows Forms verbinden, indem Sie die Ereignisansicht des Eigenschaftenfenster in c# verwenden.
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
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621885"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="27936-103">Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27936-103">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="27936-104">Beim Anwendungs Entwurf ist es möglicherweise erforderlich, dass ein einzelner Ereignishandler für mehrere Ereignisse verwendet wird, oder dass mehrere Ereignisse dieselbe Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="27936-104">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="27936-105">Beispielsweise ist es häufig ein leistungsfähiger Zeitersparnis, wenn ein Menübefehl dasselbe Ereignis wie eine Schaltfläche auf dem Formular aufhebt, wenn Sie die gleiche Funktionalität verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="27936-105">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="27936-106">Hierzu können Sie die Ereignisansicht der Eigenschaftenfenster in c# oder das `Handles` Schlüsselwort und die Dropdown Felder **Klassenname** und **Methodenname** im Visual Basic Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="27936-106">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="27936-107">So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27936-107">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="27936-108">Klicken Sie mit der rechten Maustaste, und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="27936-108">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="27936-109">Wählen Sie im Dropdown Feld **Klassen Name** eines der Steuerelemente aus, für das Sie den ereignishandlerhandle festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="27936-109">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="27936-110">Wählen Sie im Dropdown Feld **Methoden Name** eines der Ereignisse aus, die vom Ereignishandler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="27936-110">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="27936-111">Der Code-Editor fügt den entsprechenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode.</span><span class="sxs-lookup"><span data-stu-id="27936-111">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="27936-112">Im folgenden Beispiel ist es das- <xref:System.Windows.Forms.Control.Click> Ereignis für das- <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="27936-112">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="27936-113">Fügen Sie die anderen Ereignisse, die Sie behandeln möchten, an die- `Handles` Klausel an.</span><span class="sxs-lookup"><span data-stu-id="27936-113">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="27936-114">Fügen Sie dem-Ereignishandler den entsprechenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="27936-114">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="27936-115">So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in C\#</span><span class="sxs-lookup"><span data-stu-id="27936-115">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="27936-116">Wählen Sie das Steuerelement aus, mit dem Sie einen Ereignishandler verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="27936-116">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="27936-117">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Ereignisse** (![Ereignis Schaltfläche](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="27936-117">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="27936-118">Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="27936-118">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="27936-119">Klicken Sie im Abschnitt Wert neben dem Ereignis Namen auf die Dropdown Schaltfläche, um eine Liste mit den vorhandenen Ereignis Handlern anzuzeigen, die der Methoden Signatur des Ereignisses entsprechen, das Sie verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="27936-119">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="27936-120">Wählen Sie den entsprechenden Ereignishandler aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="27936-120">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="27936-121">Der Code wird dem Formular hinzugefügt, um das Ereignis an den vorhandenen Ereignishandler zu binden.</span><span class="sxs-lookup"><span data-stu-id="27936-121">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27936-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27936-122">See also</span></span>

- [<span data-ttu-id="27936-123">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27936-123">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="27936-124">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="27936-124">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
