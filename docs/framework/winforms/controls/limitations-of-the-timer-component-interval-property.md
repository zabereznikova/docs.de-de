---
title: Einschränkungen der Eigenschaft "Intervall für Timer-Komponenten"
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745232"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="ef554-102">Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef554-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="ef554-103">Die Windows Forms <xref:System.Windows.Forms.Timer> Komponente verfügt über eine <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft, die die Anzahl von Millisekunden angibt, die zwischen einem Zeit Geber Ereignis und dem nächsten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef554-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="ef554-104">Wenn die Komponente nicht deaktiviert ist, empfängt ein Timer weiterhin das <xref:System.Windows.Forms.Timer.Tick> Ereignis in ungefähr identischen Zeitintervallen.</span><span class="sxs-lookup"><span data-stu-id="ef554-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="ef554-105">Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="ef554-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="ef554-106">Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ef554-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="ef554-107">Die Interval-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ef554-107">The Interval Property</span></span>  
 <span data-ttu-id="ef554-108">Die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft muss beim Programmieren einer <xref:System.Windows.Forms.Timer> Komponente einige Einschränkungen beachten:</span><span class="sxs-lookup"><span data-stu-id="ef554-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="ef554-109">Wenn Ihre Anwendung oder eine andere Anwendung hohe Anforderungen an das System – wie z. b. lange Schleifen, intensive Berechnungen oder Laufwerk-, Netzwerk-oder Port Zugriffe –, erhält Ihre Anwendung möglicherweise keine Zeit Geber Ereignisse, so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="ef554-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="ef554-110">Es ist nicht garantiert, dass das Intervall genau in der Zeit abläuft.</span><span class="sxs-lookup"><span data-stu-id="ef554-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="ef554-111">Um die Genauigkeit zu gewährleisten, sollte der Timer die Systemuhr nach Bedarf überprüfen, anstatt zu versuchen, die kumulierte Zeit intern nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="ef554-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="ef554-112">Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft beträgt Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="ef554-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="ef554-113">Einige Computer bieten einen Leistungs befassleistungs-Leistungs Bewert, der eine höhere Auflösung als Millisekunden aufweist.</span><span class="sxs-lookup"><span data-stu-id="ef554-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="ef554-114">Die Verfügbarkeit eines solchen Zählers hängt von der Prozessor Hardware des Computers ab.</span><span class="sxs-lookup"><span data-stu-id="ef554-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ef554-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef554-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="ef554-116">Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="ef554-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="ef554-117">Übersicht über die Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="ef554-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
