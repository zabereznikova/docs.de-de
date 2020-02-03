---
title: Ereignisse in Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745756"
---
# <a name="events-in-windows-forms-controls"></a>Ereignisse in Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement erbt mehr als 60 Ereignisse von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Dazu gehört das <xref:System.Windows.Forms.Control.Paint>-Ereignis, das bewirkt, dass ein Steuerelement gezeichnet wird, Ereignisse im Zusammenhang mit der Anzeige eines Fensters, wie z. b. die Ereignisse <xref:System.Windows.Forms.Control.Resize> und <xref:System.Windows.Forms.Control.Layout> sowie Maus-und Tastatur Ereignisse auf niedriger Ebene. Einige Ereignisse auf niedriger Ebene werden durch <xref:System.Windows.Forms.Control> in Semantik Ereignisse wie <xref:System.Windows.Forms.Control.Click> und <xref:System.Windows.Forms.Control.DoubleClick>synthetisiert. Ausführliche Informationen zu geerbten Ereignissen finden Sie unter <xref:System.Windows.Forms.Control>.  
  
 Wenn das benutzerdefinierte Steuerelement geerbte Ereignisfunktionen überschreiben muss, hängen Sie keinen Delegaten an, sondern überschreiben Sie die geerbte Methode `On`*EventName*. Wenn Sie mit dem Ereignismodell in .NET Framework nicht vertraut sind, finden Sie unter [Auslösen von Ereignissen aus einer Komponente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)) weitere Informationen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Überschreiben der OnPaint-Methode](overriding-the-onpaint-method.md)
- [Behandeln von Benutzereingaben](handling-user-input.md)
- [Definieren eines Ereignisses](defining-an-event-in-windows-forms-controls.md)
- [Ereignisse](../../../standard/events/index.md)
