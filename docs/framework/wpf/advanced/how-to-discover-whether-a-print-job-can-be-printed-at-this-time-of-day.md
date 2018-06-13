---
title: 'Gewusst wie: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann'
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
ms.openlocfilehash: e5ea5ad3bcb10bfbc091f0b5852ee181a2c3fa8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548034"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Gewusst wie: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann
Druckwarteschlangen sind für 24 Stunden pro Tag nicht immer verfügbar. Sie haben die Start- und Uhrzeit-Eigenschaften, die festgelegt werden können, um sie zu bestimmten Zeiten des Tages nicht verfügbar zu machen. Diese Funktion kann verwendet werden, einen Drucker, für die ausschließliche Verwendung von einer bestimmten Abteilung nach 17: 00 Uhr reservieren. Diese Abteilung müsste eine andere Warteschlange Wartung des Druckers als andere Abteilungen verwenden. Die Warteschlange für die anderen Abteilungen nach 17: 00 Uhr nicht verfügbar ist, festgelegt, während die Warteschlange für die Vorgabe Abteilung festgelegt werden konnte, werden jederzeit zur Verfügung stehen.  
  
 Darüber hinaus können nur innerhalb einer angegebenen Zeitspanne druckbaren werden Druckaufträge selbst festgelegt werden.  
  
 Die <xref:System.Printing.PrintQueue> und <xref:System.Printing.PrintSystemJobInfo> Klassen verfügbar gemacht, der [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von Microsoft .NET Framework bieten Sie eine Möglichkeit zum Remote überprüfen, ob ein bestimmter Druckauftrag zum jetzigen Zeitpunkt auf einer bestimmten Warteschlange drucken kann.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Beispiel, das bei einem Druckauftrag Problemdiagnose kann.  
  
 Es gibt zwei Hauptschritte für diese Art von Funktion wie folgt.  
  
1.  Lesen der <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften der <xref:System.Printing.PrintQueue> zu bestimmen, ob die aktuelle Zeit zwischen ihnen.  
  
2.  Lesen der <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> und <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> Eigenschaften der <xref:System.Printing.PrintSystemJobInfo> zu bestimmen, ob die aktuelle Zeit zwischen ihnen.  
  
 Jedoch Komplikationen auftreten "naiv", die diese Eigenschaften nicht <xref:System.DateTime> Objekte. Stattdessen werden <xref:System.Int32> Objekte, die die Tageszeit als die Anzahl von Minuten seit Mitternacht Ausdrücken. Darüber hinaus ist dies nicht Mitternacht in der aktuellen Zeitzone jedoch Mitternacht laut koordinierter Weltzeit (Coordinated Universal Time).  
  
 Im erste Codebeispiel zeigt die statische Methode **ReportQueueAndJobAvailability**, der übergeben wird eine <xref:System.Printing.PrintSystemJobInfo> und ruft Helfermethoden bereit, um festzustellen, ob der Auftrag zum jetzigen Zeitpunkt gedruckt werden kann und, sofern nicht der Fall, wenn es ausdrucken zu können. Beachten Sie, dass ein <xref:System.Printing.PrintQueue> nicht an die Methode übergeben wird. Grund hierfür ist die <xref:System.Printing.PrintSystemJobInfo> enthält einen Verweis auf die Warteschlange in seiner <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> Eigenschaft.  
  
 Die untergeordneten Methoden enthalten die überladene **ReportAvailabilityAtThisTime** Methode, die entweder übernehmen kann eine <xref:System.Printing.PrintQueue> oder eine <xref:System.Printing.PrintSystemJobInfo> als Parameter. Es gibt auch eine **TimeConverter.ConvertToLocalHumanReadableTime**. Alle diese Methoden werden nachfolgend beschrieben.  
  
 Die **ReportQueueAndJobAvailability** Methode wird zuerst überprüft, um festzustellen, ob die Warteschlange oder den Druckauftrag zu diesem Zeitpunkt nicht verfügbar ist. Wenn einem der Computer nicht verfügbar ist, überprüft Sie, wenn finden Sie unter der Warteschlange nicht verfügbar. Wenn sie nicht verfügbar ist, meldet die Methode diese Tatsache und die Uhrzeit, wann die Warteschlange wieder verfügbar wird. Klicken Sie dann den Auftrag überprüft und nicht verfügbar ist, gibt das nächste Mal umfassen, wenn es gedruckt werden kann. Schließlich gibt die Methode die früheste Uhrzeit, wann der Auftrag gedruckt werden kann. Dies ist der höhere der folgenden zwei Mal.  
  
-   Der Zeitpunkt, wenn die Druckerwarteschlange weiter verfügbar ist.  
  
-   Der Zeitpunkt, wenn der Druckauftrag weiter verfügbar ist.  
  
 Entsteht Tageszeiten, die <xref:System.DateTime.ToShortTimeString%2A> Methode wird auch aufgerufen werden, da diese Methode die Jahre, Monate und Tage in der Ausgabe unterdrückt. Sie können die Verfügbarkeit einer Druckwarteschlange oder eines Druckauftrags nicht auf bestimmte Jahre, Monate oder Tage einschränken.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Die beiden Überladungen der der **ReportAvailabilityAtThisTime** Methode sind beinahe identisch, mit Ausnahme des Datentyps, sodass nur an Sie übergeben die <xref:System.Printing.PrintQueue> Version ist unten dargestellt.  
  
> [!NOTE]
>  Die Tatsache, dass die Methoden abgesehen Typ sind, löst die Frage, warum das Beispiel keine generische Methode erstellt wird **ReportAvailabilityAtThisTime\<T >**. Der Grund hierfür ist, dass eine solche Methode auf eine Klasse eingeschränkt sein, die hätte die **StartTimeOfDay** und **UntilTimeOfDay enthält** Eigenschaften, die die Methode aufruft, jedoch eine generische Methode kann nur beschränkt werden ein einzelne Klasse und die einzige Klasse, die sowohl <xref:System.Printing.PrintQueue> und <xref:System.Printing.PrintSystemJobInfo> Struktur die Vererbung wird <xref:System.Printing.PrintSystemObject> die verfügt über keine solche Eigenschaften.  
  
 Die **ReportAvailabilityAtThisTime** (im folgenden Codebeispiel dargestellt) Methode beginnt mit der Initialisierung einer <xref:System.Boolean> Sentinelvariable `true`. Wird auf zurückgesetzt werden `false`, wenn die Warteschlange nicht verfügbar ist.  
  
 Als Nächstes die Methode überprüft, ob der Start und "bis" Zeiten identisch sind. Bei die Warteschlange ist immer verfügbar, damit der Methodenrückgabe `true`.  
  
 Wenn die Warteschlange nicht verfügbar ständig ist, wird die Methode verwendet die statische <xref:System.DateTime.UtcNow%2A> Eigenschaft, um die aktuelle Uhrzeit als ein <xref:System.DateTime> Objekt. (Es ist nicht Ortszeit erforderlich, da die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> Eigenschaften werden in UTC-Zeit.)  
  
 Diese beiden Eigenschaften sind jedoch nicht <xref:System.DateTime> Objekte. Sie sind <xref:System.Int32>s, der die Zeit als die Anzahl der Minuten nach UTC Mitternacht ausdrückt. Damit wir konvertiert haben unsere <xref:System.DateTime> Objekt Minuten nach Mitternacht. Wenn Sie fertig sind, überprüft die Methode einfach an, um festzustellen, ob "jetzt" ist zwischen dem Anfang der Warteschlange und "bis" Uhrzeiten, legt der Sentinelwert auf "false", wenn "jetzt" befindet sich nicht zwischen den zwei Mal, und gibt den Sentinelwert zurück.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Die **TimeConverter.ConvertToLocalHumanReadableTime** -Methode (im folgenden Codebeispiel dargestellt) verwendet keine Methoden mit Microsoft .NET Framework eingeführt wurde, daher wird keine. Die Methode wurde eine doppelte Konvertierungsaufgabe: Es muss eine ganze Zahl, die Minuten nach Mitternacht ausdrückt und konvertieren Sie ihn in eine lesbare Zeit und es muss in die lokale Zeit konvertieren. Erreicht wird dies durch Erstellen einer <xref:System.DateTime> -Objekt, das festgelegt wird, um Mitternacht UTC und anschließend verwendet der <xref:System.DateTime.AddMinutes%2A> Methode, um die Minuten hinzuzufügen, die an die Methode übergeben wurden. Dies gibt eine neue <xref:System.DateTime> auszudrücken, die ursprüngliche Uhrzeit, die an die Methode übergeben wurde. Die <xref:System.DateTime.ToLocalTime%2A> -Methode konvertiert diese dann in die Ortszeit.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
