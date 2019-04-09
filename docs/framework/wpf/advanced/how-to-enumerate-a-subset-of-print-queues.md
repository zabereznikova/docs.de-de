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
ms.openlocfilehash: adcfff0196bd0430ec1ae563fbd5489062de11f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217184"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="38336-102">Vorgehensweise: Auflisten einer Teilmenge von Druckwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="38336-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="38336-103">Eine gängige Situation gegenüberstehen (IT) Experten, die Verwaltung einer unternehmensweiten Gruppe der Drucker ist zum Generieren einer Liste der Drucker mit bestimmten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="38336-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="38336-104">Diese Funktionalität wird bereitgestellt, indem die <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode eine <xref:System.Printing.PrintServer> Objekt und die <xref:System.Printing.EnumeratedPrintQueueTypes> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="38336-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38336-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38336-105">Example</span></span>  
 <span data-ttu-id="38336-106">Der Code zunächst im folgenden Beispiel erstellen ein Array von Flags, die die Merkmale der Druckerwarteschlangen angeben, die wir auflisten möchten.</span><span class="sxs-lookup"><span data-stu-id="38336-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="38336-107">In diesem Beispiel suchen wir nach Druckwarteschlangen, die lokal installiert sind, auf dem Druckerserver und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="38336-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="38336-108">Die <xref:System.Printing.EnumeratedPrintQueueTypes> -Enumeration bietet viele weitere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="38336-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="38336-109">Anschließend erstellt der Code eine <xref:System.Printing.LocalPrintServer> Objekt eine abgeleitete Klasse <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="38336-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="38336-110">Der lokale Druckerserver ist der Computer, auf dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38336-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="38336-111">Der letzte wichtige Schritt ist das Array, das Übergeben der <xref:System.Printing.PrintServer.GetPrintQueues%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="38336-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="38336-112">Abschließend werden dem Benutzer die Ergebnisse präsentiert.</span><span class="sxs-lookup"><span data-stu-id="38336-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="38336-113">Sie könnten dieses Beispiel erweitern, indem Sie die `foreach` Schleife, die jeder Druckwarteschlange werden die Schritte weiter sicherheitsüberprüfungen unterzogen.</span><span class="sxs-lookup"><span data-stu-id="38336-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="38336-114">Angenommen, Sie könnten blenden Sie Drucker, die nicht doppelseitiger Druck unterstützen, indem Sie den Aufruf der Schleife jeder Druckwarteschlange <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> -Methode und Testen Sie den zurückgegebenen Wert, auf das Vorhandensein von Duplexdruck.</span><span class="sxs-lookup"><span data-stu-id="38336-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38336-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38336-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="38336-116">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="38336-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="38336-117">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="38336-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="38336-118">Microsoft XPS-Dokument-Generator</span><span class="sxs-lookup"><span data-stu-id="38336-118">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
