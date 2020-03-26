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
# <a name="defining-an-event-in-windows-forms-controls"></a>Definieren eines Ereignisses in Windows Forms-Steuerelementen
Weitere Informationen zum Definieren benutzerdefinierter Ereignisse finden Sie unter [Ereignisse](../../../standard/events/index.md). Wenn Sie ein Ereignis definieren, das nicht über verknüpfte Daten verfügt, nutzen Sie den Basistyp für Ereignisdaten, <xref:System.EventArgs>, und <xref:System.EventHandler> als Ereignisdelegaten. Es bleibt nur noch zu definieren, dass `On`ein Ereignismember und eine geschützte *EventName-Methode* definiert werden, die das Ereignis auslöst.  
  
 Das folgende Codefragment zeigt, wie das benutzerdefinierte `FlashTrackBar`-Steuerelement ein benutzerdefiniertes Ereignis definiert, `ValueChanged`. Den vollständigen Code `FlashTrackBar` für das Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows-Formularsteuerelements, das den Fortschritt anzeigt.](how-to-create-a-windows-forms-control-that-shows-progress.md)  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse in Windows Forms-Steuerelementen](events-in-windows-forms-controls.md)
- [Ereignisse](../../../standard/events/index.md)
