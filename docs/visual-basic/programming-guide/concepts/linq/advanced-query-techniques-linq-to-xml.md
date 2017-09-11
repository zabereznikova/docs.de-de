---
title: Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 79be877c-fadc-4dfb-9f03-426082b13656
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6983fa5b9637210bb3c56e8f693eb4f956dab0a8
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="advanced-query-techniques-linq-to-xml-visual-basic"></a><span data-ttu-id="a97f3-102">Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-102">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a97f3-103">Dieser Abschnitt enthält Beispiele für erweiterte [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfragetechniken.</span><span class="sxs-lookup"><span data-stu-id="a97f3-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a97f3-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a97f3-104">In This Section</span></span>  
  
|<span data-ttu-id="a97f3-105">Thema</span><span class="sxs-lookup"><span data-stu-id="a97f3-105">Topic</span></span>|<span data-ttu-id="a97f3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a97f3-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a97f3-107">Gewusst wie: Verbinden von zwei Auflistungen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-107">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="a97f3-108">Zeigt, wie mit der `Join`-Klausel die Vorteile von Beziehungen in XML-Daten genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="a97f3-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="a97f3-109">Gewusst wie: Erstellen einer Hierarchie mittels Gruppierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-109">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="a97f3-110">Zeigt, wie Daten gruppiert werden und anschließend anhand der Gruppierung XML generiert wird.</span><span class="sxs-lookup"><span data-stu-id="a97f3-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="a97f3-111">Gewusst wie: Abfragen von LINQ to XML mit XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-111">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="a97f3-112">Zeigt, wie Auflistungen anhand von XPath-Abfragen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a97f3-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="a97f3-113">Gewusst wie: Schreiben einer LINQ to XML-Achsenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-113">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="a97f3-114">Zeigt die Vorgehensweise beim Schreiben einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achsenmethode.</span><span class="sxs-lookup"><span data-stu-id="a97f3-114">Shows how to write a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axis method.</span></span>|  
|[<span data-ttu-id="a97f3-115">Gewusst wie: Auflisten aller Knoten in einer Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-115">How to: List All Nodes in a Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="a97f3-116">Präsentiert eine Hilfsprogrammmethode, die alle Knoten in einer XML-Struktur auflistet.</span><span class="sxs-lookup"><span data-stu-id="a97f3-116">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="a97f3-117">Diese Methode eignet sich zum Debuggen von Code, der eine XML-Struktur ändert.</span><span class="sxs-lookup"><span data-stu-id="a97f3-117">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="a97f3-118">Gewusst wie: Abrufen von Absätzen aus einem Office Open XML-Dokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-118">How to: Retrieve Paragraphs from an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="a97f3-119">Enthält Code, der ein Office Open XML-Dokument öffnet und die Absätze in einer Auflistung von XElement-Objekten, den Text der Absätze und die Formatvorlagen der Absätze abruft.</span><span class="sxs-lookup"><span data-stu-id="a97f3-119">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="a97f3-120">Gewusst wie: Ändern eines Office Open XML-Dokuments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-120">How to: Modify an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="a97f3-121">Enthält Code, der ein Office Open XML-Dokument öffnet, ändert und speichert.</span><span class="sxs-lookup"><span data-stu-id="a97f3-121">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="a97f3-122">Gewusst wie: Auffüllen einer XML-Struktur aus dem Dateisystem (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-122">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="a97f3-123">Enthält Code, der aus dem Dateisystem eine XML-Struktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="a97f3-123">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a97f3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a97f3-124">See Also</span></span>  
 [<span data-ttu-id="a97f3-125">Abfragen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a97f3-125">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
