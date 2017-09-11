---
title: Namen von deklarierten XML-Elementen und Attributen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
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
ms.openlocfilehash: 2c0bb2350f50138d00e202e2e887a2202d21942f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="31a19-102">Namen von deklarierten XML-Elementen und Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31a19-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="31a19-103">Dieses Thema enthält [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Richtlinien für die Benennung von XML-Elementen und Attributen in XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="31a19-103">This topic provides [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="31a19-104">In einem XML-literal können Sie einen lokalen Namen oder einen qualifizierten Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="31a19-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="31a19-105">Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einem Doppelpunkt und einem lokalen Namen.</span><span class="sxs-lookup"><span data-stu-id="31a19-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="31a19-106">Weitere Informationen zu XML-Namespacepräfixen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="31a19-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="31a19-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="31a19-107">Rules</span></span>  
 <span data-ttu-id="31a19-108">Einen lokalen Namen eines Elements oder Attributs in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen die folgenden Regeln einhalten.</span><span class="sxs-lookup"><span data-stu-id="31a19-108">A local name of an element or attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="31a19-109">Sie können mit einem Namespace beginnen.</span><span class="sxs-lookup"><span data-stu-id="31a19-109">It can begin with a namespace.</span></span> <span data-ttu-id="31a19-110">Es muss mit einem Buchstaben oder Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="31a19-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="31a19-111">Es darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).</span><span class="sxs-lookup"><span data-stu-id="31a19-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="31a19-112">Es muss nicht mehr als 1024 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="31a19-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="31a19-113">Doppelpunkte, die innerhalb von Namen Namespaceabgrenzungen.</span><span class="sxs-lookup"><span data-stu-id="31a19-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="31a19-114">Daher können Sie Doppelpunkte nur für einen XML-Namespace für einen bestimmten Namen geben.</span><span class="sxs-lookup"><span data-stu-id="31a19-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="31a19-115">Darüber hinaus sollten Sie sich an die folgenden Richtlinien halten.</span><span class="sxs-lookup"><span data-stu-id="31a19-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="31a19-116">XML 1.0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "Xml", der Variation Großschreibung ab.</span><span class="sxs-lookup"><span data-stu-id="31a19-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="31a19-117">Verwenden Sie daher nicht die Namen für das Element und die Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="31a19-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="31a19-118">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="31a19-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="31a19-119">Ein Namen sollten aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="31a19-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="31a19-120">Dies verbessert die Lesbarkeit des Codes und Länge und die Quelldatei die Größe verringert.</span><span class="sxs-lookup"><span data-stu-id="31a19-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="31a19-121">Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beantwortet werden, das Element oder wie der Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="31a19-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="31a19-122">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="31a19-122">This is important for the readability of your code.</span></span> <span data-ttu-id="31a19-123">Wenn jemand versucht, zu verstehen, oder wenn Sie sich diese betrachten sehr lange, nachdem Sie ihn geschrieben haben, können geeigneter Elementnamen Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="31a19-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="31a19-124">Groß-und Kleinschreibung bei Namen</span><span class="sxs-lookup"><span data-stu-id="31a19-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="31a19-125">XML-Elementnamen Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="31a19-125">XML element names are case sensitive.</span></span> <span data-ttu-id="31a19-126">Dies bedeutet, dass bei der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler vergleicht zwei Namen, die nur die Groß-und Kleinschreibung unterscheiden, als unterschiedliche Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="31a19-126">This means that when the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="31a19-127">Interpretiert z. B. `ABC` und `abc` als Verweise auf verschiedene Elemente.</span><span class="sxs-lookup"><span data-stu-id="31a19-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="31a19-128">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="31a19-128">XML Namespaces</span></span>  
 <span data-ttu-id="31a19-129">Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="31a19-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="31a19-130">Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="31a19-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a19-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31a19-131">See Also</span></span>  
 <span data-ttu-id="31a19-132">[Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="31a19-132">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="31a19-133"> [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span><span class="sxs-lookup"><span data-stu-id="31a19-133"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span></span>
