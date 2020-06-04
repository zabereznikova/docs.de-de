---
title: Konstanten und Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants [Visual Basic]
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants [Visual Basic], enumerations
- naming conventions [Visual Basic], constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
ms.openlocfilehash: 7d15c46c0f6bb00c23dd98e464f61a5f94b0773a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414401"
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="5769a-102">Konstanten und Enumerationen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5769a-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="5769a-103">Konstanten sind ein Weg, aussagekräftige Namen anstelle von Variablen mit unveränderlichem Wert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5769a-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="5769a-104">Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung konstant bleiben.</span><span class="sxs-lookup"><span data-stu-id="5769a-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="5769a-105">Sie können Konstanten verwenden, um aussagekräftige Namen anstelle von Zahlen anzugeben, wodurch Ihr Code besser lesbar wird.</span><span class="sxs-lookup"><span data-stu-id="5769a-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="5769a-106">Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5769a-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="5769a-107">Sie können zum Beispiel eine Enumeration für einen Satz von Integerkonstanten deklarieren, denen die Tage der Woche zugewiesen sind, und dann in Ihrem Code die Namen der Wochentage statt deren Integerwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="5769a-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5769a-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5769a-108">In This Section</span></span>  
  
|<span data-ttu-id="5769a-109">Begriff</span><span class="sxs-lookup"><span data-stu-id="5769a-109">Term</span></span>|<span data-ttu-id="5769a-110">Definition</span><span class="sxs-lookup"><span data-stu-id="5769a-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="5769a-111">Übersicht über Konstanten</span><span class="sxs-lookup"><span data-stu-id="5769a-111">Constants Overview</span></span>](constants-overview.md)|<span data-ttu-id="5769a-112">Die Themen in diesem Abschnitt beschreiben Konstanten und ihre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="5769a-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="5769a-113">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5769a-113">Enumerations Overview</span></span>](enumerations-overview.md)|<span data-ttu-id="5769a-114">Die Themen in diesem Abschnitt beschreiben Konstanten und ihre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="5769a-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="5769a-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5769a-115">Related Sections</span></span>  
  
|<span data-ttu-id="5769a-116">Begriff</span><span class="sxs-lookup"><span data-stu-id="5769a-116">Term</span></span>|<span data-ttu-id="5769a-117">Definition</span><span class="sxs-lookup"><span data-stu-id="5769a-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="5769a-118">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5769a-118">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)|<span data-ttu-id="5769a-119">Beschreibt die `Const`-Anweisung, die zum Deklarieren von Konstanten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5769a-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="5769a-120">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5769a-120">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)|<span data-ttu-id="5769a-121">Beschreibt die `Enum`-Anweisung, die zum Erstellen von Konstanten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5769a-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="5769a-122">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5769a-122">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="5769a-123">Beschreibt die `Option Explicit`-Anweisung, die auf Modulebene verwendet wird, um die explizite Deklaration aller Variablen in diesem Modul zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5769a-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="5769a-124">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5769a-124">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)|<span data-ttu-id="5769a-125">Beschreibt die `Option Infer`-Anweisung, die die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5769a-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="5769a-126">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5769a-126">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)|<span data-ttu-id="5769a-127">Beschreibt die `Option Strict`-Anweisung, die die implizite Datentypkonvertierung auf Erweiterungskonvertierungen beschränkt, wodurch spätes Binden und eine implizite Typisierung in einen `Object`-Typ nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="5769a-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
