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
ms.openlocfilehash: 999531d8146748fe491255663f0d2d17d056bcd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603833"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="4d925-102">XML-CDATA-Literal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d925-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="4d925-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XCData> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4d925-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d925-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d925-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="4d925-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4d925-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="4d925-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d925-106">Required.</span></span> <span data-ttu-id="4d925-107">Kennzeichnet den Anfang des XML-CDATA-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="4d925-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="4d925-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d925-108">Required.</span></span> <span data-ttu-id="4d925-109">Text-Inhalt im XML-CDATA-Abschnitt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d925-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="4d925-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d925-110">Required.</span></span> <span data-ttu-id="4d925-111">Kennzeichnet das Ende des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="4d925-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d925-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4d925-112">Return Value</span></span>  
 <span data-ttu-id="4d925-113">Ein <xref:System.Xml.Linq.XCData>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4d925-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d925-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d925-114">Remarks</span></span>  
 <span data-ttu-id="4d925-115">XML-CDATA-Abschnitte enthalten unformatierten Text, der sollten enthalten, jedoch nicht analysiert werden, mit der XML-Code, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="4d925-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="4d925-116">Ein XML-CDATA-Abschnitt kann es sich um einen beschreibenden Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="4d925-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="4d925-117">Dies schließt die folgenden reservierte XML-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4d925-117">This includes reserved XML characters.</span></span> <span data-ttu-id="4d925-118">Die XML-CDATA-Abschnitt endet mit der Sequenz "]] >".</span><span class="sxs-lookup"><span data-stu-id="4d925-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="4d925-119">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="4d925-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="4d925-120">Sie können einen eingebetteten Ausdruck in eine XML CDATA-literal verwenden, da die Trennzeichen für eingebettete Ausdrücke gültigen XML-CDATA-Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="4d925-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="4d925-121">XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".</span><span class="sxs-lookup"><span data-stu-id="4d925-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="4d925-122">Sie können eine XML CDATA-literal kann einer Variablen zugewiesen oder in einem XML-Elementliteral eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4d925-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d925-123">Ein XML-literal kann mehrere Zeilen umfassen jedoch Zeilenfortsetzungszeichen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d925-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="4d925-124">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="4d925-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4d925-125">Visual Basic-Compiler konvertiert XML CDATA-literal in einem Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="4d925-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d925-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d925-126">Example</span></span>  
 <span data-ttu-id="4d925-127">Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "darf Literale \<XML > Tags".</span><span class="sxs-lookup"><span data-stu-id="4d925-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d925-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d925-128">See Also</span></span>  
 <xref:System.Xml.Linq.XCData>  
 [<span data-ttu-id="4d925-129">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="4d925-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="4d925-130">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="4d925-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="4d925-131">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d925-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
