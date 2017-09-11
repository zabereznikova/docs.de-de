---
title: Abfragen von XML-Strukturen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b2aa1e4852657590449be3e297302bf41ba3e5d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="80feb-102">Querying XML Trees (Visual Basic) (Abfragen von XML-Strukturen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="80feb-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="80feb-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="80feb-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
 <span data-ttu-id="80feb-104">Weitere Informationen zum Schreiben von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Abfragen finden Sie unter [erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="80feb-104">For more information about writing [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="80feb-105">Die effektivste Möglichkeit, Daten aus einer von Ihnen instanziierten XML-Struktur zu extrahieren, besteht im Schreiben von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="80feb-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="80feb-106">Das Kombinieren von Abfragen mit der funktionalen Konstruktion versetzt Sie in die Lage, ein neues XML-Dokument zu generieren, das eine andere Form als das ursprüngliche Dokument hat.</span><span class="sxs-lookup"><span data-stu-id="80feb-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80feb-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="80feb-107">In This Section</span></span>  
  
|<span data-ttu-id="80feb-108">Thema</span><span class="sxs-lookup"><span data-stu-id="80feb-108">Topic</span></span>|<span data-ttu-id="80feb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80feb-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="80feb-110">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80feb-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="80feb-111">Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="80feb-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="80feb-112">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80feb-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="80feb-113">Enthält allgemeine Beispiele für das Projizieren aus und das Transformieren in XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="80feb-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="80feb-114">Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80feb-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="80feb-115">Enthält Abfragetechniken für komplexere Szenarios.</span><span class="sxs-lookup"><span data-stu-id="80feb-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="80feb-116">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80feb-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="80feb-117">Stellt eine Reihe von XPath-Ausdrücken und ihre [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="80feb-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="80feb-118">Reine funktionale Transformationen von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80feb-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="80feb-119">Enthält ein kleines Lernprogramm zum Schreiben von Abfragen im Stil der funktionalen Programmierung.</span><span class="sxs-lookup"><span data-stu-id="80feb-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80feb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80feb-120">See Also</span></span>  
 <span data-ttu-id="80feb-121">[Programmierhandbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="80feb-121">[Programming Guide (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
<span data-ttu-id="80feb-122"> [Erste Schritte mit LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="80feb-122"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span></span>
