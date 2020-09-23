---
title: LINQ to Objects
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: cb277a255151bf7db9d0fb0a50605ee07ba1423f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075290"
---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="9eab6-102">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-102">LINQ to Objects (Visual Basic)</span></span>

<span data-ttu-id="9eab6-103">Die Bezeichnung „LINQ to Objects“ bezieht sich auf die direkte Verwendung von LINQ-Abfragen mit einer beliebigen <xref:System.Collections.IEnumerable>- oder <xref:System.Collections.Generic.IEnumerable%601>-Auflistung, ohne einen LINQ-Zwischenanbieter oder eine API wie [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) oder [LINQ to XML](../../../../standard/linq/linq-xml-overview.md) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eab6-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span></span> <span data-ttu-id="9eab6-104">Sie können LINQ zur Abfrage beliebiger aufzählbarer Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array> oder <xref:System.Collections.Generic.Dictionary%602> verwenden.</span><span class="sxs-lookup"><span data-stu-id="9eab6-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="9eab6-105">Die Auflistung kann entweder benutzerdefiniert sein oder von einer .NET Framework-API zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9eab6-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="9eab6-106">Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar.</span><span class="sxs-lookup"><span data-stu-id="9eab6-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="9eab6-107">Bisher mussten Sie komplexe `For Each`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9eab6-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="9eab6-108">Im LINQ-Ansatz verfassen Sie einen deklarativen Code, in dem beschrieben wird, was Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="9eab6-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="9eab6-109">Zudem bieten LINQ-Abfragen drei wesentliche Vorteile gegenüber herkömmlichen `For Each`-Schleifen:</span><span class="sxs-lookup"><span data-stu-id="9eab6-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1. <span data-ttu-id="9eab6-110">Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="9eab6-111">Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="9eab6-112">Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.</span><span class="sxs-lookup"><span data-stu-id="9eab6-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="9eab6-113">Je komplexer die für die Daten durchzuführende Operation, desto größer ist im Allgemeinen der Vorteil, den Sie durch die Verwendung von LINQ anstelle der herkömmlichen Iterationsverfahren haben.</span><span class="sxs-lookup"><span data-stu-id="9eab6-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="9eab6-114">Der Zweck dieses Abschnitts ist es, den LINQ-Ansatz anhand einiger Beispiele zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="9eab6-115">Er ist bei weitem nicht als vollständig zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="9eab6-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9eab6-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9eab6-116">In This Section</span></span>  

 [<span data-ttu-id="9eab6-117">LINQ und Zeichenfolgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-117">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)  
 <span data-ttu-id="9eab6-118">Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9eab6-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="9eab6-119">Dieser Abschnitt umfasst auch Links zu Themen, die diese Prinzipien veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="9eab6-120">LINQ und Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-120">LINQ and Reflection (Visual Basic)</span></span>](linq-and-reflection.md)  
 <span data-ttu-id="9eab6-121">Verweist auf ein Beispiel, das darstellt, wie LINQ die Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="9eab6-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="9eab6-122">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9eab6-122">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)  
 <span data-ttu-id="9eab6-123">Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9eab6-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="9eab6-124">Dieser Abschnitt umfasst auch Links zu Themen, die diese Konzepte veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="9eab6-125">Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="9eab6-126">Veranschaulicht die Abfrage einer ArrayList in Visual Basic und C#.</span><span class="sxs-lookup"><span data-stu-id="9eab6-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="9eab6-127">Gewusst wie: Hinzufügen von benutzerdefinierten Methoden für LINQ-Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="9eab6-128">Erläutert die Erweiterung des Methodensatzes, den Sie durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9eab6-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="9eab6-129">Language Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9eab6-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)  
 <span data-ttu-id="9eab6-130">Stellt Links zu Themen bereit, die LINQ erläutern. Zudem werden Codebeispiele bereitgestellt, die Abfragen durchführen.</span><span class="sxs-lookup"><span data-stu-id="9eab6-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
