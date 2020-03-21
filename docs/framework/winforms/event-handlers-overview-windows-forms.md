---
title: Übersicht über Ereignishandler
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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141691"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="1ff53-102">Übersicht über Ereignishandler (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1ff53-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="1ff53-103">Ein Ereignishandler ist eine Methode, die an ein Ereignis gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="1ff53-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="1ff53-104">Wenn das Ereignis ausgelöst wird, wird der Code innerhalb des Ereignishandlers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ff53-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="1ff53-105">Jeder Ereignishandler stellt zwei Parameter bereit, mit denen Sie das Ereignis ordnungsgemäß behandeln können.</span><span class="sxs-lookup"><span data-stu-id="1ff53-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="1ff53-106">Das folgende Beispiel zeigt einen <xref:System.Windows.Forms.Button> Ereignishandler <xref:System.Windows.Forms.Control.Click> für das Ereignis eines Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="1ff53-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="1ff53-107">Der erste`sender`Parameter , stellt einen Verweis auf das Objekt bereit, das das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="1ff53-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="1ff53-108">Der zweite `e`Parameter, im obigen Beispiel, übergibt ein Objekt, das für das behandelte Ereignis spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="1ff53-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="1ff53-109">Durch Verweisen auf die Eigenschaften des Objekts (und manchmal auch auf seine Methoden) können Sie Informationen wie die Position der Maus für Mausereignisse oder Daten abrufen, die in Drag-and-Drop-Ereignissen übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1ff53-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="1ff53-110">In der Regel erzeugt jedes Ereignis einen Ereignishandler mit einem anderen Ereignisobjekttyp für den zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="1ff53-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="1ff53-111">Einige Ereignishandler, z. B. für die <xref:System.Windows.Forms.Control.MouseDown> und-Ereignisse, <xref:System.Windows.Forms.Control.MouseUp> haben denselben Objekttyp für ihren zweiten Parameter.</span><span class="sxs-lookup"><span data-stu-id="1ff53-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="1ff53-112">Für diese Ereignistypen können Sie denselben Ereignishandler verwenden, um beide Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="1ff53-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="1ff53-113">Sie können auch denselben Ereignishandler verwenden, um dasselbe Ereignis für verschiedene Steuerelemente zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="1ff53-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="1ff53-114">Wenn Sie z. B. <xref:System.Windows.Forms.RadioButton> über eine Gruppe von Steuerelementen in <xref:System.Windows.Forms.Control.Click> einem Formular verfügen, <xref:System.Windows.Forms.Control.Click> können Sie einen einzelnen Ereignishandler für das Ereignis erstellen und das Ereignis jedes Steuerelements an den einzelnen Ereignishandler binden lassen.</span><span class="sxs-lookup"><span data-stu-id="1ff53-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="1ff53-115">Weitere Informationen finden Sie unter [Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1ff53-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff53-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ff53-116">See also</span></span>

- [<span data-ttu-id="1ff53-117">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ff53-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="1ff53-118">Übersicht über Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1ff53-118">Events Overview</span></span>](events-overview-windows-forms.md)
