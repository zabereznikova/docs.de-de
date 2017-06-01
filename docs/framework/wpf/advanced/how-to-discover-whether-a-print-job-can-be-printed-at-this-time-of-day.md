---
title: "Gewusst wie: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Druckaufträge, Planen"
  - "Druckwarteschlangen, Planen"
  - "Drucker, Verfügbarkeit"
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Ermitteln, ob ein Druckauftrag zu dieser Tageszeit gedruckt werden kann
Druckwarteschlangen sind nicht immer für 24 Stunden pro Tag verfügbar.  Sie verfügen über Eigenschaften zur Start\- und Endzeit, anhand derer bestimmte Tageszeiten festgelegt werden können, zu denen die Druckwarteschlangen nicht verfügbar sind.  Anhand dieses Features können Sie z. B. einen Drucker zur exklusiven Verwendung durch eine Abteilung nach 17:00 Uhr reservieren.  Diese Abteilung würde zum Drucken eine andere Druckwarteschlange als andere Abteilungen verwenden.  Die Warteschlange der anderen Abteilungen wird in diesem Fall so eingerichtet, dass sie nach 17:00 nicht mehr verfügbar ist, wohingegen die Warteschlangeneinrichtung der bevorzugten Abteilung eine ständige Verfügbarkeit vorsieht.  
  
 Darüber hinaus können auch die Druckaufträge selbst so eingerichtet werden, dass sie nur während einer angegebenen Zeitspanne gedruckt werden können.  
  
 Mithilfe der in den [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] von [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] enthaltenen Klassen <xref:System.Printing.PrintQueue> und <xref:System.Printing.PrintSystemJobInfo> kann remote geprüft werden, ob ein bestimmter Druckauftrag in einer gegebenen Warteschlange zum aktuellen Zeitpunkt gedruckt werden kann.  
  
## Beispiel  
 Das folgende Beispiel kann Probleme bei Druckaufträgen diagnostizieren.  
  
 Die zwei wichtigsten Schritte für diese Art von Funktion sind:  
  
1.  Bestimmen Sie anhand der Eigenschaften <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> und <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> der <xref:System.Printing.PrintQueue>, ob die aktuelle Zeit in diesen Zeitraum fällt.  
  
2.  Bestimmen Sie anhand der Eigenschaften <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> und <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> der <xref:System.Printing.PrintSystemJobInfo>, ob die aktuelle Zeit in diesen Zeitraum fällt.  
  
 Es können sich jedoch Komplikationen aufgrund der Tatsache ergeben, dass diese Eigenschaften keine <xref:System.DateTime>\-Objekte sind.  Stattdessen handelt es sich um <xref:System.Int32>\-Objekte, die die Tageszeit in Minuten seit Mitternacht angeben.  Darüber hinaus ist dies nicht die mitternächtliche Zeit der aktuellen Zeitzone, sondern Mitternacht nach UTC\-Zeit \(koordinierte Weltzeit\).  
  
 Das erste Codebeispiel veranschaulicht die statische Methode **ReportQueueAndJobAvailability**, der eine <xref:System.Printing.PrintSystemJobInfo> übergeben wird und die Hilfsmethoden aufruft, um zu bestimmen, ob der Auftrag zur aktuellen Zeit gedruckt werden kann und, wenn nicht, zu welchem Zeitpunkt er gedruckt werden kann.  Beachten Sie, dass keine <xref:System.Printing.PrintQueue> an die Methode übergeben wird.  Das liegt daran, dass <xref:System.Printing.PrintSystemJobInfo> einen Verweis auf die Warteschlange in seiner <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A>\-Eigenschaft enthält.  
  
 Die untergeordneten Methoden enthalten die überladene **ReportAvailabilityAtThisTime**\-Methode, die entweder <xref:System.Printing.PrintQueue> oder <xref:System.Printing.PrintSystemJobInfo> als Parameter übernehmen kann.  Außerdem ist eine **TimeConverter.ConvertToLocalHumanReadableTime** vorhanden.  Alle diese Methoden werden nachfolgend erläutert.  
  
 Die **ReportQueueAndJobAvailability**\-Methode prüft zunächst, ob zu diesem Zeitpunkt entweder die Warteschlange oder der Druckauftrag nicht zur Verfügung steht.  Wenn einer von ihnen nicht verfügbar ist, überprüft sie, ob die Warteschlange nicht verfügbar ist.  Wenn dem so ist, meldet die Methode diese Tatsache sowie den Zeitpunkt, ab dem die Warteschlange wieder zur Verfügung steht.  Danach prüft sie den Druckauftrag und meldet, sofern dieser nicht zur Verfügung steht, die nächste Zeitspanne, zu der der Auftrag gedruckt werden kann.  Schließlich meldet die Methode den frühesten Zeitpunkt, zu dem der Auftrag gedruckt werden kann.  Dabei handelt es sich um den späteren Zeitpunkt der folgenden zwei Zeitangaben.  
  
