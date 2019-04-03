---
title: Erstellen von XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: d847f589bc47f8ab3d6691666bbd879e795db0c6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813040"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="35e3b-102">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35e3b-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="35e3b-103">Visual Basic können Sie mit *XML-Literale* direkt in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="35e3b-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="35e3b-104">Stellt die XML-Literalsyntax [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte und der XML 1.0-Syntax ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="35e3b-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="35e3b-105">Dies erleichtert die XML-Elemente, Dokumente und Fragmente programmgesteuert erstellt werden, da der Code die gleiche Struktur wie der endgültige XML-Code aufweist.</span><span class="sxs-lookup"><span data-stu-id="35e3b-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35e3b-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="35e3b-106">In This Section</span></span>  
  
|<span data-ttu-id="35e3b-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="35e3b-107">Term</span></span>|<span data-ttu-id="35e3b-108">Definition</span><span class="sxs-lookup"><span data-stu-id="35e3b-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="35e3b-109">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="35e3b-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="35e3b-110">Einführung in die XML-Literale und die damit verbundenen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35e3b-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="35e3b-111">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="35e3b-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="35e3b-112">Beschreibt, wie Sie eingebettete Ausdrücke in XML-Literalen verwendet.</span><span class="sxs-lookup"><span data-stu-id="35e3b-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="35e3b-113">Vorgehensweise: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="35e3b-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="35e3b-114">Beschreibt, wie Sie ein XML-Element mit einem XML-literal in Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35e3b-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="35e3b-115">Leerzeichen in XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="35e3b-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="35e3b-116">Beschreibt, wie Visual Basic Leerzeichen in XML-Literale behandelt.</span><span class="sxs-lookup"><span data-stu-id="35e3b-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="35e3b-117">XML-Literale und die XML 1.0-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="35e3b-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="35e3b-118">Beschreibt, wie sich die XML-Literale-Syntax in Visual Basic auf XML 1.0-Spezifikation bezieht.</span><span class="sxs-lookup"><span data-stu-id="35e3b-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="35e3b-119">Vorgehensweise: Einbetten von Ausdrücken in XML-Literale</span><span class="sxs-lookup"><span data-stu-id="35e3b-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="35e3b-120">Beschreibt, wie Sie eingebettete Ausdrücke in XML-Literalen verwendet, um Inhalte zur Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35e3b-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="35e3b-121">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="35e3b-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="35e3b-122">Enthält Richtlinien für die Benennung von XML-Elemente und Attribute.</span><span class="sxs-lookup"><span data-stu-id="35e3b-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35e3b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35e3b-123">See also</span></span>

- [<span data-ttu-id="35e3b-124">XML</span><span class="sxs-lookup"><span data-stu-id="35e3b-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
