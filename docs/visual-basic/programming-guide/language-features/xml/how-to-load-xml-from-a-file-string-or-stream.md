---
title: 'Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330962"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="d4e66-102">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4e66-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="d4e66-103">Sie können [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md) erstellen und mit den Inhalten aus einer externen Quelle, z. b. einer Datei, einer Zeichenfolge oder einem Stream, mithilfe verschiedener Methoden auffüllen.</span><span class="sxs-lookup"><span data-stu-id="d4e66-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="d4e66-104">Diese Methoden sind in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4e66-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="d4e66-105">So laden Sie XML aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="d4e66-105">To load XML from a file</span></span>

<span data-ttu-id="d4e66-106">Verwenden Sie zum Auffüllen eines XML-Literals, z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einer Datei, die `Load`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d4e66-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="d4e66-107">Diese Methode kann einen Dateipfad, einen Textstream oder einen XML-Stream als Eingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4e66-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="d4e66-108">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Load%28System.String%29>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Textdatei aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="d4e66-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="d4e66-109">So laden Sie XML aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d4e66-109">To load XML from a string</span></span>

<span data-ttu-id="d4e66-110">Zum Auffüllen eines XML-Literals (z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einer Zeichenfolge) können Sie die `Parse`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4e66-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="d4e66-111">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einer Zeichenfolge aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="d4e66-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="d4e66-112">So laden Sie XML aus einem Stream</span><span class="sxs-lookup"><span data-stu-id="d4e66-112">To load XML from a stream</span></span>

<span data-ttu-id="d4e66-113">Zum Auffüllen eines XML-Literals (z. b. eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekts aus einem Stream) können Sie die `Load`-Methode oder die <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4e66-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d4e66-114">Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode verwendet wird, um ein <xref:System.Xml.Linq.XDocument>-Objekt mit XML aus einem XML-Stream aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="d4e66-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="d4e66-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4e66-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d4e66-116">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="d4e66-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d4e66-117">XML</span><span class="sxs-lookup"><span data-stu-id="d4e66-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="d4e66-118">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4e66-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