-   Der nächste Zeitpunkt, zu dem die Druckwarteschlange verfügbar ist.  
  
-   Der nächste Zeitpunkt, zu dem der Druckauftrag verfügbar ist.  
  
 Beim Melden der Tageszeiten wird außerdem die <xref:System.DateTime.ToShortTimeString%2A>\-Methode aufgerufen, da diese Methode die Angaben zu Jahr, Monat und Tag in der Ausgabe unterdrückt.  Sie können die Verfügbarkeit einer Druckwarteschlange oder eines Druckauftrags nicht auf bestimmte Jahre, Monate oder Tage einschränken.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Die beiden Überladungen der **ReportAvailabilityAtThisTime**\-Methode sind mit Ausnahme des an sie übergebenen Typs identisch, sodass in der Folge nur die <xref:System.Printing.PrintQueue>\-Version dargestellt wird.  
  
> [!NOTE]
>  Die Tatsache, dass die Methoden mit Ausnahme des Typs identisch sind, wirft die Frage auf, warum das Beispiel keine generische **ReportAvailabilityAtThisTime\<T\>**\-Methode erstellt.  Der Grund dafür ist, dass eine solche Methode auf eine Klasse beschränkt werden müsste, die die von der Methode aufgerufenen Eigenschaften **StartTimeOfDay** und **UntilTimeOfDay** enthält. Eine generische Methode kann jedoch nur auf eine einzelne Klasse beschränkt werden, und die einzige Klasse, die in der Vererbungsstruktur sowohl der <xref:System.Printing.PrintQueue> als auch der <xref:System.Printing.PrintSystemJobInfo> gemeinsam ist, ist die <xref:System.Printing.PrintSystemObject>\-Klasse, die keine dieser Eigenschaften enthält.  
  
 Die **ReportAvailabilityAtThisTime**\-Methode \(im folgenden Codebeispiel dargestellt\) initialisiert zunächst eine <xref:System.Boolean>\-Sentinelvariable auf `true`.  Sie wird auf `false` zurückgesetzt, wenn die Warteschlange nicht verfügbar ist.  
  
 Danach überprüft die Methode, ob Start\- und Endzeitpunkt identisch sind.  Wenn diese identisch sind, ist die Warteschlange immer verfügbar, und die Methode gibt `true` zurück.  
  
 Steht die Warteschlange nicht jederzeit zur Verfügung, verwendet die Methode die statische <xref:System.DateTime.UtcNow%2A>\-Eigenschaft, um die aktuelle Zeit als <xref:System.DateTime>\-Objekt abzurufen.  \(Die Ortszeit wird nicht benötigt, da die <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>\-Eigenschaft und die <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>\-Eigenschaft selbst in UTC\-Zeit geführt werden.\)  
  
 Diese beiden Eigenschaften sind jedoch keine <xref:System.DateTime>\-Objekte.  Sie sind <xref:System.Int32>\-Objekte, die die Zeit in Minuten nach Mitternacht UTC ausdrücken.  Deshalb muss das <xref:System.DateTime>\-Objekt in Minuten nach Mitternacht konvertiert werden.  Danach prüft die Methode lediglich, ob der aktuelle Zeitpunkt zwischen dem Startzeitpunkt und dem Endzeitpunkt der Warteschlange liegt, setzt den Sentinelwert auf "False", wenn der aktuelle Zeitpunkt nicht zwischen den beiden Zeitangaben liegt, und gibt den Sentinelwert zurück.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Die **TimeConverter.ConvertToLocalHumanReadableTime**\-Methode \(im folgenden Codebeispiel dargestellt\) verwendet keine der mit [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] eingeführten Methoden, sodass sie hier lediglich in aller Kürze erläutert wird.  Die Methode hat eine doppelte Konvertierungsaufgabe: Sie muss eine ganze Zahl, die die Minuten nach Mitternacht ausdrückt, in eine für den Benutzer lesbare Zeit und in eine Ortszeit konvertieren.  Sie erreicht dies, indem sie zuerst ein auf Mitternacht UTC eingestelltes <xref:System.DateTime>\-Objekt erstellt und danach die <xref:System.DateTime.AddMinutes%2A>\-Methode verwendet, um die an die Methode übergebenen Minuten hinzuzufügen.  Dies gibt einen neuen <xref:System.DateTime>\-Wert zurück, der die ursprüngliche Zeit ausdrückt, die an die Methode übergeben wurde.  Die <xref:System.DateTime.ToLocalTime%2A>\-Methode konvertiert diesen Wert dann in die Ortszeit.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## Siehe auch  
 <xref:System.DateTime>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.Printing.PrintQueue>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)