---
title: Einführung in LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: b0fa27fd81b85eb89712f9e81f42e06505878f86
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397557"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="807f7-102">Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="807f7-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="807f7-103">Language Integrated Query (LINQ) ist eine in .NET Framework-Version 3.5 eingeführte Innovation, die die Lücke zwischen der Welt der Objekte und der Welt der Daten überbrückt.</span><span class="sxs-lookup"><span data-stu-id="807f7-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="807f7-104">Abfragen von Daten werden gewöhnlich als einfache Zeichenfolgen ohne Typüberprüfung zur Kompilierzeit und ohne IntelliSense-Unterstützung ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="807f7-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="807f7-105">Außerdem müssen Sie für jeden Datenquellentyp eine andere Abfragesprache lernen: SQL-Datenbanken, XML-Dokumente, verschiedene Webdienste usw.</span><span class="sxs-lookup"><span data-stu-id="807f7-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="807f7-106">LINQ stellt eine *Abfrage* zu einem erstklassigen Sprachkonstrukt in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="807f7-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="807f7-107">Sie schreiben Abfragen für stark typisierte Auflistungen von Objekten mithilfe von Sprachschlüsselwörtern und bekannten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="807f7-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="807f7-108">Sie können LINQ-Abfragen in Visual Basic für SQL Server-Datenbanken, XML-Dokumente, ADO.NET-Datasets und jede Auflistung von Objekten schreiben, die <xref:System.Collections.IEnumerable> oder die generische- <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="807f7-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="807f7-109">LINQ-Unterstützung wird auch von Drittanbietern für viele Webdienste und andere Datenbankimplementierungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="807f7-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="807f7-110">Sie können LINQ-Abfragen in neuen Projekten oder zusammen mit nicht-LINQ-Abfragen in vorhandenen Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="807f7-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="807f7-111">Die einzige Voraussetzung ist, dass sich das Projekt auf .NET Framework 3.5 oder höher bezieht.</span><span class="sxs-lookup"><span data-stu-id="807f7-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="807f7-112">Die folgende Abbildung aus Visual Studio zeigt eine teilweise abgeschlossene LINQ-Abfrage für eine SQL Server-Datenbank in C# und Visual Basic mit vollständiger Typüberprüfung und IntelliSense-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="807f7-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagramm einer LINQ-Abfrage mit IntelliSense](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="807f7-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="807f7-114">Next Steps</span></span>  
 <span data-ttu-id="807f7-115">Wenn Sie weitere Informationen zu LINQ benötigen, machen Sie sich zunächst mit einigen grundlegenden Konzepten im Abschnitt Erste Schritte [mit LINQ in Visual Basic](getting-started-with-linq.md)vertraut, und lesen Sie dann die Dokumentation für die LINQ-Technologie, an der Sie interessiert sind:</span><span class="sxs-lookup"><span data-stu-id="807f7-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="807f7-116">SQL Server-Datenbanken: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="807f7-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="807f7-117">XML-Dokumente: [LINQ to XML (Visual Basic)](linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="807f7-117">XML documents: [LINQ to XML (Visual Basic)](linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="807f7-118">ADO.NET-Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="807f7-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="807f7-119">.NET-Auflistungen,-Dateien,-Zeichen folgen usw.: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="807f7-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807f7-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="807f7-120">See also</span></span>

- [<span data-ttu-id="807f7-121">Language Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="807f7-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
