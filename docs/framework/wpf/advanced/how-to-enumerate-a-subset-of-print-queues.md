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
ms.workload: dotnet
ms.openlocfilehash: 397ec40e2d8a0694e208296593687e9268546fc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="869f3-102">Gewusst wie: Auflisten einer Teilmenge von Druckwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="869f3-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="869f3-103">Eine allgemeine Situation gegenüberstehen (IT) Spezialisten verwalten einen Satz unternehmensweiten der Drucker ist zum Generieren einer Liste von Druckern mit bestimmten Merkmalen.</span><span class="sxs-lookup"><span data-stu-id="869f3-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="869f3-104">Diese Funktionalität wird bereitgestellt, indem Sie die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode von einer <xref:System.Printing.PrintServer> Objekt und die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="869f3-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="869f3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="869f3-105">Example</span></span>  
 <span data-ttu-id="869f3-106">Im folgenden Beispiel wird zuerst im Code erstellen ein Array von Flags, die die Merkmale der Druckerwarteschlangen angeben, die wir auflisten möchten.</span><span class="sxs-lookup"><span data-stu-id="869f3-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="869f3-107">In diesem Beispiel werden wir Druckwarteschlangen gesucht, die lokal installiert sind, auf dem Druckserver und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="869f3-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="869f3-108">Die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration bietet viele weitere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="869f3-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="869f3-109">Anschließend erstellt der Code eine <xref:System.Printing.LocalPrintServer> -Objekt, eine abgeleitete Klasse <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="869f3-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="869f3-110">Der lokale Druckerserver ist der Computer, auf dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="869f3-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="869f3-111">Der letzte wichtige Schritt ist zum Übergeben des Arrays an die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="869f3-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="869f3-112">Abschließend werden dem Benutzer die Ergebnisse präsentiert.</span><span class="sxs-lookup"><span data-stu-id="869f3-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="869f3-113">Könnten Sie in diesem Beispiel erweitern, indem Sie die `foreach` -Schleife, die weiter über jede Druckerwarteschlange Schritte ausblenden.</span><span class="sxs-lookup"><span data-stu-id="869f3-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="869f3-114">Angenommen, Sie konnte Bildschirm, Drucker, die nicht drucken zweiseitigen unterstützen, durch die Verwendung des Schleife Aufrufs jede Druckerwarteschlange <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode und Testen der zurückgegebene Wert auf das Vorhandensein des Duplexdruck.</span><span class="sxs-lookup"><span data-stu-id="869f3-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869f3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="869f3-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="869f3-116">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="869f3-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="869f3-117">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="869f3-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="869f3-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="869f3-118">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
