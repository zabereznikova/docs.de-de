---
title: XML-CDATA-Literal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 906fd2494dd952c08088b9b7e38dba4505780481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="96f31-102">XML-CDATA-Literal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96f31-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="96f31-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XCData> Objekt.</span><span class="sxs-lookup"><span data-stu-id="96f31-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96f31-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="96f31-105">Teile</span><span class="sxs-lookup"><span data-stu-id="96f31-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="96f31-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96f31-106">Required.</span></span> <span data-ttu-id="96f31-107">Kennzeichnet den Anfang des XML-CDATA-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="96f31-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="96f31-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96f31-108">Required.</span></span> <span data-ttu-id="96f31-109">Text-Inhalt im XML-CDATA-Abschnitt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="96f31-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="96f31-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96f31-110">Required.</span></span> <span data-ttu-id="96f31-111">Kennzeichnet das Ende des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="96f31-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96f31-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="96f31-112">Return Value</span></span>  
 <span data-ttu-id="96f31-113">Ein <xref:System.Xml.Linq.XCData>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="96f31-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96f31-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96f31-114">Remarks</span></span>  
 <span data-ttu-id="96f31-115">XML-CDATA-Abschnitte enthalten unformatierten Text, der sollten enthalten, jedoch nicht analysiert werden, mit der XML-Code, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="96f31-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="96f31-116">Ein XML-CDATA-Abschnitt kann es sich um einen beschreibenden Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="96f31-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="96f31-117">Dies schließt die folgenden reservierte XML-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="96f31-117">This includes reserved XML characters.</span></span> <span data-ttu-id="96f31-118">Die XML-CDATA-Abschnitt endet mit der Sequenz "]] >".</span><span class="sxs-lookup"><span data-stu-id="96f31-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="96f31-119">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="96f31-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="96f31-120">Sie können einen eingebetteten Ausdruck in eine XML CDATA-literal verwenden, da die Trennzeichen für eingebettete Ausdrücke gültigen XML-CDATA-Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="96f31-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="96f31-121">XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".</span><span class="sxs-lookup"><span data-stu-id="96f31-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="96f31-122">Sie können eine XML CDATA-literal kann einer Variablen zugewiesen oder in einem XML-Elementliteral eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="96f31-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96f31-123">Ein XML-literal kann mehrere Zeilen umfassen jedoch Zeilenfortsetzungszeichen nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="96f31-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="96f31-124">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="96f31-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="96f31-125">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert XML CDATA-literal in einem Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="96f31-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96f31-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96f31-126">Example</span></span>  
 <span data-ttu-id="96f31-127">Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "darf Literale \<XML > Tags".</span><span class="sxs-lookup"><span data-stu-id="96f31-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="96f31-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96f31-128">See Also</span></span>  
 <xref:System.Xml.Linq.XCData>  
 [<span data-ttu-id="96f31-129">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="96f31-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="96f31-130">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="96f31-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="96f31-131">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96f31-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
