---
title: Übersicht über die Timer-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 5bef0ba87d6a496acf7575965128be2b20b437ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074208"
---
# <a name="timer-component-overview-windows-forms"></a>Übersicht über die Timer-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.Timer>-Komponente von Windows Forms ist eine Komponente, die in regelmäßigen Abständen ein Ereignis auslöst. Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Wichtige Eigenschaften, Methoden und Ereignisse  
 Die Länge der Intervalle wird definiert, durch die <xref:System.Windows.Forms.Timer.Interval%2A> -Eigenschaft, dessen Wert in Millisekunden. Wenn die Komponente aktiviert ist, die <xref:System.Windows.Forms.Timer.Tick> Ereignis wird ausgelöst, jedem Intervall. Dies ist, in dem Sie die Ausführung von Code hinzufügen würden. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Prozeduren in festgelegten Abständen mit der Timer-Komponente in Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md). Die wichtigsten Methoden der der <xref:System.Windows.Forms.Timer> Komponente <xref:System.Windows.Forms.Timer.Start%2A> und <xref:System.Windows.Forms.Timer.Stop%2A>, die den Timer aktivieren, und deaktivieren. Wenn der Zeitgeber deaktiviert ist, wird er von zurückgesetzt. Es gibt keine Möglichkeit zum Anhalten einer <xref:System.Windows.Forms.Timer> Komponente.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Timer>
- [Timer-Komponente](timer-component-windows-forms.md)
- [Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms](limitations-of-the-timer-component-interval-property.md)
