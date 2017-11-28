---
title: 'Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen
Eine allgemeine Situation gegenüberstehen (IT) Spezialisten verwalten einen Satz unternehmensweiten der Drucker ist zum Generieren einer Liste von Druckern mit bestimmten Merkmalen. Diese Funktionalität wird bereitgestellt, indem Sie die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode von einer <xref:System.Printing.PrintServer> Objekt und die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zuerst im Code erstellen ein Array von Flags, die die Merkmale der Druckerwarteschlangen angeben, die wir auflisten möchten. In diesem Beispiel werden wir Druckwarteschlangen gesucht, die lokal installiert sind, auf dem Druckserver und freigegeben werden. Die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration bietet viele weitere Möglichkeiten.  
  
 Anschließend erstellt der Code eine <xref:System.Printing.LocalPrintServer> -Objekt, eine abgeleitete Klasse <xref:System.Printing.PrintServer>. Der lokale Druckerserver ist der Computer, auf dem die Anwendung ausgeführt wird.  
  
 Der letzte wichtige Schritt ist zum Übergeben des Arrays an die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Könnten Sie in diesem Beispiel erweitern, indem Sie die `foreach` -Schleife, die weiter über jede Druckerwarteschlange Schritte ausblenden. Angenommen, Sie konnte Bildschirm, Drucker, die nicht drucken zweiseitigen unterstützen, durch die Verwendung des Schleife Aufrufs jede Druckerwarteschlange <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode und Testen der zurückgegebene Wert auf das Vorhandensein des Duplexdruck.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
