---
title: Serialisieren von XML-Strukturen (C#)
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
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
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
ms.openlocfilehash: f3b8ee68065a056cccbf02d96bf5f21e7ccea16b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="978bf-102">Serialisieren von XML-Strukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="978bf-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="978bf-103">Beim Serialisieren einer XML-Struktur wird aus der XML-Struktur XML generiert.</span><span class="sxs-lookup"><span data-stu-id="978bf-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="978bf-104">Eine Serialisierung kann in eine Datei, in eine konkrete Implementierung der <xref:System.IO.TextWriter>-Klasse oder in eine konkrete Implementierung eines <xref:System.Xml.XmlWriter> erfolgen.</span><span class="sxs-lookup"><span data-stu-id="978bf-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="978bf-105">Sie können verschiedene Aspekte der Serialisierung steuern.</span><span class="sxs-lookup"><span data-stu-id="978bf-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="978bf-106">So können Sie z. B. steuern, ob das serialisierte XML mit Einzügen versehen und ob eine XML-Deklaration geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="978bf-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="978bf-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="978bf-107">In This Section</span></span>  
  
|<span data-ttu-id="978bf-108">Thema</span><span class="sxs-lookup"><span data-stu-id="978bf-108">Topic</span></span>|<span data-ttu-id="978bf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="978bf-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="978bf-110">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="978bf-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="978bf-111">Beschreibt, wie Sie beim Serialisieren von XML-Strukturen das Leerraumverhalten steuern können.</span><span class="sxs-lookup"><span data-stu-id="978bf-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="978bf-112">Serialisieren mit einer XML-Deklaration (C#)</span><span class="sxs-lookup"><span data-stu-id="978bf-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="978bf-113">Beschreibt, wie Sie eine XML-Struktur serialisieren können, die eine XML-Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="978bf-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="978bf-114">Serialisieren in Dateien, TextWriters und XmlWriters</span><span class="sxs-lookup"><span data-stu-id="978bf-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="978bf-115">Beschreibt, wie Sie ein Dokument in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren können.</span><span class="sxs-lookup"><span data-stu-id="978bf-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="978bf-116">Serialisieren in einen XmlReader (XSLT aufrufen) (C#)</span><span class="sxs-lookup"><span data-stu-id="978bf-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="978bf-117">Beschreibt, wie Sie einen <xref:System.Xml.XmlReader> erstellen können, der einem anderen Modul das Lesen des Inhalts einer XML-Struktur ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="978bf-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="978bf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="978bf-118">See Also</span></span>  
 [<span data-ttu-id="978bf-119">Programming Guide (LINQ to XML) (C#) (Programmierhandbuch (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="978bf-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

