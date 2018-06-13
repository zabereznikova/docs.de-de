---
title: Einschränkungen der Timer-Komponente in Windows Forms&#39;s Interval-Eigenschaft
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 4808d115ff842c6c0e6b036da9fe20bb1b48f8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536025"
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Einschränkungen der Timer-Komponente in Windows Forms&#39;s Interval-Eigenschaft
Windows Forms <xref:System.Windows.Forms.Timer> Komponente weist eine <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft, die die Anzahl von Millisekunden angibt, die zwischen einem timerereignisses zu übergeben. Wenn die Komponente nicht deaktiviert wird, weiterhin ein Zeitgeber empfängt die <xref:System.Windows.Forms.Timer.Tick> Ereignis in ungefähr gleich Zeitabständen.  
  
 Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Die Interval-Eigenschaft  
 Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gelten einige Einschränkungen berücksichtigt, wenn Sie Programmieren einer <xref:System.Windows.Forms.Timer> Komponente:  
  
-   Wenn Ihre Anwendung oder einer anderen Anwendung hohe Anforderungen auf dem System stammt – wie lange Schleifen, rechenintensive Berechnungen oder Laufwerk, Netzwerk oder Portzugriff – Ihre Anwendung kann nicht abgerufen werden Ereignisse für Timer so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gibt.  
  
-   Das Intervall wird nicht unbedingt genau an Zeit vergehen. Um Genauigkeit sicherzustellen, sollte der Zeitgeber die Systemuhr Bedarf überprüfen, anstatt zum Nachverfolgen häufig auftretende Zeitfehler intern versuchen.  
  
-   Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft wird in Millisekunden angegeben. Einige Computer Geben Sie einen hochauflösenden Leistungsindikator, der einer höher als Millisekunden Auflösung. Die Verfügbarkeit solcher eines Indikators hängt von der Prozessorhardware des Computers ab. Weitere Informationen finden Sie in der Microsoft Knowledge Base-Artikel 172338, "Wie zum Verwenden QueryPerformanceCounter auf Zeitcode" http://support.microsoft.com.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Timer>  
 [Timer-Komponente](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Übersicht über die Timer-Komponente](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
