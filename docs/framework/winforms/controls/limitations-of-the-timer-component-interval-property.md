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
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms
Die Windows Forms <xref:System.Windows.Forms.Timer> Komponente verfügt über eine <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft, die die Anzahl von Millisekunden angibt, die zwischen einem Zeit Geber Ereignis und dem nächsten übergeben werden. Wenn die Komponente nicht deaktiviert ist, empfängt ein Timer weiterhin das <xref:System.Windows.Forms.Timer.Tick> Ereignis in ungefähr identischen Zeitintervallen.  
  
 Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>Die Interval-Eigenschaft  
 Die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft muss beim Programmieren einer <xref:System.Windows.Forms.Timer> Komponente einige Einschränkungen beachten:  
  
- Wenn Ihre Anwendung oder eine andere Anwendung hohe Anforderungen an das System – wie z. b. lange Schleifen, intensive Berechnungen oder Laufwerk-, Netzwerk-oder Port Zugriffe –, erhält Ihre Anwendung möglicherweise keine Zeit Geber Ereignisse, so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft angibt.  
  
- Es ist nicht garantiert, dass das Intervall genau in der Zeit abläuft. Um die Genauigkeit zu gewährleisten, sollte der Timer die Systemuhr nach Bedarf überprüfen, anstatt zu versuchen, die kumulierte Zeit intern nachzuverfolgen.  
  
- Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft beträgt Millisekunden. Einige Computer bieten einen Leistungs befassleistungs-Leistungs Bewert, der eine höhere Auflösung als Millisekunden aufweist. Die Verfügbarkeit eines solchen Zählers hängt von der Prozessor Hardware des Computers ab.
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Timer>
- [Timer-Komponente](timer-component-windows-forms.md)
- [Übersicht über die Timer-Komponente](timer-component-overview-windows-forms.md)
