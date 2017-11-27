---
title: Serialisieren in Dateien, TextWriters und XmlWriters3
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4c5578bc20f91eb35f78355dff0fc4c44e878e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="b0da1-102">Serialisieren in Dateien, TextWriters und XmlWriters</span><span class="sxs-lookup"><span data-stu-id="b0da1-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="b0da1-103">Sie können XML-Strukturen in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b0da1-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="b0da1-104">Mit der <xref:System.Xml.Linq.XDocument>-Methode können Sie jede XML-Komponente, auch <xref:System.Xml.Linq.XElement> und `ToString`, in eine Zeichenfolge serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b0da1-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="b0da1-105">Wenn Sie beim Serialisieren in eine Zeichenfolge die Formatierung unterdrücken möchten, können Sie die <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0da1-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b0da1-106">Das Standardverhalten beim Serialisieren in eine Datei besteht darin, dass das resultierende XML-Dokument formatiert (mit Einzügen versehen) wird.</span><span class="sxs-lookup"><span data-stu-id="b0da1-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="b0da1-107">Wenn Sie das Dokument mit Einzügen versehen, wird der nicht signifikante Leerraum in der XML-Struktur nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b0da1-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="b0da1-108">Wenn Sie eine Serialisierung mit Formatierung vornehmen möchten, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> nicht als Argument akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b0da1-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="b0da1-109">Wenn Sie möchten, dass keine Einzüge vorgenommen werden und der nicht signifikante Leerraum in der XML-Struktur beibehalten wird, verwenden Sie eine der Überladungen der folgenden Methoden, die <xref:System.Xml.Linq.SaveOptions> als Argument akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="b0da1-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="b0da1-110">Beispiele finden Sie im entsprechenden Referenzthema.</span><span class="sxs-lookup"><span data-stu-id="b0da1-110">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0da1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0da1-111">See Also</span></span>  
 [<span data-ttu-id="b0da1-112">Serialisieren von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0da1-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
