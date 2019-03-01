---
title: XML-CDATA-Literal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981243"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="789f3-102">XML-CDATA-Literal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="789f3-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="789f3-103">Ein Zeichenfolgenliteral, ein <xref:System.Xml.Linq.XCData> Objekt.</span><span class="sxs-lookup"><span data-stu-id="789f3-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="789f3-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="789f3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="789f3-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="789f3-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="789f3-106">Required.</span></span> <span data-ttu-id="789f3-107">Kennzeichnet den Anfang des XML-CDATA-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="789f3-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="789f3-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="789f3-108">Required.</span></span> <span data-ttu-id="789f3-109">Der Textinhalt in einem XML-CDATA-Abschnitt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="789f3-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="789f3-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="789f3-110">Required.</span></span> <span data-ttu-id="789f3-111">Kennzeichnet das Ende des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="789f3-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="789f3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="789f3-112">Return Value</span></span>  
 <span data-ttu-id="789f3-113">Ein <xref:System.Xml.Linq.XCData>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="789f3-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="789f3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="789f3-114">Remarks</span></span>  
 <span data-ttu-id="789f3-115">XML-CDATA-Abschnitten enthalten die unformatierten Text, der sollten enthalten, aber nicht analysiert werden, mit dem XML, das es enthält.</span><span class="sxs-lookup"><span data-stu-id="789f3-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="789f3-116">Ein XML-CDATA-Abschnitt kann es sich um einen beliebigen Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="789f3-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="789f3-117">Dies schließt die reservierte XML-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="789f3-117">This includes reserved XML characters.</span></span> <span data-ttu-id="789f3-118">Die XML-CDATA-Abschnitt endet mit der Sequenz "]] >".</span><span class="sxs-lookup"><span data-stu-id="789f3-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="789f3-119">Dies bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="789f3-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="789f3-120">Sie können keinen eingebetteten Ausdruck in eine XML CDATA-literal verwenden, da die Trennzeichen für eingebettete Ausdrücke gültige XML-CDATA-Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="789f3-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="789f3-121">XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".</span><span class="sxs-lookup"><span data-stu-id="789f3-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="789f3-122">Sie können eine XML CDATA-literal einer Variablen zuweisen oder in einem XML-Elementliteral einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="789f3-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="789f3-123">Ein XML-literal kann mehrere Zeilen umfassen, aber keine Zeilenfortsetzungszeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="789f3-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="789f3-124">Dadurch können Sie zum Kopieren von Inhalt aus einem XML-Dokument, und fügen ihn direkt in Visual Basic-Programms.</span><span class="sxs-lookup"><span data-stu-id="789f3-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="789f3-125">Visual Basic-Compiler konvertiert XML CDATA-literal in einem Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="789f3-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="789f3-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="789f3-126">Example</span></span>  
 <span data-ttu-id="789f3-127">Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "darf Literale \<XML > Tags".</span><span class="sxs-lookup"><span data-stu-id="789f3-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="789f3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="789f3-128">See also</span></span>
- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="789f3-129">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="789f3-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="789f3-130">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="789f3-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="789f3-131">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="789f3-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
