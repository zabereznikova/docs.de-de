---
title: Einschränkungen der Timer-Komponente in Windows Forms&#39;s Interval-Eigenschaft
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9c42a0946cf29415f7bb12345da6784e0c276d5
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2018
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="72d8d-102">Einschränkungen der Timer-Komponente in Windows Forms&#39;s Interval-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="72d8d-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="72d8d-103">Windows Forms <xref:System.Windows.Forms.Timer> Komponente weist eine <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft, die die Anzahl von Millisekunden angibt, die zwischen einem timerereignisses zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="72d8d-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="72d8d-104">Wenn die Komponente nicht deaktiviert wird, weiterhin ein Zeitgeber empfängt die <xref:System.Windows.Forms.Timer.Tick> Ereignis in ungefähr gleich Zeitabständen.</span><span class="sxs-lookup"><span data-stu-id="72d8d-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="72d8d-105">Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt.</span><span class="sxs-lookup"><span data-stu-id="72d8d-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="72d8d-106">Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="72d8d-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="72d8d-107">Die Interval-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="72d8d-107">The Interval Property</span></span>  
 <span data-ttu-id="72d8d-108">Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gelten einige Einschränkungen berücksichtigt, wenn Sie Programmieren einer <xref:System.Windows.Forms.Timer> Komponente:</span><span class="sxs-lookup"><span data-stu-id="72d8d-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="72d8d-109">Wenn Ihre Anwendung oder einer anderen Anwendung hohe Anforderungen auf dem System stammt – wie lange Schleifen, rechenintensive Berechnungen oder Laufwerk, Netzwerk oder Portzugriff – Ihre Anwendung kann nicht abgerufen werden Ereignisse für Timer so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gibt.</span><span class="sxs-lookup"><span data-stu-id="72d8d-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="72d8d-110">Das Intervall wird nicht unbedingt genau an Zeit vergehen.</span><span class="sxs-lookup"><span data-stu-id="72d8d-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="72d8d-111">Um Genauigkeit sicherzustellen, sollte der Zeitgeber die Systemuhr Bedarf überprüfen, anstatt zum Nachverfolgen häufig auftretende Zeitfehler intern versuchen.</span><span class="sxs-lookup"><span data-stu-id="72d8d-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="72d8d-112">Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft wird in Millisekunden angegeben.</span><span class="sxs-lookup"><span data-stu-id="72d8d-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="72d8d-113">Einige Computer Geben Sie einen hochauflösenden Leistungsindikator, der einer höher als Millisekunden Auflösung.</span><span class="sxs-lookup"><span data-stu-id="72d8d-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="72d8d-114">Die Verfügbarkeit solcher eines Indikators hängt von der Prozessorhardware des Computers ab.</span><span class="sxs-lookup"><span data-stu-id="72d8d-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="72d8d-115">Weitere Informationen finden Sie in der Microsoft Knowledge Base-Artikel 172338, "Wie zum Verwenden QueryPerformanceCounter auf Zeitcode" http://support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="72d8d-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d8d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72d8d-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="72d8d-117">Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="72d8d-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="72d8d-118">Übersicht über die Timer-Komponente</span><span class="sxs-lookup"><span data-stu-id="72d8d-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
