---
title: "Einführung in LINQ (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6fd14840cfffb1a59949251b26c168aada336de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="b407f-102">Einführung in LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b407f-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="b407f-103">Language Integrated Query (LINQ) ist eine in .NET Framework-Version 3.5 eingeführte Innovation, die die Lücke zwischen der Welt der Objekte und der Welt der Daten überbrückt.</span><span class="sxs-lookup"><span data-stu-id="b407f-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="b407f-104">Abfragen von Daten werden gewöhnlich als einfache Zeichenfolgen ohne Typüberprüfung zur Kompilierzeit oder IntelliSense-Unterstützung ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="b407f-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="b407f-105">Darüber hinaus müssen Sie für jeden Typ von Datenquelle eine andere Abfragesprache erlernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw.</span><span class="sxs-lookup"><span data-stu-id="b407f-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="b407f-106">Durch LINQ wird eine *Abfrage* zu einem erstklassigen Sprachkonstrukt in C#.</span><span class="sxs-lookup"><span data-stu-id="b407f-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="b407f-107">Sie schreiben Abfragen für stark typisierte Auflistungen von Objekten mithilfe von Sprachschlüsselwörtern und bekannten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="b407f-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="b407f-108">Sie können LINQ-Abfragen in C# für SQL Server-Datenbanken, XML-Dokumente, ADO.NET-Datasets und jede Auflistung von Objekten schreiben, die <xref:System.Collections.IEnumerable> oder die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b407f-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b407f-109">LINQ-Unterstützung wird auch von Drittanbietern für viele Webdienste und andere Datenbankimplementierungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b407f-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="b407f-110">Sie können LINQ-Abfragen in neuen Projekten oder zusammen mit nicht-LINQ-Abfragen in vorhandenen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="b407f-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="b407f-111">Die einzige Voraussetzung ist, dass sich das Projekt auf .NET Framework 3.5 oder höher bezieht.</span><span class="sxs-lookup"><span data-stu-id="b407f-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="b407f-112">Die folgende Abbildung aus Visual Studio zeigt eine teilweise abgeschlossene LINQ-Abfrage für eine SQL Server-Datenbank in C# und Visual Basic mit vollständiger Typüberprüfung und IntelliSense-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="b407f-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="b407f-113">![LINQ-Abfrage mit IntelliSense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="b407f-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b407f-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b407f-114">Next Steps</span></span>  
 <span data-ttu-id="b407f-115">Für weitere Informationen über LINQ können Sie sich zunächst mit einigen grundlegenden Konzepten im Abschnitt [Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) vertraut machen und dann die Dokumentation für die LINQ-Technologie, die Sie interessiert, lesen:</span><span class="sxs-lookup"><span data-stu-id="b407f-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="b407f-116">SQL Server-Datenbanken: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="b407f-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="b407f-117">XML-Dokumente: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="b407f-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="b407f-118">ADO.NET-Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="b407f-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="b407f-119">.NET-Auflistungen, -Dateien, -Zeichenfolgen usw.: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="b407f-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b407f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b407f-120">See Also</span></span>  
 [<span data-ttu-id="b407f-121">Language-Integrated Query (LINQ) (Sprachintegrierte Abfrage (LINQ))</span><span class="sxs-lookup"><span data-stu-id="b407f-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
