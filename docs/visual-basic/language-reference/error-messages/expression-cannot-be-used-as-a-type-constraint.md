---
title: "&#39; &lt;Ausdruck&gt;&#39; kann nicht als eine typeinschränkung verwendet werden"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords: BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 054c05747491afb02601df00225a703560cbe91c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="c5636-102">&#39; &lt;Ausdruck&gt;&#39; kann nicht als eine typeinschränkung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="c5636-102">&#39;&lt;expression&gt;&#39; cannot be used as a type constraint</span></span>
<span data-ttu-id="c5636-103">Eine Einschränkungsliste enthält einen Ausdruck, der keine gültige Einschränkung für einen Typparameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="c5636-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="c5636-104">Eine Einschränkungsliste erzwingt Anforderungen an das Typargument, das an den Typparameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5636-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="c5636-105">Sie können die folgenden Anforderungen in beliebiger Kombination angeben:</span><span class="sxs-lookup"><span data-stu-id="c5636-105">You can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="c5636-106">Das Typargument muss mindestens eine Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="c5636-106">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="c5636-107">Das Typargument darf von höchstens einer Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="c5636-107">The type argument must inherit from at most one class</span></span>  
  
-   <span data-ttu-id="c5636-108">Das Typargument muss einen parameterlosen Konstruktor verfügbar machen, auf den der erstellende Code zugreifen kann (die `New` -Einschränkung muss enthalten sein)</span><span class="sxs-lookup"><span data-stu-id="c5636-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="c5636-109">Wenn Sie keine bestimmte Klasse oder Schnittstelle in die Einschränkungsliste aufnehmen, können Sie eine allgemeinere Anforderung festlegen, indem Sie eine der folgenden Festlegungen treffen:</span><span class="sxs-lookup"><span data-stu-id="c5636-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
-   <span data-ttu-id="c5636-110">Das Typargument muss ein Werttyp sein (die Einschränkung `Structure` enthalten)</span><span class="sxs-lookup"><span data-stu-id="c5636-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
-   <span data-ttu-id="c5636-111">Das Typargument muss ein Verweistyp sein (die Einschränkung `Class` enthalten)</span><span class="sxs-lookup"><span data-stu-id="c5636-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="c5636-112">Sie können nicht sowohl `Structure` als auch `Class` für den gleichen Typparameter angeben, und Sie können jedes Schlüsselwort nur einmal angeben.</span><span class="sxs-lookup"><span data-stu-id="c5636-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="c5636-113">**Fehler-ID:** BC32061</span><span class="sxs-lookup"><span data-stu-id="c5636-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5636-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c5636-114">To correct this error</span></span>  
  
-   <span data-ttu-id="c5636-115">Stellen Sie sicher, dass der Ausdruck und dessen Elemente richtig geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="c5636-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
-   <span data-ttu-id="c5636-116">Wenn der Ausdruck die Anforderungen der vorangehenden Liste nicht erfüllt, entfernen Sie ihn aus der Einschränkungsliste.</span><span class="sxs-lookup"><span data-stu-id="c5636-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
-   <span data-ttu-id="c5636-117">Wenn der Ausdruck auf eine Schnittstelle oder Klasse verweist, stellen Sie sicher, dass der Compiler Zugriff auf diese Schnittstelle oder Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="c5636-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="c5636-118">Möglicherweise müssen Sie deren Namen qualifizieren und einen Verweis auf Ihr Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c5636-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="c5636-119">Weitere Informationen finden Sie unter "Verweise auf Projekte" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="c5636-119">For more information, see "References to Projects" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5636-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5636-120">See Also</span></span>  
 [<span data-ttu-id="c5636-121">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5636-121">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="c5636-122">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="c5636-122">Value Types and Reference Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="c5636-123">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="c5636-123">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="c5636-124">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="c5636-124">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
