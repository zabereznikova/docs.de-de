---
title: 'Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 293e8de848f83517211e3f3ed640102a2c534764
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a><span data-ttu-id="0fa69-102">Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-102">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>
<span data-ttu-id="0fa69-103">In diesem Tutorial wird gezeigt, wie Sie mit der funktionalen Transformation und LINQ to XML den Inhalt von XML-Dokumenten manipulieren können.</span><span class="sxs-lookup"><span data-stu-id="0fa69-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="0fa69-104">Die C#-Beispiele fragen Informationen in von Microsoft Word gespeicherten Office Open XML-WordprocessingML-Dokumenten ab und bearbeiten sie.</span><span class="sxs-lookup"><span data-stu-id="0fa69-104">The C# examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="0fa69-105">Weitere Informationen dazu finden Sie auf der [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573)-Website.</span><span class="sxs-lookup"><span data-stu-id="0fa69-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fa69-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0fa69-106">In This Section</span></span>  
  
|<span data-ttu-id="0fa69-107">Thema</span><span class="sxs-lookup"><span data-stu-id="0fa69-107">Topic</span></span>|<span data-ttu-id="0fa69-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0fa69-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0fa69-109">Form von WordprocessingML-Dokumenten (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-109">Shape of WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="0fa69-110">Enthält eine kurze Erläuterung der Bestandteile von WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="0fa69-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="0fa69-111">Erstellen eines Office Open-Quell-XML-Dokuments (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-111">Creating the Source Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="0fa69-112">Enthält schrittweise Anweisungen zum Erstellen des Quelldokuments für Abfragen in diesem Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="0fa69-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="0fa69-113">Suchen der standardmäßigen Absatzformatvorlage (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-113">Finding the Default Paragraph Style (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="0fa69-114">Zeigt eine Abfrage, die den Namen der Standardformatvorlage eines Dokuments ermittelt.</span><span class="sxs-lookup"><span data-stu-id="0fa69-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="0fa69-115">Abrufen der Absätze und ihrer Stile (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-115">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="0fa69-116">Zeigt eine Abfrage, die eine Auflistung der Absätze eines Dokuments abruft.</span><span class="sxs-lookup"><span data-stu-id="0fa69-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="0fa69-117">Abrufen des Texts der Absätze (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-117">Retrieving the Text of the Paragraphs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="0fa69-118">Erweitert die vorherige Abfrage so, dass der Text der einzelnen Absätze abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0fa69-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="0fa69-119">Refactoring mit einer Erweiterungsmethode (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-119">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="0fa69-120">Vereinfacht den Code, indem er mit einer Erweiterungsmethode umgestaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0fa69-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="0fa69-121">Refactoring mit einer reinen Funktion (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-121">Refactoring Using a Pure Function (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="0fa69-122">Sorgt für eine weitere Vereinfachung des Codes durch Refactoring mit einer reinen Funktion.</span><span class="sxs-lookup"><span data-stu-id="0fa69-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="0fa69-123">Projektieren von XML in eine andere Form (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-123">Projecting XML in a Different Shape (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="0fa69-124">Schließt eine XML-Transformation ab, indem XML in eine andere Form als das Originaldokument projiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0fa69-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="0fa69-125">Suchen von Text in Word-Dokumenten (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-125">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="0fa69-126">Verwendet die vorherigen Abfragen, um nach einer konkreten Textzeichenfolge in einem Dokument zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0fa69-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="0fa69-127">Details of Office Open XML WordprocessingML Documents (C#) (Details eines Office Open XML-WordprocessingML-Dokuments (C#))</span><span class="sxs-lookup"><span data-stu-id="0fa69-127">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="0fa69-128">Enthält einige Detailinformationen zu Office Open XML-WordprocessingML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="0fa69-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fa69-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fa69-129">See Also</span></span>  
 <span data-ttu-id="0fa69-130">[Reine funktionale XML-Transformationen (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="0fa69-130">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
 [<span data-ttu-id="0fa69-131">Einführung in reine funktionale Transformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="0fa69-131">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)

