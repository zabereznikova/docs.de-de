---
title: 'Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 241f6552e46d7689b42a409ba44bc747984773ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647630"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="4832b-102">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4832b-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="4832b-103">Sie können erstellen [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) und füllen Sie sie mit dem Inhalt aus einer externen Quelle, z. B. eine Datei, eine Zeichenfolge oder einen Stream mithilfe mehrerer Methoden.</span><span class="sxs-lookup"><span data-stu-id="4832b-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="4832b-104">Diese Methoden werden in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4832b-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="4832b-105">Beim Laden von XML aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="4832b-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="4832b-106">Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Datei, die Verwendung der `Load` Methode.</span><span class="sxs-lookup"><span data-stu-id="4832b-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="4832b-107">Diese Methode kann einen Dateipfad, Textstream oder XML-Stream als Eingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="4832b-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="4832b-108">Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XDocument.Load%28System.String%29> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="4832b-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="4832b-109">Beim Laden von XML aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4832b-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="4832b-110">Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einer Zeichenfolge können Sie die `Parse` Methode.</span><span class="sxs-lookup"><span data-stu-id="4832b-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="4832b-111">Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4832b-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="4832b-112">Beim Laden von XML aus einem stream</span><span class="sxs-lookup"><span data-stu-id="4832b-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="4832b-113">Zum Auffüllen von einem XML-literal wie z. B. ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekt aus einem Stream, können Sie die `Load` Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="4832b-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4832b-114">Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XNode.ReadFrom%2A> Methode zum Auffüllen einer <xref:System.Xml.Linq.XDocument> Objekt mit XML aus einem XML-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="4832b-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4832b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4832b-115">See Also</span></span>  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4832b-116">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="4832b-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="4832b-117">XML</span><span class="sxs-lookup"><span data-stu-id="4832b-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="4832b-118">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4832b-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
