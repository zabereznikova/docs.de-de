---
title: "Beibehaltung von Leerraum während Serializing2 | Microsoft-Dokumentation"
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
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
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
ms.openlocfilehash: de06e1a5a217644a2eae99f8c7752ee780594d22
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="901c5-102">Beibehalten von Leerzeichen beim Serialisieren</span><span class="sxs-lookup"><span data-stu-id="901c5-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="901c5-103">In diesem Thema wird beschrieben, wie Sie das Leerraumverhalten beim Serialisieren von XML-Strukturen steuern können.</span><span class="sxs-lookup"><span data-stu-id="901c5-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="901c5-104">Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="901c5-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="901c5-105">Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten.</span><span class="sxs-lookup"><span data-stu-id="901c5-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="901c5-106">Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="901c5-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="901c5-107">Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert.</span><span class="sxs-lookup"><span data-stu-id="901c5-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="901c5-108">Sie möchten nicht, dass diese Einzüge irgendwie geändert werden.</span><span class="sxs-lookup"><span data-stu-id="901c5-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="901c5-109">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="901c5-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="901c5-110">Leerraumverhalten von Methoden, die XML-Strukturen serialisieren</span><span class="sxs-lookup"><span data-stu-id="901c5-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="901c5-111">Die folgenden Methoden in der <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>serialisieren eine XML-Struktur von Klassen.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="901c5-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="901c5-112">Sie können eine XML-Struktur in einer Datei Serialisieren einer <xref:System.IO.TextReader>, oder eine <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="901c5-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="901c5-113">Die `ToString`-Methode nimmt eine Serialisierung in eine Zeichenfolge vor.</span><span class="sxs-lookup"><span data-stu-id="901c5-113">The `ToString` method serializes to a string.</span></span>  
  
-   <span data-ttu-id="901c5-114"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="901c5-114"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="901c5-115"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="901c5-115"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="901c5-116"><xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="901c5-116"><xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="901c5-117"><xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="901c5-117"><xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="901c5-118">Wenn die Methode nicht <xref:System.Xml.Linq.SaveOptions>als Argument, dann formatiert die Methode den serialisierten XML (Einzug).</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="901c5-118">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="901c5-119">In diesem Fall wird der gesamte nicht signifikante Leerraum in der XML-Struktur verworfen.</span><span class="sxs-lookup"><span data-stu-id="901c5-119">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="901c5-120">Wenn die Methode akzeptiert <xref:System.Xml.Linq.SaveOptions>als Argument können Sie angeben, dass die Methode nicht formatiert (eingerückt) das serialisierte XML.</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="901c5-120">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="901c5-121">In diesem Fall wird der gesamte Leerraum in der XML-Struktur beibehalten.</span><span class="sxs-lookup"><span data-stu-id="901c5-121">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901c5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="901c5-122">See Also</span></span>  
 [<span data-ttu-id="901c5-123">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="901c5-123">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
