---
title: XML-Kommentarliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 3272cc0f976d6e8819e51bb5d5fce73066007963
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875189"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="99685-102">XML-Kommentarliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99685-102">XML Comment Literal (Visual Basic)</span></span>

<span data-ttu-id="99685-103">Ein Literalwert, der ein <xref:System.Xml.Linq.XComment> Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="99685-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99685-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99685-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="99685-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="99685-105">Parts</span></span>  
  
|<span data-ttu-id="99685-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="99685-106">Term</span></span>|<span data-ttu-id="99685-107">Definition</span><span class="sxs-lookup"><span data-stu-id="99685-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="99685-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99685-108">Required.</span></span> <span data-ttu-id="99685-109">Gibt den Anfang des XML-Kommentars an.</span><span class="sxs-lookup"><span data-stu-id="99685-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="99685-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99685-110">Required.</span></span> <span data-ttu-id="99685-111">Text, der im XML-Kommentar angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="99685-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="99685-112">Kann keine Reihe von zwei Bindestrichen (--) enthalten oder auf einen Bindestrich neben dem schließenden Tag enden.</span><span class="sxs-lookup"><span data-stu-id="99685-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="99685-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99685-113">Required.</span></span> <span data-ttu-id="99685-114">Bezeichnet das Ende des XML-Kommentars.</span><span class="sxs-lookup"><span data-stu-id="99685-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="99685-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99685-115">Return Value</span></span>  

 <span data-ttu-id="99685-116">Ein <xref:System.Xml.Linq.XComment>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="99685-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99685-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="99685-117">Remarks</span></span>  

 <span data-ttu-id="99685-118">XML-Kommentar Literale enthalten keinen Dokumentinhalt. Sie enthalten Informationen über das Dokument.</span><span class="sxs-lookup"><span data-stu-id="99685-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="99685-119">Der XML-Kommentar Abschnitt endet mit der Sequenz "-->".</span><span class="sxs-lookup"><span data-stu-id="99685-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="99685-120">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="99685-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="99685-121">Ein eingebetteter Ausdruck kann nicht in einem XML-kommentarliteralausdruck verwendet werden, da die eingebetteten Ausdrucks Trennzeichen gültige XML-Kommentar Inhalte sind.</span><span class="sxs-lookup"><span data-stu-id="99685-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="99685-122">XML-Kommentar Abschnitte können nicht eingebettet werden, da `content` den Wert "-->" nicht enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="99685-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="99685-123">Sie können einer Variablen einen XML-Kommentarliterals zuweisen, oder Sie können Sie in ein XML-Elementliteral einschließen.</span><span class="sxs-lookup"><span data-stu-id="99685-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99685-124">Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="99685-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="99685-125">Mit dieser Funktion können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.</span><span class="sxs-lookup"><span data-stu-id="99685-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="99685-126">Der Visual Basic Compiler konvertiert das XML-kommentarliteralzeichen in einen- <xref:System.Xml.Linq.XComment.%23ctor%2A> Konstruktor-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="99685-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99685-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99685-127">Example</span></span>  

 <span data-ttu-id="99685-128">Im folgenden Beispiel wird ein XML-Kommentar erstellt, der den Text "This is a comment" enthält.</span><span class="sxs-lookup"><span data-stu-id="99685-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="99685-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99685-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="99685-130">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="99685-130">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="99685-131">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="99685-131">XML Literals</span></span>](index.md)
- [<span data-ttu-id="99685-132">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99685-132">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
