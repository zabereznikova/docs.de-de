---
title: Ereignisse in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 253783f50fdbef0890ea16baa9ac996b63795ed8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716962"
---
# <a name="events-in-windows-forms-controls"></a>Ereignisse in Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement erbt mehr als sechzig Ereignisse von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Dazu gehören die <xref:System.Windows.Forms.Control.Paint> -Ereignis, das bewirkt, dass ein Steuerelement gezeichnet werden soll, die Ereignisse im Zusammenhang mit der Anzeige eines Fenster, z. B. die <xref:System.Windows.Forms.Control.Resize> und <xref:System.Windows.Forms.Control.Layout> Ereignisse und Ereignisse, die mit Maus und Tastatur auf niedriger Ebene. Einige Ereignisse auf niedriger Ebene werden von synthetisiert <xref:System.Windows.Forms.Control> in semantische Ereignisse, z. B. <xref:System.Windows.Forms.Control.Click> und <xref:System.Windows.Forms.Control.DoubleClick>. Weitere Informationen zu geerbten Ereignissen finden Sie unter <xref:System.Windows.Forms.Control>.  
  
 Wenn das benutzerdefinierte Steuerelement geerbte Ereignisfunktionen überschreiben muss, hängen Sie keinen Delegaten an, sondern überschreiben Sie die geerbte Methode `On`*EventName*. Wenn Sie mit dem Ereignismodell in .NET Framework nicht vertraut sind, finden Sie unter [Auslösen von Ereignissen aus einer Komponente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0) weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch
- [Überschreiben der OnPaint-Methode](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)
- [Behandeln von Benutzereingaben](../../../../docs/framework/winforms/controls/handling-user-input.md)
- [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
- [Ereignisse](../../../../docs/standard/events/index.md)
