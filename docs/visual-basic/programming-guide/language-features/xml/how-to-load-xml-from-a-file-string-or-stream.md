---
title: 'Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream (Visual Basic) | Microsoft-Dokumentation'
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
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 6361ef29b88b4a05b774cf67ca0f3832a8e214fa
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="016ab-102">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="016ab-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="016ab-103">Sie können erstellen [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) und füllen Sie sie mit dem Inhalt aus einer externen Quelle wie z. B. eine Datei, einer Zeichenfolge oder einem Stream mithilfe mehrerer Methoden.</span><span class="sxs-lookup"><span data-stu-id="016ab-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="016ab-104">Diese Methoden werden in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="016ab-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="016ab-105">Beim Laden von XML aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="016ab-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="016ab-106">Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt aus einer Datei, mit der `Load` -Methode.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="016ab-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="016ab-107">Diese Methode kann einen Dateipfad, Textstream oder XML-Stream als Eingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="016ab-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="016ab-108">Das folgende Codebeispiel zeigt die Verwendung der <xref:System.Xml.Linq.XDocument.Load%28System.String%29>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Textdatei.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="016ab-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     <span data-ttu-id="016ab-109">[!code-vb[VbXMLSamples&#43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="016ab-109">[!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]</span></span>  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="016ab-110">Beim Laden von XML aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="016ab-110">To load XML from a string</span></span>  
  
-   <span data-ttu-id="016ab-111">Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>-Objekt aus einer Zeichenfolge können Sie die `Parse` -Methode.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="016ab-111">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="016ab-112">Das folgende Codebeispiel zeigt die Verwendung der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Zeichenfolge.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-112">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     <span data-ttu-id="016ab-113">[!code-vb[VbXMLSamples&#47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="016ab-113">[!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]</span></span>  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="016ab-114">Beim Laden von XML aus einem stream</span><span class="sxs-lookup"><span data-stu-id="016ab-114">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="016ab-115">Zum Auffüllen einer XML-literal wie ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt aus einem Stream und können die `Load` Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>-Methode.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="016ab-115">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="016ab-116">Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einem XML-Stream.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="016ab-116">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 <span data-ttu-id="016ab-117">[!code-vb[VbXMLSamples&#46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="016ab-117">[!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016ab-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="016ab-118">See Also</span></span>  
 <span data-ttu-id="016ab-119"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-119"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="016ab-120"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-120"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="016ab-121"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-121"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="016ab-122"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-122"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="016ab-123"><xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="016ab-123"><xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="016ab-124"> [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="016ab-124"> [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="016ab-125"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="016ab-125"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="016ab-126"> [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="016ab-126"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span></span>

