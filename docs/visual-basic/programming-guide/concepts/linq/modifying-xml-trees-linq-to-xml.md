---
title: "Ändern von XML-Strukturen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ff0f95afec6248ba7f64812be5f9906c90496d9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="26680-102">Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="26680-103"> ist ein Speicher im Arbeitsspeicher, der XML-Strukturen speichert.</span><span class="sxs-lookup"><span data-stu-id="26680-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="26680-104">Nach dem Laden oder eine XML-Struktur aus einer Quelle analysieren [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie diese Struktur in ändern und anschließend serialisieren, möglicherweise in einer Datei speichern oder an einen Remoteserver senden.</span><span class="sxs-lookup"><span data-stu-id="26680-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="26680-105">Wenn Sie eine vorhandenen Struktur ändern, verwenden Sie bestimmte Methoden, z. B. <xref:System.Xml.Linq.XContainer.Add%2A>.</xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="26680-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="26680-106">Es gibt aber auch einen anderen Ansatz, nämlich die Verwendung der funktionalen Konstruktion, um eine neue Struktur mit einer anderen Form zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="26680-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="26680-107">Je nach Art der Änderungen, die Sie an Ihrer XML-Struktur vornehmen müssen, und je nach Größe der Struktur kann sich dieser Ansatz als robuster und einfacher in der Handhabung erweisen.</span><span class="sxs-lookup"><span data-stu-id="26680-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="26680-108">Das erste Thema in diesem Abschnitt enthält eine Gegenüberstellung dieser beiden Ansätze.</span><span class="sxs-lookup"><span data-stu-id="26680-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26680-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="26680-109">In This Section</span></span>  
  
|<span data-ttu-id="26680-110">Thema</span><span class="sxs-lookup"><span data-stu-id="26680-110">Topic</span></span>|<span data-ttu-id="26680-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26680-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="26680-112">Änderung des XML-Baums im Arbeitsspeicher und Funktionale Konstruktion (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="26680-113">Stellt das Ändern einer XML-Struktur im Arbeitsspeicher dem Ändern durch funktionale Konstruktion gegenüber.</span><span class="sxs-lookup"><span data-stu-id="26680-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="26680-114">Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="26680-115">Enthält Informationen zum Hinzufügen von Elementen, Attributen oder Knoten zu einer XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="26680-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="26680-116">Ändern von Elementen, Attributen und Knoten in einem XML-Baum</span><span class="sxs-lookup"><span data-stu-id="26680-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="26680-117">Enthält Informationen zum Ändern vorhandener Elemente, Attribute oder Knoten.</span><span class="sxs-lookup"><span data-stu-id="26680-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="26680-118">Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="26680-119">Enthält Informationen zum Entfernen von Elementen, Attributen oder Knoten aus einer XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="26680-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="26680-120">Verwalten von Name/Wert-Paaren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="26680-121">Beschreibt das Verwalten von Anwendungsinformationen, die am besten als Name/Wert-Paare aufbewahrt werden, wie Konfigurationsinformationen oder globale Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="26680-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="26680-122">Gewusst wie: Ändern Sie den Namespace für eine ganze XML-Struktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="26680-123">Zeigt, wie eine XML-Struktur aus einem Namespace in einen anderen Namespace verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="26680-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26680-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26680-124">See Also</span></span>  
 [<span data-ttu-id="26680-125">Programmierhandbuch (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26680-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
