---
title: Beibehaltung von Leerraum beim Laden oder analysieren XML2 | Microsoft-Dokumentation
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2872c1e2354c0a0bd106f7fb945542ce37e7774
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="d6185-102">Beibehalten von Leerzeichen beim Laden oder Parsen von XML</span><span class="sxs-lookup"><span data-stu-id="d6185-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="d6185-103">In diesem Thema wird beschrieben, wie das Leerraumverhalten von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6185-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="d6185-104">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6185-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="d6185-105">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="d6185-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="d6185-106">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6185-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="d6185-107">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="d6185-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="d6185-108">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d6185-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="d6185-109">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6185-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="d6185-110">In diesem Thema wird das Leerraumverhalten von Methoden beschrieben, die XML-Strukturen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="d6185-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="d6185-111">Informationen zum Steuern des Leerraumverhaltens beim Serialisieren von XML-Strukturen finden Sie unter [beibehalten Leerzeichen beim Serialisieren von](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="d6185-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="d6185-112">Verhalten von Methoden, die XML-Strukturen auffüllen</span><span class="sxs-lookup"><span data-stu-id="d6185-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="d6185-113">Die folgenden Methoden in der <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>Klassen eine XML-Struktur aufzufüllen.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d6185-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="d6185-114">Sie können eine XML-Struktur aus einer Datei, Auffüllen einer <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, oder eine Zeichenfolge:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="d6185-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <span data-ttu-id="d6185-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6185-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="d6185-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6185-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="d6185-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6185-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="d6185-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6185-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="d6185-119">Wenn die Methode nicht <xref:System.Xml.Linq.LoadOptions>als Argument wird die Methode nicht signifikanten Leerraum nicht beibehalten.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="d6185-119">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="d6185-120">In den meisten Fällen, wenn die Methode akzeptiert <xref:System.Xml.Linq.LoadOptions>als Argument können Sie optional nicht signifikanten Leerraum als Textknoten in der XML-Struktur erhalten.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="d6185-120">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="d6185-121">Allerdings, wenn die Methode lädt das XML aus einer <xref:System.Xml.XmlReader>, die <xref:System.Xml.XmlReader>bestimmt, ob Leerraum oder nicht beibehalten wird.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d6185-121">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="d6185-122">Festlegen von <xref:System.Xml.Linq.LoadOptions>hat keine Auswirkung.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="d6185-122">Setting <xref:System.Xml.Linq.LoadOptions> will have no effect.</span></span>  
  
 <span data-ttu-id="d6185-123">Mit diesen Methoden, sofern Leerraum beibehalten wird nicht signifikanter Leerraum eingefügt wird die XML-Struktur als <xref:System.Xml.Linq.XText>Knoten.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="d6185-123">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="d6185-124">Wenn Leerraum nicht beibehalten wird, erfolgt keine Einfügung von Textknoten.</span><span class="sxs-lookup"><span data-stu-id="d6185-124">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="d6185-125">Sie können eine XML-Struktur erstellen, mit einer <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="d6185-125">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="d6185-126">Knoten, die geschrieben werden die <xref:System.Xml.XmlWriter>werden in der Struktur aufgefüllt.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="d6185-126">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="d6185-127">Wenn Sie jedoch eine XML-Struktur mit dieser Methode erstellen, bleiben alle Knoten unabhängig davon erhalten, ob der Knoten Leerraum ist und ob er signifikant ist.</span><span class="sxs-lookup"><span data-stu-id="d6185-127">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6185-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6185-128">See Also</span></span>  
 [<span data-ttu-id="d6185-129">Analysieren von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6185-129">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
