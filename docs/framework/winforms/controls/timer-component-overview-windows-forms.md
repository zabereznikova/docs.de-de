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
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="b2bac-102">Übersicht über die Timer-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b2bac-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b2bac-103">Die <xref:System.Windows.Forms.Timer>-Komponente von Windows Forms ist eine Komponente, die in regelmäßigen Abständen ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="b2bac-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="b2bac-104">Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="b2bac-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="b2bac-105">Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="b2bac-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="b2bac-106">Wichtige Eigenschaften, Methoden und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b2bac-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="b2bac-107">Die Länge der Intervalle wird definiert, durch die <xref:System.Windows.Forms.Timer.Interval%2A> -Eigenschaft, dessen Wert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="b2bac-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="b2bac-108">Wenn die Komponente aktiviert ist, die <xref:System.Windows.Forms.Timer.Tick> Ereignis wird ausgelöst, jedem Intervall.</span><span class="sxs-lookup"><span data-stu-id="b2bac-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="b2bac-109">Dies ist, in dem Sie die Ausführung von Code hinzufügen würden.</span><span class="sxs-lookup"><span data-stu-id="b2bac-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="b2bac-110">Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Prozeduren in festgelegten Abständen mit der Timer-Komponente in Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="b2bac-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="b2bac-111">Die wichtigsten Methoden der der <xref:System.Windows.Forms.Timer> Komponente <xref:System.Windows.Forms.Timer.Start%2A> und <xref:System.Windows.Forms.Timer.Stop%2A>, die den Timer aktivieren, und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2bac-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="b2bac-112">Wenn der Zeitgeber deaktiviert ist, wird er von zurückgesetzt. Es gibt keine Möglichkeit zum Anhalten einer <xref:System.Windows.Forms.Timer> Komponente.</span><span class="sxs-lookup"><span data-stu-id="b2bac-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bac-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2bac-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="b2bac-114">Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="b2bac-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="b2bac-115">Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2bac-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
