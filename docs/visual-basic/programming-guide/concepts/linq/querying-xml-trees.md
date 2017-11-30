---
title: Querying XML Trees (Visual Basic) (Abfragen von XML-Strukturen (Visual Basic))
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1516cdc58effaa3e738210b948b43d7ed170890a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="c6f07-102">Querying XML Trees (Visual Basic) (Abfragen von XML-Strukturen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="c6f07-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="c6f07-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c6f07-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="c6f07-104">Weitere Informationen zum Schreiben von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfragen finden Sie im [erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="c6f07-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="c6f07-105">Die effektivste Möglichkeit, Daten aus einer von Ihnen instanziierten XML-Struktur zu extrahieren, besteht im Schreiben von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c6f07-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="c6f07-106">Das Kombinieren von Abfragen mit der funktionalen Konstruktion versetzt Sie in die Lage, ein neues XML-Dokument zu generieren, das eine andere Form als das ursprüngliche Dokument hat.</span><span class="sxs-lookup"><span data-stu-id="c6f07-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6f07-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c6f07-107">In This Section</span></span>  
  
|<span data-ttu-id="c6f07-108">Thema</span><span class="sxs-lookup"><span data-stu-id="c6f07-108">Topic</span></span>|<span data-ttu-id="c6f07-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6f07-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c6f07-110">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="c6f07-111">Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="c6f07-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="c6f07-112">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="c6f07-113">Enthält allgemeine Beispiele für das Projizieren aus und das Transformieren in XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="c6f07-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="c6f07-114">Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="c6f07-115">Enthält Abfragetechniken für komplexere Szenarios.</span><span class="sxs-lookup"><span data-stu-id="c6f07-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="c6f07-116">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="c6f07-117">Listet eine Reihe von XPath-Ausdrücken mit ihren [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entsprechungen auf.</span><span class="sxs-lookup"><span data-stu-id="c6f07-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="c6f07-118">Reiner funktionaler Transformationen von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="c6f07-119">Enthält ein kleines Lernprogramm zum Schreiben von Abfragen im Stil der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="c6f07-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6f07-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6f07-120">See Also</span></span>  
 [<span data-ttu-id="c6f07-121">Programmierhandbuch (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  
 [<span data-ttu-id="c6f07-122">Getting Started with LINQ in Visual Basic (Erste Schritte mit LINQ in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6f07-122">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
