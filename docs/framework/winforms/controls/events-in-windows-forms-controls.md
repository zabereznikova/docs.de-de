---
title: "Ereignisse in Windows Forms-Steuerelementen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a>Ereignisse in Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement erbt mehr als 60 Ereignisse aus <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Dazu gehören die <xref:System.Windows.Forms.Control.Paint> -Ereignis, das bewirkt, dass ein Steuerelement gezeichnet werden, Ereignisse, die im Zusammenhang mit der Anzeige eines Fensters, z. B. die <xref:System.Windows.Forms.Control.Resize> und <xref:System.Windows.Forms.Control.Layout> auch auf niedriger Ebene mit Maus und Tastatur Ereignisse. Einige Ereignisse auf niedriger Ebene werden durch synthetisiert <xref:System.Windows.Forms.Control> in semantische Ereignisse, z. B. <xref:System.Windows.Forms.Control.Click> und <xref:System.Windows.Forms.Control.DoubleClick>. Ausführliche Informationen über geerbte Ereignisse finden Sie unter <xref:System.Windows.Forms.Control>.  
  
 Wenn das benutzerdefinierte Steuerelement geerbte Ereignisfunktionen überschreiben muss, hängen Sie keinen Delegaten an, sondern überschreiben Sie die geerbte Methode `On`*EventName*. Wenn Sie mit dem Ereignismodell in .NET Framework nicht vertraut sind, finden Sie unter [Auslösen von Ereignissen aus einer Komponente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0) weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Überschreiben der OnPaint-Methode](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Behandeln von Benutzereingaben](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Definieren eines Ereignisses](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Ereignisse](../../../../docs/standard/events/index.md)
