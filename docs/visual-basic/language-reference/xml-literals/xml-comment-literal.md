---
title: XML-Kommentarliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 60c354215c627683fd6c69d9ca66fc115c26ccda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="813f7-102">XML-Kommentarliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="813f7-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="813f7-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XComment> Objekt.</span><span class="sxs-lookup"><span data-stu-id="813f7-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="813f7-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="813f7-105">Teile</span><span class="sxs-lookup"><span data-stu-id="813f7-105">Parts</span></span>  
  
|<span data-ttu-id="813f7-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="813f7-106">Term</span></span>|<span data-ttu-id="813f7-107">Definition</span><span class="sxs-lookup"><span data-stu-id="813f7-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="813f7-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="813f7-108">Required.</span></span> <span data-ttu-id="813f7-109">Kennzeichnet den Anfang des XML-Kommentars.</span><span class="sxs-lookup"><span data-stu-id="813f7-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="813f7-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="813f7-110">Required.</span></span> <span data-ttu-id="813f7-111">Text, der in der XML-Kommentar angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="813f7-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="813f7-112">Eine Reihe von zwei Bindestriche (-) oder das Ende mit einem Bindestrich angrenzend an das Endtag darf keine enthalten werden.</span><span class="sxs-lookup"><span data-stu-id="813f7-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="813f7-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="813f7-113">Required.</span></span> <span data-ttu-id="813f7-114">Kennzeichnet das Ende des XML-Kommentars.</span><span class="sxs-lookup"><span data-stu-id="813f7-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="813f7-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="813f7-115">Return Value</span></span>  
 <span data-ttu-id="813f7-116">Ein <xref:System.Xml.Linq.XComment>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="813f7-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="813f7-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="813f7-117">Remarks</span></span>  
 <span data-ttu-id="813f7-118">XML-Kommentarliterale enthalten keine Dokumentinhalt; Sie enthalten Informationen über das Dokument.</span><span class="sxs-lookup"><span data-stu-id="813f7-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="813f7-119">Der XML-Kommentarabschnitt endet mit der Sequenz "-->".</span><span class="sxs-lookup"><span data-stu-id="813f7-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="813f7-120">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="813f7-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="813f7-121">Sie können einen eingebetteten Ausdruck in einem XML-Kommentarliteral verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-Kommentar Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="813f7-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="813f7-122">XML-Kommentarabschnitte können nicht geschachtelt werden, da `content` darf keine enthalten den Wert "-->".</span><span class="sxs-lookup"><span data-stu-id="813f7-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="813f7-123">Sie können eine Variable einem XML-Kommentarliteral zuweisen, oder kann in einem XML-Elementliteral eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="813f7-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="813f7-124">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="813f7-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="813f7-125">Diese Funktion können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="813f7-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="813f7-126">Visual Basic-Compiler konvertiert die XML-Kommentarliteral in einen Aufruf der <xref:System.Xml.Linq.XComment.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="813f7-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="813f7-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="813f7-127">Example</span></span>  
 <span data-ttu-id="813f7-128">Das folgende Beispiel erstellt einen XML-Kommentar mit dem Text "This is einen Kommentar".</span><span class="sxs-lookup"><span data-stu-id="813f7-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="813f7-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="813f7-129">See Also</span></span>  
 <xref:System.Xml.Linq.XComment>  
 [<span data-ttu-id="813f7-130">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="813f7-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="813f7-131">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="813f7-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="813f7-132">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="813f7-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
