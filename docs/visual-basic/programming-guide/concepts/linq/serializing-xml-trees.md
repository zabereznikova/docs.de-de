---
title: Serialisieren von XML-Strukturen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
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
ms.openlocfilehash: a63e875b1c1391ec1bb2b0ae64be9f9cff28d87d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="886f1-102">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="886f1-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="886f1-103">Beim Serialisieren einer XML-Struktur wird aus der XML-Struktur XML generiert.</span><span class="sxs-lookup"><span data-stu-id="886f1-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="886f1-104">Serialisierung kann in eine Datei, in eine konkrete Implementierung der <xref:System.IO.TextWriter>-Klasse oder in eine konkrete Implementierung einer <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="886f1-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="886f1-105">Sie können verschiedene Aspekte der Serialisierung steuern.</span><span class="sxs-lookup"><span data-stu-id="886f1-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="886f1-106">So können Sie z. B. steuern, ob das serialisierte XML mit Einzügen versehen und ob eine XML-Deklaration geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="886f1-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="886f1-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="886f1-107">In This Section</span></span>  
  
|<span data-ttu-id="886f1-108">Thema</span><span class="sxs-lookup"><span data-stu-id="886f1-108">Topic</span></span>|<span data-ttu-id="886f1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="886f1-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="886f1-110">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="886f1-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="886f1-111">Beschreibt, wie Sie beim Serialisieren von XML-Strukturen das Leerraumverhalten steuern können.</span><span class="sxs-lookup"><span data-stu-id="886f1-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="886f1-112">Serialisieren mit einer XML-Deklaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="886f1-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="886f1-113">Beschreibt, wie Sie eine XML-Struktur serialisieren können, die eine XML-Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="886f1-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="886f1-114">Serialisieren in Dateien, TextWriters und XmlWriters</span><span class="sxs-lookup"><span data-stu-id="886f1-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="886f1-115">Beschreibt, wie Sie ein Dokument zum Serialisieren einer <xref:System.IO.File>, <xref:System.IO.TextWriter>, oder eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="886f1-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="886f1-116">Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="886f1-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="886f1-117">Beschreibt das Erstellen einer <xref:System.Xml.XmlReader>, mit der ein anderes Modul zum Lesen des Inhalts einer XML-Struktur.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="886f1-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="886f1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="886f1-118">See Also</span></span>  
 [<span data-ttu-id="886f1-119">Programmierhandbuch (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="886f1-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
