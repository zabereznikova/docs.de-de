---
title: Definieren eines Ereignisses in Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: a4738373b10fbcb1d2406406d30f10b795aeb914
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228839"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="acc22-102">Definieren eines Ereignisses in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="acc22-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="acc22-103">Weitere Informationen zum Definieren benutzerdefinierter Ereignisse finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="acc22-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="acc22-104">Wenn Sie ein Ereignis definieren, das nicht über verknüpfte Daten verfügt, nutzen Sie den Basistyp für Ereignisdaten, <xref:System.EventArgs>, und <xref:System.EventHandler> als Ereignisdelegaten.</span><span class="sxs-lookup"><span data-stu-id="acc22-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="acc22-105">Es bleibt nur noch zu definieren, dass `On`ein Ereignismember und eine geschützte *EventName-Methode* definiert werden, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="acc22-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="acc22-106">Das folgende Codefragment zeigt, wie das benutzerdefinierte `FlashTrackBar`-Steuerelement ein benutzerdefiniertes Ereignis definiert, `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="acc22-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="acc22-107">Den vollständigen Code `FlashTrackBar` für das Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows-Formularsteuerelements, das den Fortschritt anzeigt.](how-to-create-a-windows-forms-control-that-shows-progress.md)</span><span class="sxs-lookup"><span data-stu-id="acc22-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       onValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="acc22-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acc22-108">See also</span></span>

- [<span data-ttu-id="acc22-109">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="acc22-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="acc22-110">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="acc22-110">Events</span></span>](../../../standard/events/index.md)
