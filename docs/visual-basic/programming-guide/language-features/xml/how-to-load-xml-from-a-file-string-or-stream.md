---
title: 'Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054167"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="e8d02-102">Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8d02-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="e8d02-103">Sie können [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erstellen und mit den Inhalten aus einer externen Quelle, z. b. einer Datei, einer Zeichenfolge oder einem Stream, mithilfe verschiedener Methoden auffüllen.</span><span class="sxs-lookup"><span data-stu-id="e8d02-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="e8d02-104">Diese Methoden sind in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8d02-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="e8d02-105">So laden Sie XML aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="e8d02-105">To load XML from a file</span></span>

<span data-ttu-id="e8d02-106">Verwenden Sie die <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> -MethodezumAuffülleneinesXML-Literals,z.b.eines-Objektsodereines-`Load` Objekts aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="e8d02-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="e8d02-107">Diese Methode kann einen Dateipfad, einen Textstream oder einen XML-Stream als Eingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8d02-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="e8d02-108">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Load%28System.String%29> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einer Textdatei aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e8d02-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="e8d02-109">So laden Sie XML aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e8d02-109">To load XML from a string</span></span>

<span data-ttu-id="e8d02-110">Zum Auffüllen eines XML-Literals (z <xref:System.Xml.Linq.XElement> . <xref:System.Xml.Linq.XDocument> b. ein-oder-Objekt aus einer `Parse` Zeichenfolge) können Sie die-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8d02-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="e8d02-111">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einer Zeichenfolge aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e8d02-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="e8d02-112">So laden Sie XML aus einem Stream</span><span class="sxs-lookup"><span data-stu-id="e8d02-112">To load XML from a stream</span></span>

<span data-ttu-id="e8d02-113">Zum Auffüllen eines XML-Literals (z <xref:System.Xml.Linq.XElement> . <xref:System.Xml.Linq.XDocument> b. ein-oder-Objekt aus einem `Load` Stream) können <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> Sie die-Methode oder die-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8d02-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e8d02-114">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XNode.ReadFrom%2A> -Methode verwendet wird, <xref:System.Xml.Linq.XDocument> um ein-Objekt mit XML aus einem XML-Stream aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e8d02-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="e8d02-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8d02-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e8d02-116">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="e8d02-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e8d02-117">XML</span><span class="sxs-lookup"><span data-stu-id="e8d02-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="e8d02-118">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8d02-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
