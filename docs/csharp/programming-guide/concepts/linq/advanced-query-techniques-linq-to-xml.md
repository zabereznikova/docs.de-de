---
title: Erweiterte Abfragetechniken (LINQ to XML) (C#)
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
ms.assetid: 028d978e-215b-4d50-ba70-adce0659386d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91460ed99854edda829503d451728c4274d7ba2b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="advanced-query-techniques-linq-to-xml-c"></a><span data-ttu-id="5cffe-102">Erweiterte Abfragetechniken (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-102">Advanced Query Techniques (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5cffe-103">Dieser Abschnitt enthält Beispiele für erweiterte [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragetechniken.</span><span class="sxs-lookup"><span data-stu-id="5cffe-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cffe-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5cffe-104">In This Section</span></span>  
  
|<span data-ttu-id="5cffe-105">Thema</span><span class="sxs-lookup"><span data-stu-id="5cffe-105">Topic</span></span>|<span data-ttu-id="5cffe-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cffe-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5cffe-107">Vorgehensweise: Verbinden von zwei Auflistungen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-107">How to: Join Two Collections (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="5cffe-108">Zeigt, wie mit der `Join`-Klausel die Vorteile von Beziehungen in XML-Daten genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="5cffe-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="5cffe-109">Vorgehensweise: Erstellen einer Hierarchie mittels Gruppierung (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-109">How to: Create Hierarchy Using Grouping (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="5cffe-110">Zeigt, wie Daten gruppiert werden und anschließend anhand der Gruppierung XML generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5cffe-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="5cffe-111">Vorgehensweise: Abfragen von LINQ to XML mit XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-111">How to: Query LINQ to XML Using XPath (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="5cffe-112">Zeigt, wie Auflistungen anhand von XPath-Abfragen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="5cffe-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="5cffe-113">Vorgehensweise: Schreiben einer LINQ to XML-Axis-Methode (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-113">How to: Write a LINQ to XML Axis Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="5cffe-114">Zeigt die Vorgehensweise beim Schreiben einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsenmethode.</span><span class="sxs-lookup"><span data-stu-id="5cffe-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="5cffe-115">Vorgehensweise: Durchführen einer Streamingtransformation von Text in XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-115">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transformations-of-text-to-xml.md)|<span data-ttu-id="5cffe-116">Zeigt die Vorgehensweise beim Transformieren sehr großer Textdateien in XML bei gleichzeitiger Beibehaltung einer geringen Speicherbeanspruchung.</span><span class="sxs-lookup"><span data-stu-id="5cffe-116">Shows how to transform very large text files into XML while maintaining a small memory footprint.</span></span>|  
|[<span data-ttu-id="5cffe-117">Vorgehensweise: Auflisten aller Knoten in einer Struktur (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-117">How to: List All Nodes in a Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="5cffe-118">Präsentiert eine Hilfsprogrammmethode, die alle Knoten in einer XML-Struktur auflistet.</span><span class="sxs-lookup"><span data-stu-id="5cffe-118">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="5cffe-119">Diese Methode eignet sich zum Debuggen von Code, der eine XML-Struktur ändert.</span><span class="sxs-lookup"><span data-stu-id="5cffe-119">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="5cffe-120">Vorgehensweise: Abrufen von Absätzen aus einem Office Open-XML-Dokument (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-120">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="5cffe-121">Enthält Code, der ein Office Open XML-Dokument öffnet und die Absätze in einer Auflistung von XElement-Objekten, den Text der Absätze und die Formatvorlagen der Absätze abruft.</span><span class="sxs-lookup"><span data-stu-id="5cffe-121">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="5cffe-122">Vorgehensweise: Ändern eines Office Open-XML-Dokuments (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-122">How to: Modify an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="5cffe-123">Enthält Code, der ein Office Open XML-Dokument öffnet, ändert und speichert.</span><span class="sxs-lookup"><span data-stu-id="5cffe-123">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="5cffe-124">Vorgehensweise: Auffüllen einer XML-Struktur über das Dateisystem (C#)</span><span class="sxs-lookup"><span data-stu-id="5cffe-124">How to: Populate an XML Tree from the File System (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="5cffe-125">Enthält Code, der aus dem Dateisystem eine XML-Struktur erstellt.</span><span class="sxs-lookup"><span data-stu-id="5cffe-125">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cffe-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cffe-126">See Also</span></span>  
 [<span data-ttu-id="5cffe-127">Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="5cffe-127">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

