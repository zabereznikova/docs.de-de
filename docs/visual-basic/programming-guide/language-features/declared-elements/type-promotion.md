---
title: Geben Sie Promotion (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
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
ms.openlocfilehash: 383f4b1d29e9bbf81eee44bf78762a80aea9eb36
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="a4786-102">Typerweiterung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4786-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="a4786-103">Wenn Sie in einem Modul ein Programmierelement deklarieren [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] stuft den Gültigkeitsbereich auf den Namespace, der das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="a4786-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="a4786-104">Dies wird als bezeichnet *geben Promotion*.</span><span class="sxs-lookup"><span data-stu-id="a4786-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="a4786-105">Das folgende Beispiel zeigt eine Skelett Definition eines Moduls und zwei Member dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="a4786-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 <span data-ttu-id="a4786-106">[!code-vb[VbVbalrDeclaredElements&#1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4786-106">[!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span></span>  
  
 <span data-ttu-id="a4786-107">In `projModule`Programmierelemente auf Modulebene deklarierte Elemente zu hochgestuft werden `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="a4786-107">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="a4786-108">Im vorangehenden Beispiel `basicEnum` und `innerClass` höher gestuft werden, aber `numberSub` dagegen nicht, da es auf Modulebene nicht deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="a4786-108">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="a4786-109">Auswirkung der Heraufstufen von Typen</span><span class="sxs-lookup"><span data-stu-id="a4786-109">Effect of Type Promotion</span></span>  
 <span data-ttu-id="a4786-110">Heraufstufen von Typen wird ein Qualifizierungspfad müssen nicht den Namen des Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4786-110">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="a4786-111">Das folgende Beispiel enthält zwei Aufrufe an die Prozedur im vorhergehenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a4786-111">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 <span data-ttu-id="a4786-112">[!code-vb[VbVbalrDeclaredElements&#2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4786-112">[!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span></span>  
  
 <span data-ttu-id="a4786-113">Im vorherigen Beispiel verwendet der erste Aufruf vollständige Qualifizierung Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4786-113">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="a4786-114">Dies ist jedoch nicht notwendig aufgrund heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="a4786-114">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="a4786-115">Die zweite Aufruf erfolgt ebenfalls die Member des Moduls, ohne `projModule` in die Qualifikation-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4786-115">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="a4786-116">Entschärfen von Heraufstufen von Typen</span><span class="sxs-lookup"><span data-stu-id="a4786-116">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="a4786-117">Wenn der Namespace bereits einen Member mit dem gleichen Namen wie einen Modulmember verfügt, erfolgt Heraufstufen von Typen für dieses Modul-Element.</span><span class="sxs-lookup"><span data-stu-id="a4786-117">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="a4786-118">Das folgende Beispiel zeigt eine Skelette Definition für eine Enumeration und ein Modul innerhalb desselben Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a4786-118">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 <span data-ttu-id="a4786-119">[!code-vb[VbVbalrDeclaredElements&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4786-119">[!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span></span>  
  
 <span data-ttu-id="a4786-120">Im vorangehenden Beispiel [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kann nicht höher gestuft Klasse `abc` zu `thisNameSpace` da bereits eine Enumeration mit dem gleichen Namen auf Namespaceebene vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a4786-120">In the preceding example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="a4786-121">Für den Zugriff auf `abcSub`, müssen Sie den vollständigen Qualifizierungspfad verwenden `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="a4786-121">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="a4786-122">-Klasse `xyz` wird jedoch erweitert, und Sie können den `xyzSub` mit den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="a4786-122">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="a4786-123">Entschärfen von Heraufstufen von Typen für partielle Typen</span><span class="sxs-lookup"><span data-stu-id="a4786-123">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="a4786-124">Wenn eine Klasse oder Struktur innerhalb eines Moduls verwendet die [teilweise](../../../../visual-basic/language-reference/modifiers/partial.md) -Schlüsselwort, Heraufstufen von Typen ist automatisch für diese Klasse oder Struktur, außer Kraft gesetzt, und zwar unabhängig davon, ob der Namespace einen Member mit dem gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="a4786-124">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="a4786-125">Andere Elemente im Modul kommen noch für heraufstufen.</span><span class="sxs-lookup"><span data-stu-id="a4786-125">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="a4786-126">**Folgen.**</span><span class="sxs-lookup"><span data-stu-id="a4786-126">**Consequences.**</span></span> <span data-ttu-id="a4786-127">Entschärfen von Heraufstufen einer partiellen Definition kann unerwartete Ergebnisse und sogar zu Compilerfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="a4786-127">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="a4786-128">Im folgenden Beispiel wird das Skelett partielle Definitionen einer Klasse, von denen innerhalb eines Moduls ist.</span><span class="sxs-lookup"><span data-stu-id="a4786-128">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 <span data-ttu-id="a4786-129">[!code-vb[VbVbalrDeclaredElements&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4786-129">[!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span></span>  
  
 <span data-ttu-id="a4786-130">Im vorangehenden Beispiel erwarten Entwickler den Compiler die beiden partiellen Definitionen von merge `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="a4786-130">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="a4786-131">Der Compiler berücksichtigt jedoch keine Erweiterung der partiellen Definition in `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="a4786-131">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="a4786-132">Daher versucht er, zwei separate Klassen zu kompilieren, mit dem Namen `sampleClass` jedoch mit verschiedenen Qualifizierung Pfade.</span><span class="sxs-lookup"><span data-stu-id="a4786-132">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="a4786-133">Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a4786-133">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="a4786-134">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a4786-134">Recommendations</span></span>  
 <span data-ttu-id="a4786-135">Die folgenden Aspekte stellen guten Programmierpraxis dar.</span><span class="sxs-lookup"><span data-stu-id="a4786-135">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="a4786-136">**Eindeutige Namen.**</span><span class="sxs-lookup"><span data-stu-id="a4786-136">**Unique Names.**</span></span> <span data-ttu-id="a4786-137">Wenn Sie vollständige Kontrolle über die Benennung von Programmierelementen verfügen, ist es immer eine gute Idee, eindeutige Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4786-137">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="a4786-138">Identische Namen können erfordern zusätzliche Qualifizierung und Ihren Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a4786-138">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="a4786-139">Sie können auch Fehler auftreten und unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="a4786-139">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="a4786-140">**Vollständige Qualifizierung.**</span><span class="sxs-lookup"><span data-stu-id="a4786-140">**Full Qualification.**</span></span> <span data-ttu-id="a4786-141">Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, ist am sichersten immer vollständige Qualifizierung für alle Programmierelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4786-141">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="a4786-142">Wenn Heraufstufen von Typen für einen Modulmember erfolgt und Sie diesen Member nicht vollständig qualifizieren, konnten Sie versehentlich einen anderen Programmierelement zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a4786-142">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4786-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4786-143">See Also</span></span>  
 <span data-ttu-id="a4786-144">[Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a4786-144">[Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="a4786-145"> [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a4786-145"> [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="a4786-146"> [Teilweise](../../../../visual-basic/language-reference/modifiers/partial.md) </span><span class="sxs-lookup"><span data-stu-id="a4786-146"> [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) </span></span>  
<span data-ttu-id="a4786-147"> [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="a4786-147"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="a4786-148"> [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="a4786-148"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="a4786-149"> [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="a4786-149"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
