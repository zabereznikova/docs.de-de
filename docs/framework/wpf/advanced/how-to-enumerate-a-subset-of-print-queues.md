---
title: 'Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094539"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen
Eine häufige Situation von IT-Spezialisten, die eine unternehmensweite Gruppe von Druckern verwalten, besteht darin, eine Liste von Druckern zu generieren, die bestimmte Merkmale aufweisen. Diese Funktionalität wird durch die <xref:System.Printing.PrintServer.GetPrintQueues%2A>-Methode eines <xref:System.Printing.PrintServer>-Objekts und die <xref:System.Printing.EnumeratedPrintQueueTypes>-Enumeration bereitgestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel beginnt der Code mit dem Erstellen eines Arrays von Flags, die die Merkmale der Druck Warteschlangen angeben, die aufgelistet werden sollen. In diesem Beispiel suchen wir nach Druck Warteschlangen, die lokal auf dem Druckserver installiert sind und freigegeben werden. Die <xref:System.Printing.EnumeratedPrintQueueTypes>-Enumeration bietet viele weitere Möglichkeiten.  
  
 Der Code erstellt dann ein <xref:System.Printing.LocalPrintServer> Objekt, eine Klasse, die von <xref:System.Printing.PrintServer>abgeleitet ist. Der lokale Druckserver ist der Computer, auf dem die Anwendung ausgeführt wird.  
  
 Der letzte bedeutende Schritt besteht darin, das Array an die <xref:System.Printing.PrintServer.GetPrintQueues%2A>-Methode zu übergeben.  
  
 Abschließend werden dem Benutzer die Ergebnisse präsentiert.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Sie können dieses Beispiel erweitern, indem Sie die `foreach`-Schleife verwenden, die durch die einzelnen Druck Warteschlangen durchlaufen wird. Beispielsweise können Sie Drucker herausfiltern, die das zweiseitige Drucken nicht unterstützen, indem Sie die <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> Methode der Druck Warteschlange aufrufen und den zurückgegebenen Wert für das vorhanden sein von Duplexing testen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokumentwriter](/windows/win32/printdocs/microsoft-xps-document-writer)
