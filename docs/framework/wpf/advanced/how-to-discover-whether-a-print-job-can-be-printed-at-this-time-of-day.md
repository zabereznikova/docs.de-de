---
title: 'Vorgehensweise: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: 7eed5400744f1010cbf52dc8d3b3d0bc24aa4371
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326865"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Vorgehensweise: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann
Druckwarteschlangen sind für 24 Stunden pro Tag nicht immer verfügbar. Sie haben die Start- und einer Uhrzeit-Eigenschaften, die festgelegt werden können, um sie zu bestimmten Zeiten des Tages nicht verfügbar zu machen. Dieses Feature kann z. B. verwendet werden, um einen Drucker, für die exklusive Verwendung von einer bestimmten Abteilung nach 17: 00 Uhr zu reservieren. Diese Abteilung müsste eine andere Warteschlange Wartung des Druckers als andere Abteilungen verwenden. Die Warteschlange für die anderen Abteilungen würden nach 17 Uhr nicht verfügbar ist, festgelegt werden, während die Warteschlange für die bevorzugte-Abteilung festgelegt werden konnte, werden jederzeit zur Verfügung stehen.  
  
 Darüber hinaus können der Druckaufträge selbst festgelegt werden, nur innerhalb einer angegebenen Zeitspanne druckbaren sein.  
  
 Die <xref:System.Printing.PrintQueue> und <xref:System.Printing.PrintSystemJobInfo> Klassen verfügbar gemacht, der [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von Microsoft .NET Framework kann Remote geprüft, ob ein bestimmter Druckauftrag zum aktuellen Zeitpunkt auf eine bestimmte Warteschlange drucken kann.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Beispiel, das bei einem Druckauftrag Problemdiagnose kann.  
  
 Es gibt zwei wichtige Schritte für diese Art von Funktion wie folgt.  
  
1. Lesen der <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften der <xref:System.Printing.PrintQueue> zu bestimmen, ob die aktuelle Zeit zwischen ihnen liegt.  
  
2. Lesen der <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> und <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> Eigenschaften der <xref:System.Printing.PrintSystemJobInfo> zu bestimmen, ob die aktuelle Zeit zwischen ihnen liegt.  
  
 Jedoch Komplikationen auftreten, von der Tatsache ab, die diese Eigenschaften nicht <xref:System.DateTime> Objekte. Sondern <xref:System.Int32> -Objekten, die Uhrzeit als die Anzahl von Minuten seit Mitternacht Ausdrücken. Darüber hinaus ist dies nicht Mitternacht in der aktuellen Zeitzone, aber Mitternacht UTC (Coordinated Universal Time).  
  
 Im erste Codebeispiel stellt die statische Methode **ReportQueueAndJobAvailability**, die übergeben wird eine <xref:System.Printing.PrintSystemJobInfo> und ruft die Hilfsmethoden zum bestimmen, ob der Druckauftrag zum aktuellen Zeitpunkt und, sofern nicht der Fall, wenn es ausdrucken zu können. Beachten Sie, dass eine <xref:System.Printing.PrintQueue> nicht an die Methode übergeben wird. Grund hierfür ist die <xref:System.Printing.PrintSystemJobInfo> enthält einen Verweis auf die Warteschlange in die <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> Eigenschaft.  
  
 Die untergeordneten Methoden enthalten, die überladene **ReportAvailabilityAtThisTime** Methode, die entweder übernehmen kann eine <xref:System.Printing.PrintQueue> oder <xref:System.Printing.PrintSystemJobInfo> als Parameter. Es gibt auch eine **TimeConverter.ConvertToLocalHumanReadableTime**. Alle diese Methoden werden nachfolgend beschrieben.  
  
 Die **ReportQueueAndJobAvailability** Methode beginnt mit der überprüft wird, wenn entweder die Warteschlange oder der Druckauftrag zurzeit nicht verfügbar ist. Wenn eine der Eigenschaften nicht verfügbar ist, überprüft Sie, wenn finden Sie unter der Warteschlange nicht verfügbar. Wenn sie nicht verfügbar ist, meldet die Methode diese Fakten- und die Uhrzeit, wann die Warteschlange wieder verfügbar wird. Er überprüft dann den Auftrag und wenn es nicht mehr verfügbar ist, meldet das nächste Mal umfassen, wenn es gedruckt werden kann. Schließlich meldet die Methode die früheste Uhrzeit, wann der Auftrag gedruckt werden kann. Dies ist das spätere der folgenden zwei Mal.  
  
-   Der nächste Zeitpunkt, die Warteschlange verfügbar ist.  
  
-   Der Zeitpunkt, wenn der Druckauftrag neben verfügbar ist.  
  
 Beim Melden von der Tageszeit, die <xref:System.DateTime.ToShortTimeString%2A> Methode wird auch aufgerufen werden, da diese Methode der Jahre, Monate und Tage in der Ausgabe unterdrückt. Sie können nicht die Verfügbarkeit eines Druckauftrags oder eine Druckwarteschlange auf bestimmte Jahre, Monate oder Tage einschränken.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Die beiden Überladungen, der die **ReportAvailabilityAtThisTime** Methode sind identisch, mit Ausnahme des Datentyps übergebenen, sodass nur die <xref:System.Printing.PrintQueue> Version wird unten angezeigt.  
  
> [!NOTE]
>  Die Tatsache, dass die Methoden, mit Ausnahme des Typs identisch sind, wirft die Frage, warum das Beispiel eine generische Methode keine erstellt **ReportAvailabilityAtThisTime\<T >**. Der Grund dafür besteht darin, dass eine solche Methode würde zu einer Klasse eingeschränkt werden, die die **StartTimeOfDay** und **UntilTimeOfDay enthält** Eigenschaften, die die Methode aufruft, jedoch eine generische Methode kann nur beschränkt werden ein Single-Klasse und die einzige Klasse, die sowohl <xref:System.Printing.PrintQueue> und <xref:System.Printing.PrintSystemJobInfo> in die Vererbung ist Baum <xref:System.Printing.PrintSystemObject> der über keine solche Eigenschaften verfügt.  
  
 Die **ReportAvailabilityAtThisTime** -Methode (im folgenden Codebeispiel dargestellt) beginnt, durch die Initialisierung einer <xref:System.Boolean> Sentinelvariable, die `true`. Wird zum zurückgesetzt `false`, wenn die Warteschlange nicht verfügbar ist.  
  
 Als Nächstes die Methode überprüft, ob der Start und "until" identisch sind. Wenn dies der Fall, die Warteschlange ist immer verfügbar, deshalb gibt die Methode zurück `true`.  
  
 Wenn die Warteschlange nicht ständig vorliegen, wird die Methode verwendet die statische <xref:System.DateTime.UtcNow%2A> -Eigenschaft zum Abrufen der aktuellen Zeit eine <xref:System.DateTime> Objekt. (Wir müssen lokale Zeit nicht mehr, da die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften werden in UTC-Zeit.)  
  
 Diese beiden Eigenschaften sind jedoch nicht <xref:System.DateTime> Objekte. Sie sind <xref:System.Int32>s, der die Zeit als die Anzahl der Minuten nach der UTC-Mitternacht ausdrückt. Damit wir konvertiert haben unsere <xref:System.DateTime> Objekt Minuten nach Mitternacht. Wenn Sie fertig sind, überprüft die Methode einfach an, um herauszufinden, ob "jetzt" ist zwischen der Warteschlange starten und "bis"-Zeit, legt der Sentinelwert auf "false", wenn "jetzt" liegt nicht zwischen den beiden Zeiten, und gibt den Sentinelwert zurück.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Die **TimeConverter.ConvertToLocalHumanReadableTime** (im folgenden Codebeispiel dargestellt) Methode verwendet keine Methoden, die mit Microsoft .NET Framework eingeführt wurde, daher wird. Die Methode verfügt über eine doppelte Konvertierungsaufgabe: sie müssen eine ganze Zahl, die Minuten nach Mitternacht Ausdrücken und konvertieren Sie ihn in einen Menschen lesbarer Zeit und sie müssen dies in die lokale Zeit konvertieren. Er erreicht dies, indem zuerst ein <xref:System.DateTime> -Objekt, das auf Mitternacht UTC-Zeit aus, und klicken Sie dann es verwendet die <xref:System.DateTime.AddMinutes%2A> Methode, um die Minuten hinzuzufügen, die an die Methode übergeben wurden. Dies gibt eine neue <xref:System.DateTime> Ausdrücken der ursprünglichen Zeit, die an die Methode übergeben wurde. Die <xref:System.DateTime.ToLocalTime%2A> -Methode konvertiert diese dann in die lokale Zeit.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
