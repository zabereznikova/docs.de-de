---
title: "Einführung in LINQ (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2c02daacc2674da31715e5fda027b97e6b7bc97
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="e02e5-102">Einführung in LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e02e5-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="e02e5-103">Language-Integrated Query (LINQ) ist eine Innovation in .NET Framework, Version 3.5, Bridges die Lücke zwischen der Welt der Objekte und der Welt der Daten eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e02e5-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="e02e5-104">Abfragen von Daten werden in der Vergangenheit ausgedrückt, wie einfache Zeichenfolgen ohne Überprüfung an Zeit oder IntelliSense-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="e02e5-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="e02e5-105">Darüber hinaus müssen Sie für jeden Typ von Datenquelle eine andere Abfragesprache erlernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw..</span><span class="sxs-lookup"><span data-stu-id="e02e5-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="e02e5-106">LINQ ist ein *Abfrage* einem erstklassigen Sprachkonstrukt in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e02e5-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="e02e5-107">Sie schreiben die Abfragen für stark typisierte Auflistungen von Objekten mithilfe der Schlüsselwörter und bekannten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e02e5-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="e02e5-108">Sie können LINQ-Abfragen in Visual Basic schreiben, für die SQL Server-Datenbanken, XML-Dokumente, ADO.NET-Datasets und jeder Auflistung von Objekten, die unterstützt <xref:System.Collections.IEnumerable>oder die generische <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="e02e5-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="e02e5-109">LINQ-Unterstützung wird auch für viele Webdienste und andere Datenbank-Implementierungen von Drittanbietern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e02e5-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="e02e5-110">Sie können LINQ-Abfragen in neuen Projekten oder zusammen mit nicht-LINQ-Abfragen in vorhandenen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e02e5-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="e02e5-111">Die einzige Voraussetzung ist, dass das Projekt auf .NET Framework 3.5 oder höher abzielen.</span><span class="sxs-lookup"><span data-stu-id="e02e5-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="e02e5-112">In Visual Studio die folgende Abbildung zeigt eine teilweise abgeschlossen LINQ-Abfrage für eine SQL Server-Datenbank in c# und Visual Basic mit vollständigen Typprüfung und IntelliSense-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="e02e5-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="e02e5-113">![LINQ-Abfrage mit Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="e02e5-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e02e5-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e02e5-114">Next Steps</span></span>  
 <span data-ttu-id="e02e5-115">Weitere Informationen über LINQ finden Starten von vertraut mit einigen grundlegenden Konzepten im Abschnitt Erste Schritte [erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), und Lesen Sie die Dokumentation für die LINQ-Technologie, die Sie interessieren:</span><span class="sxs-lookup"><span data-stu-id="e02e5-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="e02e5-116">SQL Server-Datenbanken: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="e02e5-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="e02e5-117">XML-Dokumente: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="e02e5-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="e02e5-118">ADO.NET Datasets: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span><span class="sxs-lookup"><span data-stu-id="e02e5-118">ADO.NET Datasets: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span></span>  
  
-   <span data-ttu-id="e02e5-119">Auflistungen von .NET, Dateien, Zeichenfolgen usw.: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="e02e5-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e02e5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e02e5-120">See Also</span></span>  
 [<span data-ttu-id="e02e5-121">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e02e5-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
