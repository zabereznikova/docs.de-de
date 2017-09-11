---
title: Bearbeiten von XML in Visual Basic | Microsoft-Dokumentation
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62b955d78eb507aab4c786e84f3044ba54a38ebc
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="7b98e-102">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b98e-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="7b98e-103">Sie können *XML-Literale* beim Laden von XML aus einer externen Quelle wie z. B. eine Zeichenfolge, die Datei oder den Stream.</span><span class="sxs-lookup"><span data-stu-id="7b98e-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="7b98e-104">Anschließend können Sie [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] den XML-Code bearbeitet und mit [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] abgefragt.</span><span class="sxs-lookup"><span data-stu-id="7b98e-104">You can then use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b98e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7b98e-105">In This Section</span></span>  
 [<span data-ttu-id="7b98e-106">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="7b98e-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="7b98e-107">Veranschaulicht, wie beim Laden von XML in ein <xref:System.Xml.Linq.XDocument>oder <xref:System.Xml.Linq.XElement>Objekt aus einer Textdatei, die Zeichenfolge oder den Stream.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="7b98e-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="7b98e-108">Gewusst wie: Transformieren von XML unter Verwendung von LINQ</span><span class="sxs-lookup"><span data-stu-id="7b98e-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="7b98e-109">Veranschaulicht, wie der Inhalt der Transformation ein <xref:System.Xml.Linq.XDocument>Objekt in ein neues XML-Dokument.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="7b98e-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="7b98e-110">Gewusst wie: Ändern von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="7b98e-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="7b98e-111">Veranschaulicht, wie die Elemente, Attribute und Werte in einem XML-Literal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7b98e-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7b98e-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7b98e-112">Related Sections</span></span>  
 [<span data-ttu-id="7b98e-113">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7b98e-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="7b98e-114">Enthält Links zu Abschnitten, in denen die verschiedenen XML-Zugriffseigenschaften beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b98e-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="7b98e-115">Übersicht über LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b98e-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="7b98e-116">Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7b98e-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7b98e-117">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b98e-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="7b98e-118">Bietet eine Einführung zur Verwendung von XML-Literalen in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7b98e-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7b98e-119">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b98e-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="7b98e-120">Veranschaulicht, wie Teile eines XML-Elements oder Dokuments in Visual Basic zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7b98e-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7b98e-121">XML</span><span class="sxs-lookup"><span data-stu-id="7b98e-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="7b98e-122">Enthält Links zu Abschnitten, die beschreiben, wie Sie [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7b98e-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b98e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b98e-123">See Also</span></span>  
 <span data-ttu-id="7b98e-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b98e-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="7b98e-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b98e-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="7b98e-126"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="7b98e-126"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
