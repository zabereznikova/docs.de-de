---
title: 'Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: f8028ba8-2dd1-4425-930c-8cc23176ebbc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 28ab2d19cba0344868061fbe1f59c546a569fbdc
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-visual-basic"></a><span data-ttu-id="d9d0e-102">Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-102">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>
<span data-ttu-id="d9d0e-103">In diesem Tutorial wird gezeigt, wie Sie mit der funktionalen Transformation und LINQ to XML den Inhalt von XML-Dokumenten manipulieren können.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="d9d0e-104">Die Visual Basic-Beispiele für Abfragen und Bearbeiten von Informationen in von Microsoft Word gespeicherten Office Open XML-WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-104">The Visual Basic examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="d9d0e-105">Weitere Informationen finden Sie unter der [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Website.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9d0e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d9d0e-106">In This Section</span></span>  
  
|<span data-ttu-id="d9d0e-107">Thema</span><span class="sxs-lookup"><span data-stu-id="d9d0e-107">Topic</span></span>|<span data-ttu-id="d9d0e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9d0e-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d9d0e-109">Form von WordprocessingML-Dokumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-109">Shape of WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="d9d0e-110">Enthält eine kurze Erläuterung der Bestandteile von WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="d9d0e-111">Erstellen von Office Open XML-Quelldokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-111">Creating the Source Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="d9d0e-112">Enthält schrittweise Anweisungen zum Erstellen des Quelldokuments für Abfragen in diesem Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="d9d0e-113">Suchen der standardmäßigen Absatzformatvorlage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-113">Finding the Default Paragraph Style (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="d9d0e-114">Zeigt eine Abfrage, die den Namen der Standardformatvorlage eines Dokuments ermittelt.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="d9d0e-115">Abrufen der Absätze und deren Stile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-115">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="d9d0e-116">Zeigt eine Abfrage, die eine Auflistung der Absätze eines Dokuments abruft.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="d9d0e-117">Abrufen des Texts der Absätze (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-117">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="d9d0e-118">Erweitert die vorherige Abfrage so, dass der Text der einzelnen Absätze abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="d9d0e-119">Umgestalten mit einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-119">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="d9d0e-120">Vereinfacht den Code, indem er mit einer Erweiterungsmethode umgestaltet wird.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="d9d0e-121">Umgestalten mit einer reinen Funktion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-121">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="d9d0e-122">Sorgt für eine weitere Vereinfachung des Codes durch Refactoring mit einer reinen Funktion.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="d9d0e-123">Projizieren von XML in eine andere Form (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-123">Projecting XML in a Different Shape (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="d9d0e-124">Schließt eine XML-Transformation ab, indem XML in eine andere Form als das Originaldokument projiziert wird.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="d9d0e-125">Suchen nach Text in Word-Dokumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-125">Finding Text in Word Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="d9d0e-126">Verwendet die vorherigen Abfragen, um nach einer konkreten Textzeichenfolge in einem Dokument zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="d9d0e-127">Details von Office Open XML-WordprocessingML-Dokumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-127">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="d9d0e-128">Enthält einige Detailinformationen zu Office Open XML-WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="d9d0e-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9d0e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d0e-129">See Also</span></span>  
 <span data-ttu-id="d9d0e-130">[Reine funktionale Transformationen von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="d9d0e-130">[Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
<span data-ttu-id="d9d0e-131"> [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="d9d0e-131"> [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span></span>
