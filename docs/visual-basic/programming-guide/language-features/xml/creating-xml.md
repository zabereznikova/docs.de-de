---
title: Erstellen von XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 1c720bc2aca4cec3dd10656d924cf2413fc18a2d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351733"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="09a9d-102">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09a9d-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="09a9d-103">Visual Basic enables you to use *XML literals* directly in your code.</span><span class="sxs-lookup"><span data-stu-id="09a9d-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="09a9d-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span><span class="sxs-lookup"><span data-stu-id="09a9d-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="09a9d-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span><span class="sxs-lookup"><span data-stu-id="09a9d-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09a9d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="09a9d-106">In This Section</span></span>  
  
|<span data-ttu-id="09a9d-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="09a9d-107">Term</span></span>|<span data-ttu-id="09a9d-108">Definition</span><span class="sxs-lookup"><span data-stu-id="09a9d-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="09a9d-109">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="09a9d-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="09a9d-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09a9d-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="09a9d-111">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="09a9d-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="09a9d-112">Describes how to use embedded expressions in XML literals.</span><span class="sxs-lookup"><span data-stu-id="09a9d-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="09a9d-113">Gewusst wie: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="09a9d-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="09a9d-114">Describes how to create an XML element in code by using an XML literal.</span><span class="sxs-lookup"><span data-stu-id="09a9d-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="09a9d-115">Leerzeichen in XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="09a9d-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="09a9d-116">Describes how Visual Basic treats white space in XML literals.</span><span class="sxs-lookup"><span data-stu-id="09a9d-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="09a9d-117">XML-Literale und die XML 1.0-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="09a9d-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="09a9d-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span><span class="sxs-lookup"><span data-stu-id="09a9d-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="09a9d-119">Gewusst wie: Einbetten von Ausdrücken in XML-Literale</span><span class="sxs-lookup"><span data-stu-id="09a9d-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="09a9d-120">Describes how to use embedded expressions in XML literals to create content at run time.</span><span class="sxs-lookup"><span data-stu-id="09a9d-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="09a9d-121">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="09a9d-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="09a9d-122">Describes guidelines for naming XML elements and attributes.</span><span class="sxs-lookup"><span data-stu-id="09a9d-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09a9d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09a9d-123">See also</span></span>

- [<span data-ttu-id="09a9d-124">XML</span><span class="sxs-lookup"><span data-stu-id="09a9d-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
