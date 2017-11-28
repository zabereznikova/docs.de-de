---
title: Projektionen und Transformationen (LINQ to XML) (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bb0457ab-1823-47e6-9d2d-c93c958cc913
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81172ebb440bc2737bbe3f1de0f1dd3cf6e086c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="projections-and-transformations-linq-to-xml-c"></a><span data-ttu-id="f2347-102">Projektionen und Transformationen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f2347-102">Projections and Transformations (LINQ to XML) (C#)</span></span>
<span data-ttu-id="f2347-103">Dieser Abschnitt enthält Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Projektionen und -Transformationen.</span><span class="sxs-lookup"><span data-stu-id="f2347-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2347-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2347-104">In This Section</span></span>  
  
|<span data-ttu-id="f2347-105">Thema</span><span class="sxs-lookup"><span data-stu-id="f2347-105">Topic</span></span>|<span data-ttu-id="f2347-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2347-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f2347-107">How to: Work with Dictionaries Using LINQ to XML (C#) (Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-107">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="f2347-108">Zeigt, wie Sie Wörterbücher in XML und XML in Wörterbücher transformieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="f2347-109">How to: Transform the Shape of an XML Tree (C#) (Vorgehensweise: Transformieren der Form einer XML-Struktur (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-109">How to: Transform the Shape of an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="f2347-110">Zeigt, wie Sie die Form eines XML-Dokuments transformieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="f2347-111">How to: Control the Type of a Projection (C#) (Vorgehensweise: Steuern des Typs einer Projektion (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-111">How to: Control the Type of a Projection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="f2347-112">Zeigt, wie Sie den Typ einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage steuern können.</span><span class="sxs-lookup"><span data-stu-id="f2347-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="f2347-113">How to: Project a New Type (LINQ to XML) (C#) (Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-113">How to: Project a New Type (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="f2347-114">Zeigt, wie Sie eine Auflistung eines benutzerdefinierten Typs aus einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="f2347-115">How to: Project an Object Graph (C#) (Vorgehensweise: Projektieren eines Objektdiagramms (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-115">How to: Project an Object Graph (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="f2347-116">Zeigt, wie Sie ein komplexeres Objektdiagramm aus einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="f2347-117">How to: Project an Anonymous Type (C#) (Vorgehensweise: Projektieren eines anonymen Typs (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-117">How to: Project an Anonymous Type (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="f2347-118">Zeigt, wie Sie eine Auflistung anonymer Objekte aus einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage projizieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="f2347-119">How to: Generate Text Files from XML (C#) (Vorgehensweise: Generieren von Textdateien aus XML (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-119">How to: Generate Text Files from XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="f2347-120">Zeigt, wie Sie eine XML-Datei in eine Nicht-XML-Textdatei transformieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="f2347-121">How to: Generate XML from CSV Files (C#) (Vorgehensweise: Generieren von XML aus CSV-Dateien (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-121">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="f2347-122">Zeigt, wie Sie mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] eine CSV-Datei analysieren und XML daraus generieren können.</span><span class="sxs-lookup"><span data-stu-id="f2347-122">Shows how to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2347-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2347-123">See Also</span></span>  
 [<span data-ttu-id="f2347-124">Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))</span><span class="sxs-lookup"><span data-stu-id="f2347-124">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
