---
title: 'Vorgehensweise: Auflisten einer Teilmenge von Druckwarteschlangen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: 7cdd0ebeb03d078a952dd9ffe4d2ed7590417054
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359483"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Vorgehensweise: Auflisten einer Teilmenge von Druckwarteschlangen
Eine gängige Situation gegenüberstehen (IT) Experten, die Verwaltung einer unternehmensweiten Gruppe der Drucker ist zum Generieren einer Liste der Drucker mit bestimmten Eigenschaften. Diese Funktionalität wird bereitgestellt, indem die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode eine <xref:System.Printing.PrintServer> Objekt und die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration.  
  
## <a name="example"></a>Beispiel  
 Der Code zunächst im folgenden Beispiel erstellen ein Array von Flags, die die Merkmale der Druckerwarteschlangen angeben, die wir auflisten möchten. In diesem Beispiel suchen wir nach Druckwarteschlangen, die lokal installiert sind, auf dem Druckerserver und freigegeben werden. Die <xref:System.Printing.EnumeratedPrintQueueTypes> -Enumeration bietet viele weitere Möglichkeiten.  
  
 Anschließend erstellt der Code eine <xref:System.Printing.LocalPrintServer> Objekt eine abgeleitete Klasse <xref:System.Printing.PrintServer>. Der lokale Druckerserver ist der Computer, auf dem die Anwendung ausgeführt wird.  
  
 Der letzte wichtige Schritt ist das Array, das Übergeben der <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Sie könnten dieses Beispiel erweitern, indem Sie die `foreach` Schleife, die jeder Druckwarteschlange werden die Schritte weiter sicherheitsüberprüfungen unterzogen. Angenommen, Sie könnten blenden Sie Drucker, die nicht doppelseitiger Druck unterstützen, indem Sie den Aufruf der Schleife jeder Druckwarteschlange <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode und Testen Sie den zurückgegebenen Wert, auf das Vorhandensein von Duplexdruck.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokument-Generator](https://go.microsoft.com/fwlink/?LinkId=147319)
