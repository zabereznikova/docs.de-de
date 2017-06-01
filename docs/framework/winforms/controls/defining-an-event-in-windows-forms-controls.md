---
title: "Definieren eines Ereignisses in Windows&#160;Forms-Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Ereignisse mit Code"
  - "Ereignisse [Windows Forms], Definieren in benutzerdefinierten Windows Forms-Steuerelementen"
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Definieren eines Ereignisses in Windows&#160;Forms-Steuerelementen
Detaillierte Informationen zum Definieren benutzerdefinierter Ereignisse finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).  Wenn Sie ein Ereignis definieren, das nicht über verknüpfte Daten verfügt, nutzen Sie den Basistyp für Ereignisdaten, <xref:System.EventArgs>, und <xref:System.EventHandler> als Ereignisdelegaten.  Sie müssen nur noch ein Ereignismember definieren sowie eine geschützte `On`*EventName*\-Methode, die das Ereignis auslöst.  
  
 Das folgende Codefragment zeigt, wie das benutzerdefinierte `FlashTrackBar`\-Steuerelement ein benutzerdefiniertes Ereignis definiert, `ValueChanged`.  Den vollständigen Code für das `FlashTrackBar`\-Beispiel finden Sie unter [Gewusst wie: Erstellen eines Windows Forms\-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
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
   protected virtual void OnValueChanged(EventArgs e) {  
      if (ValueChanged != null) {  
         ValueChanged(this, e);  
      }  
   }  
}  
```  
  
## Siehe auch  
 [Ereignisse in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Ereignisse](../../../../docs/standard/events/index.md)   
 [Ereignisse](../../../../docs/standard/events/index.md)