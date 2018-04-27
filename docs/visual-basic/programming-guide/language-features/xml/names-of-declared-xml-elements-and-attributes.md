---
title: Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07666ead0770c8055a62f75cb481648b0c72ef8b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="842b0-102">Namen von deklarierten XML-Elementen und Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="842b0-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="842b0-103">Dieses Thema enthält Visual Basic-Richtlinien für die Benennung von XML-Elemente und Attribute im XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="842b0-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="842b0-104">In einem XML-literal können Sie einen lokalen Namen oder einen qualifizierten Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="842b0-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="842b0-105">Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einen Doppelpunkt und einem lokalen Namen.</span><span class="sxs-lookup"><span data-stu-id="842b0-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="842b0-106">Weitere Informationen zu XML-Namespacepräfixe, finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="842b0-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="842b0-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="842b0-107">Rules</span></span>  
 <span data-ttu-id="842b0-108">Ein lokaler Namen eines Elements oder Attributs in Visual Basic muss die folgenden Regeln entsprechen.</span><span class="sxs-lookup"><span data-stu-id="842b0-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="842b0-109">Sie können mit einem Namespace beginnen.</span><span class="sxs-lookup"><span data-stu-id="842b0-109">It can begin with a namespace.</span></span> <span data-ttu-id="842b0-110">Er muss mit einem Buchstaben oder Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="842b0-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="842b0-111">Es darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).</span><span class="sxs-lookup"><span data-stu-id="842b0-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="842b0-112">Es darf nicht mehr als 1.024 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="842b0-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="842b0-113">Doppelpunkte, die im Namen angezeigt werden. Geben Sie Abgrenzung Namespace an.</span><span class="sxs-lookup"><span data-stu-id="842b0-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="842b0-114">Aus diesem Grund können Sie Doppelpunkte nur zum Angeben eines XML-Namespaces für einen bestimmten Namen aus.</span><span class="sxs-lookup"><span data-stu-id="842b0-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="842b0-115">Darüber hinaus sollten Sie die folgenden Richtlinien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="842b0-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="842b0-116">XML 1.0-Spezifikation behält sich alle Namen, die mit der Zeichenfolge "Xml", der eine Variante der Schreibweise beginnt.</span><span class="sxs-lookup"><span data-stu-id="842b0-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="842b0-117">Verwenden Sie daher nicht die Namen für das Element und Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="842b0-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="842b0-118">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="842b0-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="842b0-119">Ein Name sollte aus praktischen Gründen so kurz wie möglich sein immer noch eindeutig identifiziert die Art des Elements.</span><span class="sxs-lookup"><span data-stu-id="842b0-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="842b0-120">Dies verbessert die Lesbarkeit des Codes und reduziert die Größe des Zeile Länge und Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="842b0-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="842b0-121">Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beschrieben werden, das Element oder wie Sie im Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="842b0-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="842b0-122">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="842b0-122">This is important for the readability of your code.</span></span> <span data-ttu-id="842b0-123">Wenn eine andere Person versucht wird, zu verstehen, oder wenn Sie selbst an ihn sind sehr lange, nachdem Sie ihn geschrieben haben, können die entsprechenden Elementnamen Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="842b0-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="842b0-124">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="842b0-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="842b0-125">XML-Elementnamen sind Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="842b0-125">XML element names are case sensitive.</span></span> <span data-ttu-id="842b0-126">Dies bedeutet, dass bei der Visual Basic-Compiler zwei Namen verglichen werden, die nur die Groß-und Kleinschreibung unterscheiden, werden als unterschiedliche Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="842b0-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="842b0-127">Beispielsweise interpretiert `ABC` und `abc` als Verweise auf verschiedene Elemente.</span><span class="sxs-lookup"><span data-stu-id="842b0-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="842b0-128">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="842b0-128">XML Namespaces</span></span>  
 <span data-ttu-id="842b0-129">Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="842b0-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="842b0-130">Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="842b0-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842b0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="842b0-131">See Also</span></span>  
 [<span data-ttu-id="842b0-132">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="842b0-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="842b0-133">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="842b0-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
