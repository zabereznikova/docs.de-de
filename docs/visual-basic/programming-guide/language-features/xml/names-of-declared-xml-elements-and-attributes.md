---
title: Namen von deklarierten XML-Elementen und Attributen
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085619"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="f8465-102">Namen von deklarierten XML-Elementen und Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8465-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>

<span data-ttu-id="f8465-103">Dieses Thema enthält Visual Basic Richtlinien für das Benennen von XML-Elementen und-Attributen in XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="f8465-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="f8465-104">In einem XML-Literalwert können Sie einen lokalen Namen oder einen qualifizierten Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="f8465-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="f8465-105">Ein qualifizierter Name besteht aus einem XML-Namespace Präfix, einem Doppelpunkt und einem lokalen Namen.</span><span class="sxs-lookup"><span data-stu-id="f8465-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="f8465-106">Weitere Informationen zu XML-Namespace Präfixen finden Sie unter [XML-Elementliterale](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f8465-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f8465-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="f8465-107">Rules</span></span>  

 <span data-ttu-id="f8465-108">Der lokale Name eines Elements oder Attributs in Visual Basic muss den folgenden Regeln entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f8465-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="f8465-109">Er kann mit einem Namespace beginnen.</span><span class="sxs-lookup"><span data-stu-id="f8465-109">It can begin with a namespace.</span></span> <span data-ttu-id="f8465-110">Er muss mit einem Buchstaben oder einem Unterstrich ( `_` ) beginnen.</span><span class="sxs-lookup"><span data-stu-id="f8465-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="f8465-111">Sie darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-) enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8465-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="f8465-112">Er darf nicht mehr als 1.024 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="f8465-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="f8465-113">Doppelpunkte, die in Namen angezeigt werden, geben die Namespace Abgrenzung an.</span><span class="sxs-lookup"><span data-stu-id="f8465-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="f8465-114">Daher können Sie nur Doppelpunkte verwenden, um einen XML-Namespace für einen bestimmten Namen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8465-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="f8465-115">Außerdem sollten Sie die folgende Richtlinie einhalten.</span><span class="sxs-lookup"><span data-stu-id="f8465-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="f8465-116">Die XML 1,0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "XML" beginnen, einer beliebigen groß-und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="f8465-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="f8465-117">Verwenden Sie daher diese Namen nicht für die Element-und Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="f8465-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="f8465-118">Namens Längen Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f8465-118">Name Length Guidelines</span></span>  

 <span data-ttu-id="f8465-119">Als praktische Angelegenheit sollte ein Name so kurz wie möglich sein, während er die Art des Elements eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f8465-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="f8465-120">Dadurch wird die Lesbarkeit des Codes verbessert, und die Zeilen-und Quelldatei Größe wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="f8465-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="f8465-121">Der Name sollte jedoch nicht so kurz sein, dass er das Element nicht ordnungsgemäß beschreibt oder wie der Code es verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8465-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="f8465-122">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="f8465-122">This is important for the readability of your code.</span></span> <span data-ttu-id="f8465-123">Wenn ein anderer Benutzer versucht, ihn zu verstehen, oder wenn Sie sich nach dem Schreiben einen langen Zeitraum ansehen, können die entsprechenden Elementnamen Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="f8465-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="f8465-124">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="f8465-124">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="f8465-125">Bei XML-Elementnamen wird Groß-/Kleinschreibung beachtet</span><span class="sxs-lookup"><span data-stu-id="f8465-125">XML element names are case sensitive.</span></span> <span data-ttu-id="f8465-126">Dies bedeutet Folgendes: Wenn der Visual Basic Compiler zwei Namen vergleicht, die sich nur in alphabetischer Schreibweise unterscheiden, werden Sie als unterschiedliche Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f8465-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="f8465-127">Er interpretiert z. b `ABC` `abc` . und als Verweis auf getrennte Elemente.</span><span class="sxs-lookup"><span data-stu-id="f8465-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="f8465-128">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="f8465-128">XML Namespaces</span></span>  

 <span data-ttu-id="f8465-129">Beim Erstellen eines XML-Elementliterals können Sie das XML-Namespace Präfix für den Elementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="f8465-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="f8465-130">Weitere Informationen finden Sie unter [XML-Elementliterale](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f8465-130">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8465-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8465-131">See also</span></span>

- [<span data-ttu-id="f8465-132">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8465-132">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="f8465-133">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="f8465-133">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
