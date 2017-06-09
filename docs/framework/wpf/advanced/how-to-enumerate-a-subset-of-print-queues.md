---
title: "Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen | Microsoft Docs"
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
  - "Auflisten, Untermenge von Druckwarteschlangen"
  - "Druckwarteschlangen, Auflisten von Untermengen von"
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen
IT\-Experten, die für die unternehmensweite Verwaltung von Druckern verantwortlich sind, müssen häufig eine Liste von Druckern erstellen, die bestimmte Eigenschaften aufweisen.  Diese Funktionalität wird von der <xref:System.Printing.PrintServer.GetPrintQueues%2A>\-Methode eines <xref:System.Printing.PrintServer>\-Objekts und der <xref:System.Printing.EnumeratedPrintQueueTypes>\-Enumeration bereitgestellt.  
  
## Beispiel  
 In den folgenden Beispielen wird durch den Code zunächst ein Array von Flags erstellt, die die Eigenschaften der aufzulistenden Druckwarteschlangen angeben.  In diesem Beispiel wird nach Druckwarteschlangen gesucht, die lokal auf dem Druckerserver installiert und freigegeben sind.  Die <xref:System.Printing.EnumeratedPrintQueueTypes>\-Enumeration stellt viele andere Möglichkeiten bereit.  
  
 Im Code wird dann ein <xref:System.Printing.LocalPrintServer>\-Objekt erstellt, eine von <xref:System.Printing.PrintServer> abgeleitete Klasse.  Der lokale Druckerserver ist der Computer, auf dem die Anwendung ausgeführt wird.  
  
 Der letzte wichtige Schritt besteht darin, das Array an die <xref:System.Printing.PrintServer.GetPrintQueues%2A>\-Methode zu übergeben.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Sie können dieses Beispiel erweitern, indem Sie die `foreach`\-Schleife verwenden, die jede Druckwarteschlange durchläuft und weitere Prüfungen ausführt.  Sie könnten z. B. Drucker aussortieren, die das doppelseitige Drucken nicht unterstützen, indem die Schleife jede <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>\-Methode der Druckwarteschlange aufruft und den zurückgegebenen Wert auf Duplexdruck prüft.  
  
## Siehe auch  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS\-Dokument\-Generator](http://go.microsoft.com/fwlink/?LinkId=147319)