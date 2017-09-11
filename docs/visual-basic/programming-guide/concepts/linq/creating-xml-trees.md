---
title: Erstellen von XML-Strukturen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: e86ba12b-17de-4579-81bb-66322b84cfbe
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c60746a3da6255e4c245febf55151b41186a75b7
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-trees-visual-basic"></a><span data-ttu-id="b83ac-102">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-102">Creating XML Trees (Visual Basic)</span></span>
<span data-ttu-id="b83ac-103">Eine der häufigsten XML-Aufgaben besteht darin, eine XML-Struktur zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="b83ac-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="b83ac-104">In diesem Abschnitt werden mehrere Möglichkeiten für die Erstellung solcher Strukturen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b83ac-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b83ac-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b83ac-105">In This Section</span></span>  
  
|<span data-ttu-id="b83ac-106">Thema</span><span class="sxs-lookup"><span data-stu-id="b83ac-106">Topic</span></span>|<span data-ttu-id="b83ac-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b83ac-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b83ac-108">Funktionale Konstruktion (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-108">Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="b83ac-109">Enthält eine Übersicht über die funktionale Konstruktion in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b83ac-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="b83ac-110">Die funktionale Konstruktion ermöglicht es Ihnen, Ihre XML-Struktur ganz oder teilweise in einer einzigen Anweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b83ac-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="b83ac-111">In diesem Thema wird außerdem gezeigt, wie Sie beim Konstruieren einer XML-Struktur Abfragen einbetten können.</span><span class="sxs-lookup"><span data-stu-id="b83ac-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="b83ac-112">Einführung in XML-Literalen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b83ac-112">Introduction to XML Literals in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)|<span data-ttu-id="b83ac-113">Bietet eine kurze Einführung in das Erstellen von Strukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mithilfe von XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="b83ac-113">Provides a quick introduction to creating trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using XML literals.</span></span> <span data-ttu-id="b83ac-114">Dieses Thema enthält Links zur [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Dokumentation zu XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="b83ac-114">This topic includes links to the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] documentation of XML literals.</span></span>|  
|[<span data-ttu-id="b83ac-115">Klonen oder Anfügen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-115">Cloning vs. Attaching (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="b83ac-116">Zeigt den Unterschied zwischen dem Hinzufügen von Knoten aus einer vorhandenen XML-Struktur (die Knoten werden geklont und dann hinzugefügt) und dem Hinzufügen von Knoten ohne übergeordnetes Element (die Knoten werden einfach angefügt).</span><span class="sxs-lookup"><span data-stu-id="b83ac-116">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="b83ac-117">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-117">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="b83ac-118">Zeigt, wie Sie XML aus den verschiedensten Quellen analysieren können.</span><span class="sxs-lookup"><span data-stu-id="b83ac-118">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b83ac-119">besteht aus mehreren Ebenen auf der Basis von <xref:System.Xml.XmlReader>, der zum Analysieren der XML verwendet wird.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="b83ac-119"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="b83ac-120">Gewusst wie: Auffüllen einer XML-Struktur mit einem XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-120">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="b83ac-121">Zeigt, wie eine XML-Struktur mit einem <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> aufgefüllt</span><span class="sxs-lookup"><span data-stu-id="b83ac-121">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="b83ac-122">Gewusst wie: Überprüfen mit XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-122">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="b83ac-123">Zeigt, wie Sie eine XML-Struktur mit XSD validieren können.</span><span class="sxs-lookup"><span data-stu-id="b83ac-123">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="b83ac-124">Gültiger Inhalt von XElement- und XDocument-Objekten</span><span class="sxs-lookup"><span data-stu-id="b83ac-124">Valid Content of XElement and XDocument Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects.md)|<span data-ttu-id="b83ac-125">Beschreibt die gültigen Argumente, die an Konstruktoren und Methoden übergeben werden können, mit denen Elemente und Dokumente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b83ac-125">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b83ac-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b83ac-126">See Also</span></span>  
 [<span data-ttu-id="b83ac-127">Programmierhandbuch (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b83ac-127">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
