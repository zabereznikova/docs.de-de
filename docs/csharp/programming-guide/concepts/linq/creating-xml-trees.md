---
title: Erstellen von XML-Strukturen (C#)
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
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99b197b86096b803b9732ab2546b23ff59e3e2fe
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="4bb88-102">Erstellen von XML-Strukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="4bb88-103">Eine der häufigsten XML-Aufgaben besteht darin, eine XML-Struktur zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="4bb88-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="4bb88-104">In diesem Abschnitt werden mehrere Möglichkeiten für die Erstellung solcher Strukturen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4bb88-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bb88-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4bb88-105">In This Section</span></span>  
  
|<span data-ttu-id="4bb88-106">Thema</span><span class="sxs-lookup"><span data-stu-id="4bb88-106">Topic</span></span>|<span data-ttu-id="4bb88-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bb88-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4bb88-108">Funktionale Konstruktion (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="4bb88-109">Enthält eine Übersicht über die funktionale Konstruktion in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bb88-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="4bb88-110">Die funktionale Konstruktion ermöglicht es Ihnen, Ihre XML-Struktur ganz oder teilweise in einer einzigen Anweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4bb88-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="4bb88-111">In diesem Thema wird außerdem gezeigt, wie Sie beim Konstruieren einer XML-Struktur Abfragen einbetten können.</span><span class="sxs-lookup"><span data-stu-id="4bb88-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="4bb88-112">Erstellen von XML-Bäumen in C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4bb88-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="4bb88-113">Zeigt, wie Sie in C# Strukturen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4bb88-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="4bb88-114">Klonen oder Anfügen (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-114">Cloning vs. Attaching (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="4bb88-115">Zeigt den Unterschied zwischen dem Hinzufügen von Knoten aus einer vorhandenen XML-Struktur (die Knoten werden geklont und dann hinzugefügt) und dem Hinzufügen von Knoten ohne übergeordnetes Element (die Knoten werden einfach angefügt).</span><span class="sxs-lookup"><span data-stu-id="4bb88-115">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="4bb88-116">Parsen von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-116">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="4bb88-117">Zeigt, wie Sie XML aus den verschiedensten Quellen analysieren können.</span><span class="sxs-lookup"><span data-stu-id="4bb88-117">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="4bb88-118"> wird über dem zum Analysieren von XML verwendeten <xref:System.Xml.XmlReader>-Objekt implementiert.</span><span class="sxs-lookup"><span data-stu-id="4bb88-118"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="4bb88-119">Vorgehensweise: Füllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-119">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="4bb88-120">Zeigt, wie Sie eine XML-Struktur mit einem <xref:System.Xml.XmlWriter> auffüllen können.</span><span class="sxs-lookup"><span data-stu-id="4bb88-120">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="4bb88-121">Vorgehensweise: Überprüfen mit XSD (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4bb88-121">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="4bb88-122">Zeigt, wie Sie eine XML-Struktur mit XSD validieren können.</span><span class="sxs-lookup"><span data-stu-id="4bb88-122">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="4bb88-123">Gültiger Inhalt von XElement- und XDocument-Objekten</span><span class="sxs-lookup"><span data-stu-id="4bb88-123">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="4bb88-124">Beschreibt die gültigen Argumente, die an Konstruktoren und Methoden übergeben werden können, mit denen Elemente und Dokumente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4bb88-124">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bb88-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bb88-125">See Also</span></span>  
 [<span data-ttu-id="4bb88-126">Programming Guide (LINQ to XML) (C#) (Programmierhandbuch (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="4bb88-126">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

