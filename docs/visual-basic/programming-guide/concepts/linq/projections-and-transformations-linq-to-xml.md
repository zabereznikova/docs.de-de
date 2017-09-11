---
title: Projektionen und Transformationen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 723685400aadbf883d7ad939e6a1dd5bdeb7ba09
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="81942-102">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="81942-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Projektionen und Transformationen.</span><span class="sxs-lookup"><span data-stu-id="81942-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81942-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81942-104">In This Section</span></span>  
  
|<span data-ttu-id="81942-105">Thema</span><span class="sxs-lookup"><span data-stu-id="81942-105">Topic</span></span>|<span data-ttu-id="81942-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81942-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="81942-107">Gewusst wie: Arbeiten mit Wörterbüchern mit LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="81942-108">Zeigt, wie Sie Wörterbücher in XML und XML in Wörterbücher transformieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="81942-109">Gewusst wie: Transformieren der Form einer XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="81942-110">Zeigt, wie Sie die Form eines XML-Dokuments transformieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="81942-111">Gewusst wie: Steuern des Typs einer Projektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="81942-112">Zeigt, wie Sie den Typ einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage steuern können.</span><span class="sxs-lookup"><span data-stu-id="81942-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="81942-113">Gewusst wie: Projizieren eines neuen Typs (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="81942-114">Zeigt, wie Sie eine Auflistung eines benutzerdefinierten Typs aus einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="81942-115">Gewusst wie: Projizieren eines Objektdiagramms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-115">How to: Project an Object Graph (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="81942-116">Zeigt, wie Sie ein komplexeres Objektdiagramm aus einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="81942-117">Gewusst wie: Projizieren eines anonymen Typs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="81942-118">Zeigt, wie Sie eine Auflistung anonymer Objekte aus einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="81942-119">Gewusst wie: Generieren von Textdateien aus XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="81942-120">Zeigt, wie Sie eine XML-Datei in eine Nicht-XML-Textdatei transformieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="81942-121">Gewusst wie: Generieren von XML aus CSV-Dateien (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="81942-122">Zeigt, wie Sie mit [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] eine CSV-Datei analysieren und XML daraus generieren können.</span><span class="sxs-lookup"><span data-stu-id="81942-122">Shows how to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81942-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81942-123">See Also</span></span>  
 [<span data-ttu-id="81942-124">Abfragen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81942-124">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
