---
title: LINQ to Objects (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
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
ms.openlocfilehash: 82094ee6232ef5b1884f1b4b15eacb635be758aa
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="cab4c-102">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="cab4c-103">Der Begriff "LINQ to Objects" bezieht sich auf die Verwendung von LINQ-Abfragen mit einem <xref:System.Collections.IEnumerable>oder <xref:System.Collections.Generic.IEnumerable%601>Auflistung direkt verwenden, ohne die Verwendung eines intermediate LINQ-Anbieter oder einer API wie [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) oder [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="cab4c-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="cab4c-104">Sie können LINQ zur Abfrage beliebiger aufzählbaren Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array>, oder <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="cab4c-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="cab4c-105">Die Auflistung kann benutzerdefiniert sein oder von einer .NET Framework-API zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cab4c-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="cab4c-106">Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar.</span><span class="sxs-lookup"><span data-stu-id="cab4c-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="cab4c-107">Bisher mussten Sie komplexe `For Each`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cab4c-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="cab4c-108">In der LINQ-Ansatz schreiben Sie deklarativen Code, der beschreibt, was Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="cab4c-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="cab4c-109">Darüber hinaus LINQ-Abfragen bieten drei wesentliche Vorteile gegenüber herkömmlichen `For Each` Schleifen:</span><span class="sxs-lookup"><span data-stu-id="cab4c-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1.  <span data-ttu-id="cab4c-110">Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="cab4c-111">Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="cab4c-112">Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.</span><span class="sxs-lookup"><span data-stu-id="cab4c-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="cab4c-113">Im Allgemeinen gilt: Je komplexer die Operation, die für die Daten ausgeführt werden soll, die mehr Vorteile Sie erkennen mithilfe von LINQ anstelle der herkömmlichen Iterationsverfahren erreichen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="cab4c-114">Dieser Abschnitt dient, den LINQ--Ansatz anhand einiger Beispiele veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="cab4c-115">Er ist bei weitem nicht als vollständig zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="cab4c-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cab4c-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cab4c-116">In This Section</span></span>  
 [<span data-ttu-id="cab4c-117">LINQ und Zeichenfolgen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="cab4c-118">Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cab4c-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="cab4c-119">Dieser Abschnitt umfasst auch Links zu Themen, die diese Prinzipien veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="cab4c-120">LINQ und Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-120">LINQ and Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="cab4c-121">Verweist auf ein Beispiel, das veranschaulicht, wie LINQ Reflektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="cab4c-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="cab4c-122">LINQ und Dateiverzeichnisse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-122">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="cab4c-123">Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cab4c-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="cab4c-124">Dieser Abschnitt umfasst auch Links zu Themen, die diese Konzepte veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="cab4c-125">Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="cab4c-126">Abfragen von ArrayList in c# veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cab4c-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="cab4c-127">Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="cab4c-128">Erläutert, wie das Erweitern der Methoden für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden, die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="cab4c-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="cab4c-129">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cab4c-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="cab4c-130">Enthält Links zu Themen, die erklären LINQ und Beispiele von Codes, die Abfragen durchführen.</span><span class="sxs-lookup"><span data-stu-id="cab4c-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
