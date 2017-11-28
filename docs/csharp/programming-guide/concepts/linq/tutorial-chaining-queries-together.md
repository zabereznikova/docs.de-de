---
title: 'Tutorial: Verketten von Abfragen (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 08196f4780e566cc05e36b6cfe78caad3e9c96a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="a771d-102">Tutorial: Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="a771d-103">Dieses Lernprogramm zeigt das Verarbeitungsmodell für das Verketten von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="a771d-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="a771d-104">Das Verketten von Abfragen ist ein wichtiger Bestandteil des Schreibens funktionaler Transformationen.</span><span class="sxs-lookup"><span data-stu-id="a771d-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="a771d-105">Es ist daher wichtig, genau zu verstehen, wie verkettete Abfragen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a771d-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="a771d-106">Bei Abfragen, die Office Open XML-Dokumente verarbeiten, kommt dieses Verfahren sehr häufig vor.</span><span class="sxs-lookup"><span data-stu-id="a771d-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a771d-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a771d-107">In This Section</span></span>  
  
|<span data-ttu-id="a771d-108">Thema</span><span class="sxs-lookup"><span data-stu-id="a771d-108">Topic</span></span>|<span data-ttu-id="a771d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a771d-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a771d-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#) (Verzögerte Ausführung und Auswertung in LINQ to XML (C#))</span><span class="sxs-lookup"><span data-stu-id="a771d-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="a771d-111">Beschreibt die Konzepte der verzögerten Ausführung (Deferred Execution) und der verzögerten Auswertung (Lazy Evaluation).</span><span class="sxs-lookup"><span data-stu-id="a771d-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|[<span data-ttu-id="a771d-112">Beispiel für eine verzögerte Ausführung (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-112">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)|<span data-ttu-id="a771d-113">Enthält ein Beispiel für eine verzögerte Ausführung.</span><span class="sxs-lookup"><span data-stu-id="a771d-113">Provides an example of deferred execution.</span></span>|  
|[<span data-ttu-id="a771d-114">Beispiel für das Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-114">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)|<span data-ttu-id="a771d-115">Zeigt, wie die verzögerte Ausführung bei verketteten Abfragen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a771d-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|[<span data-ttu-id="a771d-116">Zwischenmaterialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-116">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)|<span data-ttu-id="a771d-117">Identifiziert und veranschaulicht die Semantik von Zwischenmaterialisierungen.</span><span class="sxs-lookup"><span data-stu-id="a771d-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|[<span data-ttu-id="a771d-118">Verketten von Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-118">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)|<span data-ttu-id="a771d-119">Beschreibt die verzögerte Semantik der Standardabfrageoperatoren.</span><span class="sxs-lookup"><span data-stu-id="a771d-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a771d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a771d-120">See Also</span></span>  
 [<span data-ttu-id="a771d-121">Reine funktionale XML-Transformationen (C#)</span><span class="sxs-lookup"><span data-stu-id="a771d-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
