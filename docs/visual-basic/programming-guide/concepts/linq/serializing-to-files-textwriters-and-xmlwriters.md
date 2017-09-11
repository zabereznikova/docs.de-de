---
title: Beim Serialisieren in Dateien, TextWriters und XmlWriters3 | Microsoft-Dokumentation
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
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
ms.openlocfilehash: f8f8672004b0704b00ff60e5b58256f664bcbd82
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="74c8a-102">Serialisieren in Dateien, TextWriters und XmlWriters</span><span class="sxs-lookup"><span data-stu-id="74c8a-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="74c8a-103">Sie können XML-Strukturen zu serialisieren einer <xref:System.IO.File>, <xref:System.IO.TextWriter>, oder eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="74c8a-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="74c8a-104">Sie können jede XML-Komponente, serialisieren einschließlich <xref:System.Xml.Linq.XDocument>und <xref:System.Xml.Linq.XElement>, in eine Zeichenfolge mit der `ToString` -Methode.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="74c8a-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="74c8a-105">Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie mithilfe der <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>-Methode.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74c8a-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="74c8a-106">Thedefault-Verhalten beim Serialisieren in eine Datei wird (Einzug) das resultierende XML-Dokument formatiert.</span><span class="sxs-lookup"><span data-stu-id="74c8a-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="74c8a-107">Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="74c8a-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="74c8a-108">Um mit Formatierung serialisieren, verwenden Sie eine der Überladungen der folgenden Methoden, die kein <xref:System.Xml.Linq.SaveOptions>als Argument:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="74c8a-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="74c8a-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74c8a-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="74c8a-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74c8a-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="74c8a-111">Wenn Sie die Option nicht für den Einzug und der nicht signifikante Leerraum in der XML-Struktur beibehalten möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die akzeptiert <xref:System.Xml.Linq.SaveOptions>als Argument:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="74c8a-111">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="74c8a-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74c8a-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="74c8a-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74c8a-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="74c8a-114">Beispiele finden Sie im entsprechenden Referenzthema.</span><span class="sxs-lookup"><span data-stu-id="74c8a-114">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c8a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c8a-115">See Also</span></span>  
 [<span data-ttu-id="74c8a-116">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74c8a-116">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
