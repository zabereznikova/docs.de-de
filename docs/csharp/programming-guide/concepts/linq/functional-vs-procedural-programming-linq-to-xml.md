---
title: Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)
description: Für die XML-Verarbeitung unterstützt LINQ to XML prozedurale XML-Baumänderungen im Arbeitsspeicher und eine funktionale Konstruktion, die einen deklarativen Ansatz verwendet.
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e19f9311c56f4fe2c5e7e5f228aca6c03c6fe04d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103659"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="19146-103">Vergleich von funktionaler und Prozedurale Programmierung (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="19146-103">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="19146-104">Es gibt viele verschiedene Arten von XML-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="19146-104">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="19146-105">Einige Anwendungen produzieren auf der Basis von XML-Quelldokumenten neue XML-Dokumente, die eine andere Form als die Quelldokumente besitzen.</span><span class="sxs-lookup"><span data-stu-id="19146-105">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="19146-106">Andere Anwendungen produzieren auf der Basis von XML-Quelldokumenten Ergebnisdokumente mit einem völlig anderen Format, z. B. HTML- oder CSV-Textdateien.</span><span class="sxs-lookup"><span data-stu-id="19146-106">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="19146-107">Wieder andere Anwendungen nehmen XML-Quelldokumente und fügen Datensätze in eine Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="19146-107">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="19146-108">Es gibt aber auch Anwendungen, die Daten aus einer anderen Quelle, z. B. einer Datenbank, verwenden und aus ihnen XML-Dokumente erstellen.</span><span class="sxs-lookup"><span data-stu-id="19146-108">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="19146-109">Dies sind immer noch nicht alle Arten von XML-Anwendungen, die es gibt, sie stehen aber stellvertretend für die verschiedenartige Funktionalität, die XML-Programmierer implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="19146-109">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="19146-110">Bei allen diesen Arten von Anwendungen kann ein Entwickler sich grundsätzlich zwischen den folgenden beiden gegensätzlichen Ansätzen entscheiden:</span><span class="sxs-lookup"><span data-stu-id="19146-110">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="19146-111">funktionale Konstruktion unter Verwendung eines deklarativen Ansatzes</span><span class="sxs-lookup"><span data-stu-id="19146-111">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="19146-112">XML-Strukturänderung im Arbeitsspeicher unter Verwendung prozeduralen Codes</span><span class="sxs-lookup"><span data-stu-id="19146-112">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="19146-113">LINQ to XML unterstützt beide Ansätze.</span><span class="sxs-lookup"><span data-stu-id="19146-113">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="19146-114">Beim funktionalen Ansatz schreiben Sie Transformationen, die aus Quelldokumenten vollständig neue Ergebnisdokumente in der gewünschten Form generieren.</span><span class="sxs-lookup"><span data-stu-id="19146-114">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="19146-115">Beim Ändern einer XML-Struktur an Ort und Stelle schreiben Sie Code, der die Knoten in einer XML-Struktur im Arbeitsspeicher durchläuft und durch sie navigiert und dabei Knoten nach Bedarf einfügt, löscht und bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="19146-115">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="19146-116">Sie können LINQ to XML für beide Ansätze verwenden.</span><span class="sxs-lookup"><span data-stu-id="19146-116">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="19146-117">Bei beiden Ansätzen werden die gleichen Klassen und mitunter auch die gleichen Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="19146-117">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="19146-118">Der Aufbau und die Ziele der beiden Ansätze unterscheiden sich jedoch deutlich.</span><span class="sxs-lookup"><span data-stu-id="19146-118">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="19146-119">Welcher Ansatz im konkreten Fall leistungsfähiger und weniger speicherintensiv ist, hängt von der jeweiligen Situation ab.</span><span class="sxs-lookup"><span data-stu-id="19146-119">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="19146-120">Außerdem ist es auch von Fall zu Fall unterschiedlich, ob der Code gerade einfacher zu schreiben und besser zu unterhalten ist.</span><span class="sxs-lookup"><span data-stu-id="19146-120">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="19146-121">Eine Gegenüberstellung der beiden Ansätze finden Sie unter [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#) (Änderung der XML-Struktur im Arbeitsspeicher und funktionale Konstruktion im Vergleich (LINQ to XML) (C#))](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19146-121">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="19146-122">Ein Tutorial zum Schreiben funktionaler Transformationen finden Sie unter [Pure Functional Transformations of XML (C#) (Reine funktionale XML-Transformationen (C#))](./introduction-to-pure-functional-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="19146-122">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](./introduction-to-pure-functional-transformations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19146-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19146-123">See also</span></span>

- [<span data-ttu-id="19146-124">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="19146-124">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
