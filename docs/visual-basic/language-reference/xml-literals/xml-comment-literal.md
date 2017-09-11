---
title: XML-Kommentarliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
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
ms.openlocfilehash: ab896399b664c658710c24d9799218ff3d81aecc
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="b797b-102">XML-Kommentarliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b797b-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="b797b-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XComment>Objekt.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="b797b-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b797b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b797b-104">Syntax</span></span>  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="b797b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b797b-105">Parts</span></span>  
  
|<span data-ttu-id="b797b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b797b-106">Term</span></span>|<span data-ttu-id="b797b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b797b-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="b797b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b797b-108">Required.</span></span> <span data-ttu-id="b797b-109">Kennzeichnet den Anfang des XML-Kommentars.</span><span class="sxs-lookup"><span data-stu-id="b797b-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="b797b-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b797b-110">Required.</span></span> <span data-ttu-id="b797b-111">Text, der in der XML-Kommentar angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b797b-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="b797b-112">Dürfen keine Reihe von zwei Bindestriche (-) oder mit einem neben dem Endtag ein Bindestrich enden.</span><span class="sxs-lookup"><span data-stu-id="b797b-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="b797b-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b797b-113">Required.</span></span> <span data-ttu-id="b797b-114">Kennzeichnet das Ende des XML-Kommentars.</span><span class="sxs-lookup"><span data-stu-id="b797b-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="b797b-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b797b-115">Return Value</span></span>  
 <span data-ttu-id="b797b-116">Ein <xref:System.Xml.Linq.XComment>Objekt.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="b797b-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b797b-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b797b-117">Remarks</span></span>  
 <span data-ttu-id="b797b-118">XML-Kommentarliterale enthalten keine Dokumentinhalt; Sie enthalten Informationen über das Dokument.</span><span class="sxs-lookup"><span data-stu-id="b797b-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="b797b-119">Der XML-Kommentarabschnitt endet mit der Sequenz "-->".</span><span class="sxs-lookup"><span data-stu-id="b797b-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="b797b-120">Dies impliziert die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="b797b-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="b797b-121">Sie können einen eingebetteten Ausdruck in einem XML-Kommentarliteral verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-Kommentar Inhalt sind.</span><span class="sxs-lookup"><span data-stu-id="b797b-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="b797b-122">XML-Kommentarabschnitte können nicht geschachtelt werden, da `content` kann nicht den Wert "-->" enthalten.</span><span class="sxs-lookup"><span data-stu-id="b797b-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="b797b-123">Sie können eine Variable ein XML-Kommentarliteral zuweisen, oder in einem XML-Elementliteral eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b797b-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b797b-124">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="b797b-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="b797b-125">Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und Einfügen direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="b797b-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="b797b-126">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Kommentarliteral in einen Aufruf der <xref:System.Xml.Linq.XComment.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XComment.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="b797b-126">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b797b-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b797b-127">Example</span></span>  
 <span data-ttu-id="b797b-128">Das folgende Beispiel erstellt einen XML-Kommentar mit dem Text "Dies ist ein Kommentar".</span><span class="sxs-lookup"><span data-stu-id="b797b-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 <span data-ttu-id="b797b-129">[!code-vb[VbXMLSamples&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b797b-129">[!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b797b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b797b-130">See Also</span></span>  
 <span data-ttu-id="b797b-131"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="b797b-131"><xref:System.Xml.Linq.XComment></span></span>   
<span data-ttu-id="b797b-132"> [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="b797b-132"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="b797b-133"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="b797b-133"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="b797b-134"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="b797b-134"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
