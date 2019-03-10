---
title: Übersicht über Ereignishandler (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 6dbcffadfd484dc33db2fcd3ee3f680dcc0740e5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703386"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="c72c6-102">Übersicht über Ereignishandler (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c72c6-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="c72c6-103">Ein Ereignishandler ist eine Methode, die auf ein Ereignis gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="c72c6-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="c72c6-104">Wenn das Ereignis ausgelöst wird, wird der Code innerhalb des ereignishandlers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c72c6-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="c72c6-105">Jeder Ereignishandler enthält zwei Parameter, die Ihnen ermöglichen, die das Ereignis ordnungsgemäß zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c72c6-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="c72c6-106">Das folgende Beispiel zeigt einen Ereignishandler für ein <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="c72c6-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="c72c6-107">Der erste Parameter,`sender`, stellt einen Verweis auf das Objekt, das das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="c72c6-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="c72c6-108">Der zweite Parameter, `e`, im obigen Beispiel übergibt ein spezifisches Objekt an das Ereignis, das behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="c72c6-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="c72c6-109">Durch Verweisen auf die Eigenschaften des Objekts (und in einigen Fällen ihre Methoden), erhalten Sie Informationen wie z. B. die Position des Mauszeigers für Mausereignisse oder Daten, die Drag & Drop-Ereignisse übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="c72c6-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="c72c6-110">In der Regel führt jedes Ereignis einen Ereignishandler mit einem anderen Ereignis-Objekt für den zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="c72c6-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="c72c6-111">Einige Ereignishandler, etwa solche für die <xref:System.Windows.Forms.Control.MouseDown> und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse weisen denselben Objekttyp für ihre zweite Parameter.</span><span class="sxs-lookup"><span data-stu-id="c72c6-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="c72c6-112">Für diese Arten von Ereignissen können Sie denselben Ereignishandler, um beide Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c72c6-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="c72c6-113">Sie können auch den Ereignishandler zum Behandeln des gleichen Ereignisses für verschiedene Steuerelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="c72c6-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="c72c6-114">Für, wenn Sie z. B. eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente eines Formulars, können Sie einen einzelnen Ereignishandler für erstellen die <xref:System.Windows.Forms.Control.Click> Ereignis und jedes Steuerelement die <xref:System.Windows.Forms.Control.Click> Ereignis gebunden, um die einzelnen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c72c6-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="c72c6-115">Weitere Informationen finden Sie unter [Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c72c6-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72c6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c72c6-116">See also</span></span>
- [<span data-ttu-id="c72c6-117">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c72c6-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="c72c6-118">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c72c6-118">Events Overview</span></span>](events-overview-windows-forms.md)
