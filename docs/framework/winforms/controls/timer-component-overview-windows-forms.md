---
title: "Übersicht über die Timer-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea78cadae6e033bc54274e5428ba5e8c6410259d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="timer-component-overview-windows-forms"></a>Übersicht über die Timer-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.Timer>-Komponente von Windows Forms ist eine Komponente, die in regelmäßigen Abständen ein Ereignis auslöst. Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Wichtige Eigenschaften, Methoden und Ereignisse  
 Die Länge der Intervalle wird definiert, indem die <xref:System.Windows.Forms.Timer.Interval%2A> -Eigenschaft, deren Wert in Millisekunden. Wenn die Komponente aktiviert ist, die <xref:System.Windows.Forms.Timer.Tick> Ereignis wird jedes Intervall. Dies ist in dem Sie die auszuführende codeanweisung hinzufügen würden. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Prozeduren in Intervallen festlegen, mit der Timer-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). Folgende Schlüsselmethoden der <xref:System.Windows.Forms.Timer> Komponente <xref:System.Windows.Forms.Timer.Start%2A> und <xref:System.Windows.Forms.Timer.Stop%2A>, die den Zeitgeber auf Aktivieren bzw. deaktivieren. Wenn der Timer deaktiviert ist, wird er zurückgesetzt. Es gibt keine Möglichkeit zum Anhalten einer <xref:System.Windows.Forms.Timer> Komponente.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Timer>  
 [Timer-Komponente](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
