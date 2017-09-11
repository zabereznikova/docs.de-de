---
title: XML-CDATA-Literal (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6bf12a5dd5b24b0a915cb15f41cb8947c33e94b0
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="51684-102">XML-CDATA-Literal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51684-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="51684-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XCData>Objekt.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="51684-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51684-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51684-104">Syntax</span></span>  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="51684-105">Teile</span><span class="sxs-lookup"><span data-stu-id="51684-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="51684-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51684-106">Required.</span></span> <span data-ttu-id="51684-107">Kennzeichnet den Anfang des XML-CDATA-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="51684-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="51684-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51684-108">Required.</span></span> <span data-ttu-id="51684-109">Der Textinhalt in einem XML-CDATA-Abschnitt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="51684-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="51684-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51684-110">Required.</span></span> <span data-ttu-id="51684-111">Kennzeichnet das Ende des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="51684-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51684-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51684-112">Return Value</span></span>  
 <span data-ttu-id="51684-113">Ein <xref:System.Xml.Linq.XCData>Objekt.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="51684-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51684-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51684-114">Remarks</span></span>  
 <span data-ttu-id="51684-115">XML-CDATA-Abschnitte enthalten unformatierten Text, der sollte enthalten, jedoch nicht analysiert werden, mit dem XML, das es enthält.</span><span class="sxs-lookup"><span data-stu-id="51684-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="51684-116">Ein XML-CDATA-Abschnitt kann Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="51684-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="51684-117">Dies schließt reservierte XML-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="51684-117">This includes reserved XML characters.</span></span> <span data-ttu-id="51684-118">XML-CDATA-Abschnitt endet mit der Sequenz "]] >".</span><span class="sxs-lookup"><span data-stu-id="51684-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="51684-119">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="51684-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="51684-120">Sie können einen eingebetteten Ausdruck in einem CDATA-literal XML verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-CDATA-Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="51684-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="51684-121">XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".</span><span class="sxs-lookup"><span data-stu-id="51684-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="51684-122">Sie können ein CDATA-literal XML einer Variablen zuweisen oder in einem XML-Elementliteral eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="51684-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51684-123">Ein XML-literal kann mehrere Zeilen umfassen, aber keine Zeilenfortsetzungszeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="51684-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="51684-124">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="51684-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="51684-125">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert XML CDATA-literal in einen Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XCData.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="51684-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51684-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51684-126">Example</span></span>  
 <span data-ttu-id="51684-127">Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "literal darf \<XML > Tags".</span><span class="sxs-lookup"><span data-stu-id="51684-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 <span data-ttu-id="51684-128">[!code-vb[VbXMLSamples&23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="51684-128">[!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51684-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51684-129">See Also</span></span>  
 <span data-ttu-id="51684-130"><xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="51684-130"><xref:System.Xml.Linq.XCData></span></span>   
<span data-ttu-id="51684-131"> [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="51684-131"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="51684-132"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="51684-132"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="51684-133"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="51684-133"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
