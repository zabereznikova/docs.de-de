---
title: 'Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignis Handler'
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
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739607"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="f730b-102">Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f730b-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="f730b-103">Beim Anwendungs Entwurf ist es möglicherweise erforderlich, dass ein einzelner Ereignishandler für mehrere Ereignisse verwendet wird, oder dass mehrere Ereignisse dieselbe Prozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="f730b-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="f730b-104">Beispielsweise ist es häufig ein leistungsfähiger Zeitersparnis, wenn ein Menübefehl dasselbe Ereignis wie eine Schaltfläche auf dem Formular aufhebt, wenn Sie die gleiche Funktionalität verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="f730b-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="f730b-105">Hierzu können Sie die Ereignisansicht der Eigenschaftenfenster in C# oder das `Handles`-Schlüsselwort und die Dropdown Felder **Klassenname** und **Methodenname** im Visual Basic Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="f730b-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="f730b-106">So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f730b-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="f730b-107">Klicken Sie mit der rechten Maustaste, und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="f730b-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="f730b-108">Wählen Sie im Dropdown Feld **Klassen Name** eines der Steuerelemente aus, für das Sie den ereignishandlerhandle festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="f730b-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="f730b-109">Wählen Sie im Dropdown Feld **Methoden Name** eines der Ereignisse aus, die vom Ereignishandler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f730b-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="f730b-110">Der Code-Editor fügt den entsprechenden Ereignishandler ein und positioniert die Einfügemarke innerhalb der Methode.</span><span class="sxs-lookup"><span data-stu-id="f730b-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="f730b-111">Im folgenden Beispiel ist es das <xref:System.Windows.Forms.Control.Click>-Ereignis für das <xref:System.Windows.Forms.Button>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f730b-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="f730b-112">Fügen Sie die anderen Ereignisse, die Sie behandeln möchten, an die `Handles`-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="f730b-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="f730b-113">Fügen Sie dem-Ereignishandler den entsprechenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f730b-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="f730b-114">So verbinden Sie mehrere Ereignisse mit einem einzelnen Ereignishandler in C\#</span><span class="sxs-lookup"><span data-stu-id="f730b-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="f730b-115">Wählen Sie das Steuerelement aus, mit dem Sie einen Ereignishandler verbinden möchten.</span><span class="sxs-lookup"><span data-stu-id="f730b-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="f730b-116">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Ereignisse** (![Ereignis Schaltfläche](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="f730b-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="f730b-117">Klicken Sie auf den Namen des Ereignisses, das Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="f730b-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="f730b-118">Klicken Sie im Abschnitt Wert neben dem Ereignis Namen auf die Dropdown Schaltfläche, um eine Liste mit den vorhandenen Ereignis Handlern anzuzeigen, die der Methoden Signatur des Ereignisses entsprechen, das Sie verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="f730b-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="f730b-119">Wählen Sie den entsprechenden Ereignishandler aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="f730b-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="f730b-120">Der Code wird dem Formular hinzugefügt, um das Ereignis an den vorhandenen Ereignishandler zu binden.</span><span class="sxs-lookup"><span data-stu-id="f730b-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f730b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f730b-121">See also</span></span>

- [<span data-ttu-id="f730b-122">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f730b-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="f730b-123">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="f730b-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
