---
title: Zugreifen auf XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386459"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="211b3-102">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="211b3-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="211b3-103">Visual Basic bietet XML-Achseneigenschaften für den Zugriff auf und die berichtsnavigation [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Strukturen.</span><span class="sxs-lookup"><span data-stu-id="211b3-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="211b3-104">Diese Eigenschaften verwenden eine spezielle Syntax, um Elemente und Attribute zugreifen, indem Sie die XML-Namen angeben können.</span><span class="sxs-lookup"><span data-stu-id="211b3-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="211b3-105">Die folgende Tabelle enthält die Sprachfunktionen, die Ihnen den Zugriff auf XML-Elemente und Attribute in Visual Basic ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="211b3-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="211b3-106">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="211b3-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="211b3-107">Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="211b3-107">Property description</span></span>|<span data-ttu-id="211b3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="211b3-108">Example</span></span>|<span data-ttu-id="211b3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="211b3-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="211b3-110">*Child-Achse*</span><span class="sxs-lookup"><span data-stu-id="211b3-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="211b3-111">Ruft alle `phone` Elemente, die untergeordneten Elemente sind die `contact` Element.</span><span class="sxs-lookup"><span data-stu-id="211b3-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="211b3-112">*Attribute-Achse*</span><span class="sxs-lookup"><span data-stu-id="211b3-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="211b3-113">Ruft alle `type` Attribute der `phone` Element.</span><span class="sxs-lookup"><span data-stu-id="211b3-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="211b3-114">*descendant-Achse*</span><span class="sxs-lookup"><span data-stu-id="211b3-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="211b3-115">Ruft alle `name` Bestandteile der `contacts` Element, unabhängig davon, wie viele Ebenen in der Hierarchie, die sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="211b3-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="211b3-116">*erweiterungsindizierer*</span><span class="sxs-lookup"><span data-stu-id="211b3-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="211b3-117">Ruft das erste `name` Element aus der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="211b3-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="211b3-118">*Wert*</span><span class="sxs-lookup"><span data-stu-id="211b3-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="211b3-119">Ruft eine Zeichenfolgendarstellung des ersten Objekts in der Sequenz oder `Nothing` , wenn die Sequenz leer ist.</span><span class="sxs-lookup"><span data-stu-id="211b3-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="211b3-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="211b3-120">In This Section</span></span>  
 [<span data-ttu-id="211b3-121">Gewusst wie: Zugreifen auf XML-Nachfolgerelemente</span><span class="sxs-lookup"><span data-stu-id="211b3-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="211b3-122">Zeigt, wie für eine descendant-Achse-Eigenschaft den Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und unter einem angegebenen XML-Element enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="211b3-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="211b3-123">Gewusst wie: Zugreifen auf untergeordnete XML-Elemente</span><span class="sxs-lookup"><span data-stu-id="211b3-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="211b3-124">Veranschaulicht, wie einer untergeordneten Achseneigenschaft auf alle untergeordneten XML-Elemente, die einen angegebenen Namen in ein XML-Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="211b3-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="211b3-125">Gewusst wie: Zugreifen auf XML-Attribute</span><span class="sxs-lookup"><span data-stu-id="211b3-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="211b3-126">Veranschaulicht, wie ein Attributachseneigenschaft zu verwenden, um alle XML-Attribute zuzugreifen, die einen angegebenen Namen in ein XML-Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="211b3-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="211b3-127">Gewusst wie: Deklarieren und Verwenden von XML-Namespacepräfixen</span><span class="sxs-lookup"><span data-stu-id="211b3-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="211b3-128">Zeigt, wie ein XML-Namespacepräfix zu deklarieren und zu erstellen und Zugreifen auf XML-Elemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="211b3-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="211b3-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="211b3-129">Related Sections</span></span>  
 [<span data-ttu-id="211b3-130">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="211b3-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="211b3-131">Enthält Links zu Abschnitten beschreiben die verschiedenen Eigenschaften der XML-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="211b3-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="211b3-132">Übersicht über LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="211b3-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="211b3-133">Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="211b3-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="211b3-134">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="211b3-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="211b3-135">Bietet eine Einführung in die Verwendung von XML-Literale in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="211b3-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="211b3-136">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="211b3-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="211b3-137">Enthält Links zu Abschnitten zum Laden und Ändern von XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="211b3-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="211b3-138">XML</span><span class="sxs-lookup"><span data-stu-id="211b3-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="211b3-139">Enthält Links zu Abschnitten, die beschreibt, wie mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="211b3-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
