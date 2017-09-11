---
title: Reine funktionale Transformationen von XML (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce372c12ec2359aa0f3f10e977241cb3d5a71ec8
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="7c2fc-102">Reine funktionale Transformationen von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c2fc-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="7c2fc-103">Dieser Abschnitt enthält eine Einführung in die funktionale Transformation für XML.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="7c2fc-104">Sie finden hier Erläuterungen der wichtigsten Konzepte und Begriffe sowie die Sprachkonstrukte, die Sie für den Einsatz funktionaler Transformationen kennen müssen. Außerdem enthält der Abschnitt auch Beispiele für die Verwendung funktionaler Transformationen zur Manipulation eines XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="7c2fc-105">Die Codebeispiele in diesem Abschnitt beziehen sich zwar alle auf LINQ to XML, aber die zugrunde liegenden Konzepte lassen sich auch auf andere LINQ-Technologien übertragen.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="7c2fc-106">Die [Lernprogramm: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) Lernprogramm bietet eine Reihe von Beispielen, jeweils auf dem vorherigen aufbauen.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="7c2fc-107">In diesen Beispielen wird die Manipulation von XML durch die reine funktionale Transformation veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="7c2fc-108">Dieses Lernprogramm setzt Kenntnisse von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="7c2fc-109">Sie finden hier keine ausführlichen semantischen Erläuterungen der Sprachkonstrukte. Wenn Sie diesbezüglich nähere Informationen benötigen, können Sie die an den entsprechenden Stellen angegebenen Links zur Sprachdokumentation verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="7c2fc-110">Es wird weiterhin davon ausgegangen, dass der Leser über grundlegende Kenntnisse von Begriffen und Konzepten der Informatik und von XML, einschließlich der XML-Namespaces, verfügt.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c2fc-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7c2fc-111">In This Section</span></span>  
  
|<span data-ttu-id="7c2fc-112">Thema</span><span class="sxs-lookup"><span data-stu-id="7c2fc-112">Topic</span></span>|<span data-ttu-id="7c2fc-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c2fc-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7c2fc-114">Einführung in reine funktionale Transformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c2fc-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="7c2fc-115">Beschreibt funktionale Transformationen und enthält entsprechende Terminologiedefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="7c2fc-116">Lernprogramm: Verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c2fc-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="7c2fc-117">Enthält ausführliche Beschreibungen der verzögerten Auswertung ("Lazy Evaluation") und der verzögerten Ausführung.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="7c2fc-118">Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c2fc-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="7c2fc-119">Veranschaulicht eine funktionale Transformation.</span><span class="sxs-lookup"><span data-stu-id="7c2fc-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c2fc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c2fc-120">See Also</span></span>  
 [<span data-ttu-id="7c2fc-121">Abfragen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c2fc-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
