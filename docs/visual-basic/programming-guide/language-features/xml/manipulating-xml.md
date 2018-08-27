---
title: Bearbeiten von XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 7fd111f5e885de3389b8f93002db22b48c4edd45
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931103"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="15964-102">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15964-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="15964-103">Sie können *XML-Literale* beim Laden von XML aus einer externen Quelle wie z. B. eine Zeichenfolge, die Datei oder den Stream.</span><span class="sxs-lookup"><span data-stu-id="15964-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="15964-104">Anschließend können Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] den XML-Code zu verändern und verwenden [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] zum Abfragen des XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="15964-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15964-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="15964-105">In This Section</span></span>  
 [<span data-ttu-id="15964-106">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="15964-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="15964-107">Veranschaulicht, wie beim Laden von XML in eine <xref:System.Xml.Linq.XDocument> oder <xref:System.Xml.Linq.XElement> Objekt aus einer Textdatei, die Zeichenfolge oder den Stream.</span><span class="sxs-lookup"><span data-stu-id="15964-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="15964-108">Gewusst wie: Transformieren von XML unter Verwendung von LINQ</span><span class="sxs-lookup"><span data-stu-id="15964-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="15964-109">Veranschaulicht, wie der Inhalt der Transformation ein <xref:System.Xml.Linq.XDocument> Objekt in ein neues XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="15964-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="15964-110">Gewusst wie: Ändern von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="15964-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="15964-111">Veranschaulicht, wie die Elemente, Attribute und Werte in ein XML-Literal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="15964-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15964-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="15964-112">Related Sections</span></span>  
 [<span data-ttu-id="15964-113">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="15964-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="15964-114">Enthält Links zu Abschnitten, die die verschiedenen Eigenschaften der XML-Zugriff zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="15964-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="15964-115">Übersicht über LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15964-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="15964-116">Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15964-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="15964-117">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15964-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="15964-118">Bietet eine Einführung in die Verwendung von XML-Literale in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15964-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="15964-119">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15964-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="15964-120">Veranschaulicht, wie Teile eines XML-Elements oder Dokuments in Visual Basic den Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="15964-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="15964-121">XML</span><span class="sxs-lookup"><span data-stu-id="15964-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="15964-122">Enthält Links zu Abschnitten, die beschreiben, wie Sie mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15964-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15964-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15964-123">See Also</span></span>  
 [<span data-ttu-id="15964-124">XML</span><span class="sxs-lookup"><span data-stu-id="15964-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="15964-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="15964-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="15964-126">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15964-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
