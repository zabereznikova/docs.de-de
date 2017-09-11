---
title: Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4bad11434ed2610492854d5ec4a7a84bceb189f3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="ba615-102">Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="ba615-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="ba615-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ba615-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="ba615-104">Weitere Informationen zum Schreiben von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen finden Sie unter [Erste Schritte mit LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="ba615-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="ba615-105">Die effektivste Möglichkeit, Daten aus einer von Ihnen instanziierten XML-Struktur zu extrahieren, besteht im Schreiben von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ba615-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="ba615-106">Das Kombinieren von Abfragen mit der funktionalen Konstruktion versetzt Sie in die Lage, ein neues XML-Dokument zu generieren, das eine andere Form als das ursprüngliche Dokument hat.</span><span class="sxs-lookup"><span data-stu-id="ba615-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba615-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba615-107">In This Section</span></span>  
  
|<span data-ttu-id="ba615-108">Thema</span><span class="sxs-lookup"><span data-stu-id="ba615-108">Topic</span></span>|<span data-ttu-id="ba615-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba615-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ba615-110">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="ba615-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="ba615-111">Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="ba615-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="ba615-112">Projections and Transformations (LINQ to XML) (C#) (Projektionen und Transformationen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="ba615-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="ba615-113">Enthält allgemeine Beispiele für das Projizieren aus und das Transformieren in XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="ba615-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="ba615-114">Advanced Query Techniques (LINQ to XML) (C#) (Erweiterte Abfragetechniken (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="ba615-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="ba615-115">Enthält Abfragetechniken für komplexere Szenarios.</span><span class="sxs-lookup"><span data-stu-id="ba615-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="ba615-116">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="ba615-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="ba615-117">Listet eine Reihe von XPath-Ausdrücken mit ihren [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entsprechungen auf.</span><span class="sxs-lookup"><span data-stu-id="ba615-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="ba615-118">Pure Functional Transformations of XML (C#) (Reine funktionale XML-Transformationen (C#))</span><span class="sxs-lookup"><span data-stu-id="ba615-118">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="ba615-119">Enthält ein kleines Lernprogramm zum Schreiben von Abfragen im Stil der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="ba615-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba615-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba615-120">See Also</span></span>  
 <span data-ttu-id="ba615-121">[Programmierhandbuch (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ba615-121">[Programming Guide (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="ba615-122">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="ba615-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

