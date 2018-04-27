---
title: Typerweiterung (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ddb0d61f0f1c94e8e28493d0c62afe1e09503804
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="58512-102">Typerweiterung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58512-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="58512-103">Wenn Sie ein Programmierelement in einem Modul deklarieren, stuft Visual Basic den Gültigkeitsbereich auf den Namespace, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="58512-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="58512-104">Dies bezeichnet man *heraufstufung geben*.</span><span class="sxs-lookup"><span data-stu-id="58512-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="58512-105">Das folgende Beispiel zeigt eine rumpfdefinition eines Moduls und zwei Member des Moduls.</span><span class="sxs-lookup"><span data-stu-id="58512-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="58512-106">In `projModule`Programmierelemente auf Modulebene deklarierten Elemente zu hochgestuft `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="58512-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="58512-107">Im vorherigen Beispiel `basicEnum` und `innerClass` höher gestuft werden, aber `numberSub` ist nicht der Fall, da er nicht auf Modulebene deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="58512-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="58512-108">Auswirkungen der Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="58512-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="58512-109">Die Auswirkung der typerweiterung ist Qualifizierungspfad müssen nicht den Namen des Moduls enthalten.</span><span class="sxs-lookup"><span data-stu-id="58512-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="58512-110">Das folgende Beispiel enthält zwei Aufrufe an die Prozedur im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="58512-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="58512-111">Im vorherigen Beispiel verwendet der erste Aufruf vollständige Qualifizierung-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="58512-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="58512-112">Allerdings ist dies nicht erforderlich aufgrund typerweiterung.</span><span class="sxs-lookup"><span data-stu-id="58512-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="58512-113">Der zweite Aufruf auch greift auf die Member des Moduls ohne `projModule` in die Qualifizierung-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="58512-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="58512-114">Entschärfen der Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="58512-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="58512-115">Wenn der Namespace bereits ein Element mit dem gleichen Namen wie ein Modul Element verfügt, ist typerweiterung wird für dieses Modul Element außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="58512-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="58512-116">Im folgenden Beispiel wird die rumpfdefinition einer Enumeration und ein Modul innerhalb des gleichen Namespace.</span><span class="sxs-lookup"><span data-stu-id="58512-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="58512-117">Im vorherigen Beispiel Visual Basic keine Klasse hochstufen `abc` auf `thisNameSpace` weil bereits eine Enumeration mit dem gleichen Namen auf Namespaceebene vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="58512-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="58512-118">Für den Zugriff auf `abcSub`, müssen Sie den vollständigen Qualifizierungspfad verwenden `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="58512-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="58512-119">Allerdings-Klasse `xyz` noch höher gestuft, und Sie können den `xyzSub` mit den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="58512-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="58512-120">Entschärfen der Typerweiterung für partielle Typen</span><span class="sxs-lookup"><span data-stu-id="58512-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="58512-121">Wenn eine Klasse oder Struktur innerhalb eines Moduls verwendet die [partielle](../../../../visual-basic/language-reference/modifiers/partial.md) Schlüsselwort typerweiterung ist für diese Klasse oder Struktur automatisch wird außer Kraft gesetzt, und zwar unabhängig davon, ob der Namespace ein Element mit dem gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="58512-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="58512-122">Andere Elemente im Modul sind weiterhin für typerweiterung geeignet.</span><span class="sxs-lookup"><span data-stu-id="58512-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="58512-123">**Folgen.**</span><span class="sxs-lookup"><span data-stu-id="58512-123">**Consequences.**</span></span> <span data-ttu-id="58512-124">Entschärfen von datentyphöherstufung der eine partielle Definition kann unerwartete Ergebnisse und sogar zu Compilerfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="58512-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="58512-125">Das folgende Beispiel zeigt das Gerüst eines partielle Definitionen einer Klasse, von denen innerhalb eines Moduls ist.</span><span class="sxs-lookup"><span data-stu-id="58512-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="58512-126">Im vorherigen Beispiel der Entwickler den Compiler an, die beiden partiellen Definitionen von merge erwarten kann `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="58512-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="58512-127">Der Compiler berücksichtigt jedoch nicht Heraufstufen der partiellen Definition in `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="58512-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="58512-128">Daher versucht er, zwei separate Klassen zu kompilieren, die beiden benannten `sampleClass` jedoch mit anderen Qualifizierung Pfade.</span><span class="sxs-lookup"><span data-stu-id="58512-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="58512-129">Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.</span><span class="sxs-lookup"><span data-stu-id="58512-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="58512-130">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="58512-130">Recommendations</span></span>  
 <span data-ttu-id="58512-131">Die folgenden Empfehlungen darstellen gebräuchliche programmiergrundlagen.</span><span class="sxs-lookup"><span data-stu-id="58512-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="58512-132">**Eindeutige Namen.**</span><span class="sxs-lookup"><span data-stu-id="58512-132">**Unique Names.**</span></span> <span data-ttu-id="58512-133">Wenn Sie vollständige Kontrolle über die Benennung von Programmierelementen haben, ist es immer ratsam, eindeutige Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="58512-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="58512-134">Identische Namen erfordern zusätzliche Qualifizierung und können Ihr Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="58512-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="58512-135">Sie können auch geringfügige Fehler zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="58512-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="58512-136">**Vollständige Qualifizierung.**</span><span class="sxs-lookup"><span data-stu-id="58512-136">**Full Qualification.**</span></span> <span data-ttu-id="58512-137">Bei der Arbeit mit Modulen und andere Elemente im selben Namespace ist am sichersten, immer vollständige Qualifizierung für alle Programmierelemente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58512-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="58512-138">Wenn typhöherstufung für ein Modul-Element erfolgt, und Sie dieses Element nicht vollständig qualifiziert, konnte die ein anderes Programmierelements versehentlich zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="58512-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58512-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58512-139">See Also</span></span>  
 [<span data-ttu-id="58512-140">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="58512-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="58512-141">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="58512-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="58512-142">Partial</span><span class="sxs-lookup"><span data-stu-id="58512-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="58512-143">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58512-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="58512-144">Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen</span><span class="sxs-lookup"><span data-stu-id="58512-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="58512-145">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="58512-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
