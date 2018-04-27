---
title: Erstellen von XML in Visual Basic
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 029ff0a2120809fd4637de5910adaffa60e3b8a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="c4b66-102">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4b66-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="c4b66-103">Visual Basic ermöglicht es Ihnen, *XML-Literale* direkt im Code.</span><span class="sxs-lookup"><span data-stu-id="c4b66-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="c4b66-104">Die XML-literal-Syntax stellt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte und ähnelt der XML 1.0-Syntax.</span><span class="sxs-lookup"><span data-stu-id="c4b66-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="c4b66-105">Dies erleichtert die XML-Elemente, Dokumente und Fragmente programmgesteuert erstellt werden, da der Code dieselbe Struktur auf wie die endgültigen XML hat.</span><span class="sxs-lookup"><span data-stu-id="c4b66-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4b66-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c4b66-106">In This Section</span></span>  
  
|<span data-ttu-id="c4b66-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="c4b66-107">Term</span></span>|<span data-ttu-id="c4b66-108">Definition</span><span class="sxs-lookup"><span data-stu-id="c4b66-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="c4b66-109">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="c4b66-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="c4b66-110">Einführung in XML-Literale und die damit verbundenen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4b66-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="c4b66-111">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="c4b66-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="c4b66-112">Beschreibt, wie eingebettete Ausdrücke in XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="c4b66-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="c4b66-113">Gewusst wie: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="c4b66-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="c4b66-114">Beschreibt, wie ein XML-Element mit einem XML-literal in Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4b66-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="c4b66-115">Leerzeichen in XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="c4b66-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="c4b66-116">Beschreibt, wie Visual Basic Leerzeichen in XML-Literale behandelt.</span><span class="sxs-lookup"><span data-stu-id="c4b66-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="c4b66-117">XML-Literale und die XML 1.0-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="c4b66-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="c4b66-118">Beschreibt, wie die Syntax der XML-Literale in Visual Basic auf die XML 1.0-Spezifikation bezieht.</span><span class="sxs-lookup"><span data-stu-id="c4b66-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="c4b66-119">Gewusst wie: Einbetten von Ausdrücken in XML-Literale</span><span class="sxs-lookup"><span data-stu-id="c4b66-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="c4b66-120">Beschreibt, wie eingebettete Ausdrücke in XML-Literale zu verwenden, um Inhalte zur Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4b66-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="c4b66-121">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="c4b66-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="c4b66-122">Beschreibt die Richtlinien für die Benennung von XML-Elemente und Attribute.</span><span class="sxs-lookup"><span data-stu-id="c4b66-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4b66-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4b66-123">See Also</span></span>  
 [<span data-ttu-id="c4b66-124">XML</span><span class="sxs-lookup"><span data-stu-id="c4b66-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
