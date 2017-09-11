---
title: Erstellen von XML in Visual Basic | Microsoft-Dokumentation
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
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
ms.openlocfilehash: ec45ab4dc7d4c9282d444c00b0b262b3d8dd4da1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="b9400-102">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9400-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b9400-103">können Sie mit *XML-Literale* direkt im Code.</span><span class="sxs-lookup"><span data-stu-id="b9400-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="b9400-104">Stellt die XML-Literale Syntax [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte und ähnelt der XML 1.0-Syntax.</span><span class="sxs-lookup"><span data-stu-id="b9400-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="b9400-105">Dies erleichtert die XML-Elemente, Dokumente und Fragmente programmgesteuert erstellt werden, da der Code dieselbe Struktur wie die endgültigen XML enthält.</span><span class="sxs-lookup"><span data-stu-id="b9400-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9400-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b9400-106">In This Section</span></span>  
  
|<span data-ttu-id="b9400-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="b9400-107">Term</span></span>|<span data-ttu-id="b9400-108">Definition</span><span class="sxs-lookup"><span data-stu-id="b9400-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="b9400-109">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="b9400-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="b9400-110">Einführung in XML-Literale und deren Beziehung zu [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9400-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>|  
|[<span data-ttu-id="b9400-111">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="b9400-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="b9400-112">Beschreibt, wie eingebettete Ausdrücke in XML-Literalen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9400-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="b9400-113">Gewusst wie: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="b9400-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="b9400-114">Beschreibt, wie ein XML-Element mit einem XML-literal in Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9400-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="b9400-115">Leerzeichen in XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="b9400-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="b9400-116">Beschreibt, wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] behandelt Leerraum in XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="b9400-116">Describes how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="b9400-117">XML-Literale und die XML 1.0-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="b9400-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="b9400-118">Beschreibt, wie die XML-Literalen Syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bezieht sich auf die XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="b9400-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="b9400-119">Gewusst wie: Einbetten von Ausdrücken in XML-Literale</span><span class="sxs-lookup"><span data-stu-id="b9400-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="b9400-120">Beschreibt, wie eingebettete Ausdrücke in XML-Literalen verwendet werden, um Inhalt zur Laufzeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9400-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="b9400-121">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="b9400-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="b9400-122">Enthält Richtlinien für die Benennung von XML-Elementen und Attributen.</span><span class="sxs-lookup"><span data-stu-id="b9400-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9400-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9400-123">See Also</span></span>  
 [<span data-ttu-id="b9400-124">XML</span><span class="sxs-lookup"><span data-stu-id="b9400-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
