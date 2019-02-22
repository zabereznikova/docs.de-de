---
title: Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: d280d14b116a356e1d9da94ef61d00ccae734b94
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664119"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="5eae0-102">Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5eae0-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="5eae0-103">Die Windows-Formulare <xref:System.Windows.Forms.Timer> Komponente weist eine <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft, die die Anzahl der Millisekunden angibt, die zwischen einem Timer-Ereignishandler und dem nächsten übergeben.</span><span class="sxs-lookup"><span data-stu-id="5eae0-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="5eae0-104">Wenn die Komponente deaktiviert wird, wird ein Zeitgeber erhalten die <xref:System.Windows.Forms.Timer.Tick> Ereignis zu ungefähr gleichen Intervallen Zeit.</span><span class="sxs-lookup"><span data-stu-id="5eae0-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="5eae0-105">Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="5eae0-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="5eae0-106">Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="5eae0-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="5eae0-107">Die Interval-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5eae0-107">The Interval Property</span></span>  
 <span data-ttu-id="5eae0-108">Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft weist einige Einschränkungen zu beachten, wenn Sie Programmieren eine <xref:System.Windows.Forms.Timer> Komponente:</span><span class="sxs-lookup"><span data-stu-id="5eae0-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="5eae0-109">Wenn Ihre Anwendung oder einer anderen Anwendung einer hohen auf dem System herstellt, wird – wie lange Schleifen, intensiven Berechnungen oder Laufwerk, Netzwerk oder Portzugriff – Ihre Anwendung kann nicht abgerufen werden Ereignisse für Timer so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gibt an.</span><span class="sxs-lookup"><span data-stu-id="5eae0-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="5eae0-110">Das Intervall ist nicht unbedingt genau an der Zeit verstreichen.</span><span class="sxs-lookup"><span data-stu-id="5eae0-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="5eae0-111">Um Genauigkeit zu gewährleisten, sollen der Timer die Systemuhr je nach Bedarf überprüfen, sondern versuchen, die bisher abgelaufene Zeit intern mitverfolgen.</span><span class="sxs-lookup"><span data-stu-id="5eae0-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="5eae0-112">Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft wird in Millisekunden angegeben.</span><span class="sxs-lookup"><span data-stu-id="5eae0-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="5eae0-113">Einige Computer Geben Sie einen hochauflösenden Indikator, der einer höher als Millisekunden Auflösung.</span><span class="sxs-lookup"><span data-stu-id="5eae0-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="5eae0-114">Die Verfügbarkeit solcher Zähler hängt von der Prozessorhardware des Computers ab.</span><span class="sxs-lookup"><span data-stu-id="5eae0-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5eae0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eae0-115">See also</span></span>
- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="5eae0-116">Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="5eae0-116">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [<span data-ttu-id="5eae0-117">Übersicht über die Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="5eae0-117">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
