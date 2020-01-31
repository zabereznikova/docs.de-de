---
title: Übersicht über die Timer-Komponente
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742779"
---
# <a name="timer-component-overview-windows-forms"></a>Übersicht über die Timer-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.Timer>-Komponente von Windows Forms ist eine Komponente, die in regelmäßigen Abständen ein Ereignis auslöst. Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Schlüsseleigenschaften, Methoden und Ereignisse  
 Die Länge der Intervalle wird durch die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft definiert, deren Wert in Millisekunden angegeben ist. Wenn die Komponente aktiviert ist, wird das <xref:System.Windows.Forms.Timer.Tick>-Ereignis jedes Intervall ausgelöst. An dieser Stelle würden Sie Code hinzufügen, der ausgeführt werden soll. Weitere Informationen finden Sie unter Gewusst [wie: Ausführen von Prozeduren in festgelegten Intervallen mit der Windows Forms Timer-Komponente](run-procedures-at-set-intervals-with-wf-timer-component.md). Die Schlüsselmethoden der <xref:System.Windows.Forms.Timer> Komponente sind <xref:System.Windows.Forms.Timer.Start%2A> und <xref:System.Windows.Forms.Timer.Stop%2A>, die den Timer aktivieren und deaktivieren. Wenn der Timer ausgeschaltet ist, wird zurückgesetzt. Es gibt keine Möglichkeit, eine <xref:System.Windows.Forms.Timer> Komponente anzuhalten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Timer>
- [Timer-Komponente](timer-component-windows-forms.md)
- [Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms](limitations-of-the-timer-component-interval-property.md)
