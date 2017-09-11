---
title: "Einführung in reine funktionale Transformationen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 82bf3348-c503-4854-a91f-71f9835779ff
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 72d05eada95f5ce08d60c283346e221328c23020
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="introduction-to-pure-functional-transformations-visual-basic"></a><span data-ttu-id="bce3d-102">Einführung in reine funktionale Transformationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-102">Introduction to Pure Functional Transformations (Visual Basic)</span></span>
<span data-ttu-id="bce3d-103">Dieser Abschnitt führt Sie in das Thema "funktionale Transformationen" ein und bietet eine Übersicht über die zugrunde liegenden Konzepte und die zugehörigen Sprachkonstrukte.</span><span class="sxs-lookup"><span data-stu-id="bce3d-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="bce3d-104">Es werden die Unterschiede zwischen dem Programmieren mit dem objektorientierten Ansatz und dem Programmieren mit der funktionalen Transformation erläutert und Empfehlungen für die Umstellung auf die funktionale Transformation gegeben.</span><span class="sxs-lookup"><span data-stu-id="bce3d-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="bce3d-105">In diesem Abschnitt wird die XML-Transformation zu Illustrationszwecken verwendet, funktionale Transformationen können aber auch in vielen anderen Programmierszenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bce3d-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bce3d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bce3d-106">In This Section</span></span>  
  
|<span data-ttu-id="bce3d-107">Thema</span><span class="sxs-lookup"><span data-stu-id="bce3d-107">Topic</span></span>|<span data-ttu-id="bce3d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce3d-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bce3d-109">Konzepte und Terminologie (funktionale Transformation) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-109">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="bce3d-110">Enthält eine Einführung in die Konzepte und Begriffe der Transformationen mit reinen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bce3d-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="bce3d-111">Funktionale Programmierung und Imperative Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-111">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="bce3d-112">Benennt die Gemeinsamkeiten und Unterschiede der funktionalen Programmierung und der herkömmlichen imperativen (prozeduralen) Programmierung.</span><span class="sxs-lookup"><span data-stu-id="bce3d-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="bce3d-113">Umgestalten in reine Funktionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-113">Refactoring Into Pure Functions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="bce3d-114">Enthält eine Einführung in die reinen Funktionen und zeigt Beispiele für reine und unreine Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bce3d-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="bce3d-115">Anwendbarkeit der funktionalen Transformation (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-115">Applicability of Functional Transformation (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="bce3d-116">Beschreibt typische Szenarios für funktionale Transformationen.</span><span class="sxs-lookup"><span data-stu-id="bce3d-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="bce3d-117">Funktionale Transformation von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="bce3d-118">Beschreibt funktionale Transformationen im Kontext der Transformierung von XML-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="bce3d-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bce3d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bce3d-119">See Also</span></span>  
 [<span data-ttu-id="bce3d-120">Reine funktionale Transformationen von XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce3d-120">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
