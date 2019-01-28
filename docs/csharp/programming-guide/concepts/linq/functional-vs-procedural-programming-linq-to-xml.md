---
title: Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: 0f45efabd0e2092325ac18c7fbf195c3338acf87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536710"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="6b9fa-102">Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6b9fa-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6b9fa-103">Es gibt viele verschiedene Arten von XML-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="6b9fa-103">There are various types of XML applications:</span></span>  
  
-   <span data-ttu-id="6b9fa-104">Einige Anwendungen produzieren auf der Basis von XML-Quelldokumenten neue XML-Dokumente, die eine andere Form als die Quelldokumente besitzen.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
-   <span data-ttu-id="6b9fa-105">Andere Anwendungen produzieren auf der Basis von XML-Quelldokumenten Ergebnisdokumente mit einem völlig anderen Format, z. B. HTML- oder CSV-Textdateien.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
-   <span data-ttu-id="6b9fa-106">Wieder andere Anwendungen nehmen XML-Quelldokumente und fügen Datensätze in eine Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
-   <span data-ttu-id="6b9fa-107">Es gibt aber auch Anwendungen, die Daten aus einer anderen Quelle, z. B. einer Datenbank, verwenden und aus ihnen XML-Dokumente erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="6b9fa-108">Dies sind immer noch nicht alle Arten von XML-Anwendungen, die es gibt, sie stehen aber stellvertretend für die verschiedenartige Funktionalität, die XML-Programmierer implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="6b9fa-109">Bei allen diesen Arten von Anwendungen kann ein Entwickler sich grundsätzlich zwischen den folgenden beiden gegensätzlichen Ansätzen entscheiden:</span><span class="sxs-lookup"><span data-stu-id="6b9fa-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
-   <span data-ttu-id="6b9fa-110">funktionale Konstruktion unter Verwendung eines deklarativen Ansatzes</span><span class="sxs-lookup"><span data-stu-id="6b9fa-110">Functional construction using a declarative approach.</span></span>  
  
-   <span data-ttu-id="6b9fa-111">XML-Strukturänderung im Arbeitsspeicher unter Verwendung prozeduralen Codes</span><span class="sxs-lookup"><span data-stu-id="6b9fa-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="6b9fa-112">LINQ to XML unterstützt beide Ansätze.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="6b9fa-113">Beim funktionalen Ansatz schreiben Sie Transformationen, die aus Quelldokumenten vollständig neue Ergebnisdokumente in der gewünschten Form generieren.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="6b9fa-114">Beim Ändern einer XML-Struktur an Ort und Stelle schreiben Sie Code, der die Knoten in einer XML-Struktur im Arbeitsspeicher durchläuft und durch sie navigiert und dabei Knoten nach Bedarf einfügt, löscht und bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="6b9fa-115">Sie können LINQ to XML für beide Ansätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="6b9fa-116">Bei beiden Ansätzen werden die gleichen Klassen und mitunter auch die gleichen Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="6b9fa-117">Der Aufbau und die Ziele der beiden Ansätze unterscheiden sich jedoch deutlich.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="6b9fa-118">Welcher Ansatz im konkreten Fall leistungsfähiger und weniger speicherintensiv ist, hängt von der jeweiligen Situation ab.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="6b9fa-119">Außerdem ist es auch von Fall zu Fall unterschiedlich, ob der Code gerade einfacher zu schreiben und besser zu unterhalten ist.</span><span class="sxs-lookup"><span data-stu-id="6b9fa-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="6b9fa-120">Eine Gegenüberstellung der beiden Ansätze finden Sie unter [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#) (Änderung der XML-Struktur im Arbeitsspeicher und funktionale Konstruktion im Vergleich (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6b9fa-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="6b9fa-121">Ein Tutorial zum Schreiben funktionaler Transformationen finden Sie unter [Pure Functional Transformations of XML (C#) (Reine funktionale XML-Transformationen (C#))](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6b9fa-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9fa-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b9fa-122">See also</span></span>

- [<span data-ttu-id="6b9fa-123">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="6b9fa-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
