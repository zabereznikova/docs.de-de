---
title: Abfragen von XML-Strukturen
ms.date: 07/20/2015
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
ms.openlocfilehash: 22e3dd873e2be8381f3d8da8f7c4284d09e45543
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411869"
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="83677-102">Querying XML Trees (Visual Basic) (Abfragen von XML-Strukturen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="83677-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="83677-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="83677-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="83677-104">Weitere Informationen zum Schreiben von LINQ-Abfragen finden Sie unter [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="83677-104">For more information about writing LINQ queries, see [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="83677-105">Die effektivste Möglichkeit, Daten aus einer von Ihnen instanziierten XML-Struktur zu extrahieren, besteht im Schreiben von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="83677-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="83677-106">Das Kombinieren von Abfragen mit der funktionalen Konstruktion versetzt Sie in die Lage, ein neues XML-Dokument zu generieren, das eine andere Form als das ursprüngliche Dokument hat.</span><span class="sxs-lookup"><span data-stu-id="83677-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83677-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="83677-107">In This Section</span></span>  
  
|<span data-ttu-id="83677-108">Thema</span><span class="sxs-lookup"><span data-stu-id="83677-108">Topic</span></span>|<span data-ttu-id="83677-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="83677-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="83677-110">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)|<span data-ttu-id="83677-111">Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="83677-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="83677-112">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="83677-113">Enthält allgemeine Beispiele für das Projizieren aus und das Transformieren in XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="83677-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="83677-114">Erweiterte Abfrage Techniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="83677-115">Enthält Abfragetechniken für komplexere Szenarios.</span><span class="sxs-lookup"><span data-stu-id="83677-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="83677-116">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)|<span data-ttu-id="83677-117">Listet eine Reihe von XPath-Ausdrücken mit ihren [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entsprechungen auf.</span><span class="sxs-lookup"><span data-stu-id="83677-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="83677-118">Reine funktionale XML-Transformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](pure-functional-transformations-of-xml.md)|<span data-ttu-id="83677-119">Enthält ein kleines Lernprogramm zum Schreiben von Abfragen im Stil der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="83677-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83677-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83677-120">See also</span></span>

- [<span data-ttu-id="83677-121">Programmier Handbuch (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83677-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](programming-guide-linq-to-xml.md)
- [<span data-ttu-id="83677-122">Erste Schritte mit LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83677-122">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
