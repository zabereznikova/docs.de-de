---
title: XML-CDATA-Literal
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 4447ad6cf0fb251b0d2d1387c109b06d32f69cb8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866096"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="0ea93-102">XML-CDATA-Literal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ea93-102">XML CDATA Literal (Visual Basic)</span></span>

<span data-ttu-id="0ea93-103">Ein Literalwert, der ein <xref:System.Xml.Linq.XCData> Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ea93-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ea93-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="0ea93-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0ea93-105">Parts</span></span>  

 `<![CDATA[`  
 <span data-ttu-id="0ea93-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0ea93-106">Required.</span></span> <span data-ttu-id="0ea93-107">Bezeichnet den Anfang des XML-CDATA-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="0ea93-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="0ea93-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0ea93-108">Required.</span></span> <span data-ttu-id="0ea93-109">Text Inhalt, der im XML-CDATA-Abschnitt angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ea93-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="0ea93-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0ea93-110">Required.</span></span> <span data-ttu-id="0ea93-111">Bezeichnet das Ende des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="0ea93-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ea93-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ea93-112">Return Value</span></span>  

 <span data-ttu-id="0ea93-113">Ein <xref:System.Xml.Linq.XCData>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="0ea93-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ea93-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0ea93-114">Remarks</span></span>  

 <span data-ttu-id="0ea93-115">XML-CDATA-Abschnitte enthalten Rohtext, der eingeschlossen, aber nicht analysiert werden soll, mit dem XML-Code, der ihn enthält.</span><span class="sxs-lookup"><span data-stu-id="0ea93-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="0ea93-116">Ein XML-CDATA-Abschnitt kann beliebigen Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ea93-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="0ea93-117">Dies schließt reservierte XML-Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="0ea93-117">This includes reserved XML characters.</span></span> <span data-ttu-id="0ea93-118">Der XML-CDATA-Abschnitt endet mit der Sequenz "]] >".</span><span class="sxs-lookup"><span data-stu-id="0ea93-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="0ea93-119">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="0ea93-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="0ea93-120">Sie können keinen eingebetteten Ausdruck in einem XML-CDATA-Literalformat verwenden, da die eingebetteten Ausdrucks Trennzeichen gültige XML-CDATA-Inhalte sind.</span><span class="sxs-lookup"><span data-stu-id="0ea93-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="0ea93-121">XML-CDATA-Abschnitte können nicht eingebettet werden, da `content` den Wert "]] >" nicht enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="0ea93-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="0ea93-122">Sie können eine XML-CDATA-Literale einer Variablen zuweisen oder in ein XML-Elementliteral einschließen.</span><span class="sxs-lookup"><span data-stu-id="0ea93-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ea93-123">XML-Literale können sich über mehrere Zeilen erstrecken, verwenden jedoch keine Zeilen Fortsetzungs Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0ea93-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="0ea93-124">Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.</span><span class="sxs-lookup"><span data-stu-id="0ea93-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="0ea93-125">Der Visual Basic Compiler konvertiert das XML-CDATA-Literale in einen- <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor-Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="0ea93-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ea93-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ea93-126">Example</span></span>  

 <span data-ttu-id="0ea93-127">Im folgenden Beispiel wird ein CDATA-Abschnitt erstellt, der den Text "kann \<XML> literaltags enthalten" enthält.</span><span class="sxs-lookup"><span data-stu-id="0ea93-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="0ea93-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ea93-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="0ea93-129">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="0ea93-129">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="0ea93-130">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="0ea93-130">XML Literals</span></span>](index.md)
- [<span data-ttu-id="0ea93-131">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ea93-131">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
