---
title: Verarbeitung von XML-Daten mit LINQ to XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 26258489742db3de108ddf68f68074682c30fe57
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="4bcf6-102">Verarbeitung von XML-Daten mit LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="4bcf6-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="4bcf6-103">LINQ to XML ist das neue Modell in .NET Framework 3.5 zum Verarbeiten von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="4bcf6-104">Mit LINQ to XML können Entwickler alles tun, was man mit XML-Daten tun kann: abfragen, ändern, erstellen, speichern und XML-Dokumente serialisieren.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="4bcf6-105">Die wirklichen Vorteile liegen in den Abfrage- und Erstellungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="4bcf6-106">Abfragen in LINQ to XML sind kompakt und aussagekräftig. Die verwendete Syntax ähnelt mehr SQL als XPath oder XQuery.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="4bcf6-107">Da Abfrageergebnisse als Auflistungen von Elementen oder Attributen zurückgegeben und als Parameter für <legacyBold>XElement</legacyBold>-Objekte verwendet werden können, lassen sich XML-Strukturen problemlos von einer Form in eine andere transformieren.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="4bcf6-108">LINQ to XML nutzt die Language Integrated Query (LINQ)-Technologie in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="4bcf6-109">LINQ erweitert die Sprachsyntax von C# und Visual Basic, um leistungsfähige Abfragefunktionen bereitzustellen, für die es praktisch keine Datenspeichergrenzen gibt.</span><span class="sxs-lookup"><span data-stu-id="4bcf6-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="4bcf6-110">Eine ausführliche Erörterung der Verwendung von LINQ to XML finden Sie unter [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13). Eine Übersicht über das LINQ-Framework finden Sie unter [LINQ (Language-Integrated Query, sprachintegrierte Abfrage)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="4bcf6-110">See [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) for a detailed discussion of its use, and see [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) for an overview of the LINQ framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcf6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bcf6-111">See Also</span></span>  
 <xref:System.Xml.Linq>  
 <xref:System.Linq>  
 [<span data-ttu-id="4bcf6-112">LINQ to XML im Vergleich zu DOM</span><span class="sxs-lookup"><span data-stu-id="4bcf6-112">LINQ to XML vs. DOM</span></span>](http://msdn.microsoft.com/library/19b5ed02-feb2-455a-8897-f7f0fd76aca3)  
 [<span data-ttu-id="4bcf6-113">LINQ to XML im Vergleich zu anderen XML-Technologien</span><span class="sxs-lookup"><span data-stu-id="4bcf6-113">LINQ to XML vs. Other XML Technologies</span></span>](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)
