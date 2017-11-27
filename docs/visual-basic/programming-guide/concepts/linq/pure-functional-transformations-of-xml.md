---
title: Reiner funktionaler Transformationen von XML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01ad228d91037de1585d1e66292fddb80c785ada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="ee585-102">Reiner funktionaler Transformationen von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee585-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="ee585-103">Dieser Abschnitt enthält eine Einführung in die funktionale Transformation für XML.</span><span class="sxs-lookup"><span data-stu-id="ee585-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="ee585-104">Sie finden hier Erläuterungen der wichtigsten Konzepte und Begriffe sowie die Sprachkonstrukte, die Sie für den Einsatz funktionaler Transformationen kennen müssen. Außerdem enthält der Abschnitt auch Beispiele für die Verwendung funktionaler Transformationen zur Manipulation eines XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="ee585-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="ee585-105">Die Codebeispiele in diesem Abschnitt beziehen sich zwar alle auf LINQ to XML, aber die zugrunde liegenden Konzepte lassen sich auch auf andere LINQ-Technologien übertragen.</span><span class="sxs-lookup"><span data-stu-id="ee585-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="ee585-106">Die [Lernprogramm: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) Lernprogramm enthält eine Reihe von Beispielen, die jede baut auf der vorherigen Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ee585-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="ee585-107">In diesen Beispielen wird die Manipulation von XML durch die reine funktionale Transformation veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ee585-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="ee585-108">In diesem Lernprogramm wird davon ausgegangen praktische Kenntnisse in Visual Basic aus.</span><span class="sxs-lookup"><span data-stu-id="ee585-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="ee585-109">Sie finden hier keine ausführlichen semantischen Erläuterungen der Sprachkonstrukte. Wenn Sie diesbezüglich nähere Informationen benötigen, können Sie die an den entsprechenden Stellen angegebenen Links zur Sprachdokumentation verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee585-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="ee585-110">Es wird weiterhin davon ausgegangen, dass der Leser über grundlegende Kenntnisse von Begriffen und Konzepten der Informatik und von XML, einschließlich der XML-Namespaces, verfügt.</span><span class="sxs-lookup"><span data-stu-id="ee585-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee585-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ee585-111">In This Section</span></span>  
  
|<span data-ttu-id="ee585-112">Thema</span><span class="sxs-lookup"><span data-stu-id="ee585-112">Topic</span></span>|<span data-ttu-id="ee585-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee585-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ee585-114">Einführung in reine funktionale Transformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee585-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="ee585-115">Beschreibt funktionale Transformationen und enthält entsprechende Terminologiedefinitionen.</span><span class="sxs-lookup"><span data-stu-id="ee585-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="ee585-116">Lernprogramm: Verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee585-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="ee585-117">Enthält ausführliche Beschreibungen der verzögerten Auswertung ("Lazy Evaluation") und der verzögerten Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ee585-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="ee585-118">Lernprogramm: Bearbeiten von Inhalt in einem WordprocessingML-Dokument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee585-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="ee585-119">Veranschaulicht eine funktionale Transformation.</span><span class="sxs-lookup"><span data-stu-id="ee585-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee585-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee585-120">See Also</span></span>  
 [<span data-ttu-id="ee585-121">Abfragen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee585-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
