---
title: Deklarierte Elementnamen (Visual Basic) | Microsoft-Dokumentation
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
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
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
ms.openlocfilehash: 899bcb2ecc8f5c07fdf4592e15827ff67f55c136
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="cbbc3-102">Namen deklarierter Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbbc3-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="cbbc3-103">Jedes deklarierte Element hat einen Namen, die auch als bezeichnet ein *Bezeichner*, wird der Code dazu verwendet wird, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="cbbc3-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="cbbc3-104">Rules</span></span>  
 <span data-ttu-id="cbbc3-105">Ein Elementname in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen die folgenden Regeln beachten:</span><span class="sxs-lookup"><span data-stu-id="cbbc3-105">An element name in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="cbbc3-106">Es muss mit einem Buchstaben oder Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="cbbc3-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="cbbc3-107">Es darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="cbbc3-108">Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalstelle enthalten, wenn er mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="cbbc3-109">Sie müssen nicht mehr als 1023 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="cbbc3-110">Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge eines vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="cbbc3-111">Das folgende Beispiel zeigt einige gültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="cbbc3-112">Das folgende Beispiel zeigt einige ungültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="cbbc3-113">Die erste enthält nur einen Unterstrich, das zweite Beispiel beginnt mit einer Dezimalstelle und die dritte Spalte enthält ein ungültiges Zeichen ($).</span><span class="sxs-lookup"><span data-stu-id="cbbc3-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="cbbc3-114">Elementnamen, die mit einem Unterstrich beginnen (`_`) sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), d. h. CLS-kompatiblen Code eine Komponente verwenden können, die solche Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="cbbc3-115">Allerdings ist ein Unterstrich an einer anderen Stelle in einem Elementnamen CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="cbbc3-116">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="cbbc3-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="cbbc3-117">Ihr Name sollte aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="cbbc3-118">Dies verbessert die Lesbarkeit des Codes und Länge und die Quelldatei die Größe verringert.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="cbbc3-119">Auf der anderen Seite sollte den Namen Ihres nicht so kurz sein, dass es nicht angemessen beantwortet werden, was das Element darstellt, und wie der Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="cbbc3-120">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-120">This is important for the readability of your code.</span></span> <span data-ttu-id="cbbc3-121">Wenn jemand versucht, zu verstehen, oder wenn Sie sich diese betrachten sehr lange, nachdem Sie ihn geschrieben haben, geeignete Elementnamen verwendet eine beträchtliche Zeit speichern.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="cbbc3-122">Namen mit Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="cbbc3-122">Escaped Names</span></span>  
 <span data-ttu-id="cbbc3-123">In der Regel ein Elementname muss mit keinem der reservierten Schlüsselwort [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], wie z. B. `Case` oder `Friend`.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="cbbc3-124">Allerdings können Sie definieren ein *mit Escapezeichen versehen Name*, der von geschweiften Klammern eingeschlossen ist (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="cbbc3-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="cbbc3-125">Ein Name mit Escapezeichen kann keinem [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Schlüsselwort, da die Klammern Mehrdeutigkeit.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-125">An escaped name can match any [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="cbbc3-126">Die Klammern wird auch bei auf den Namen später in Ihrem Code verweisen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="cbbc3-127">Im Allgemeinen verwenden Sie Escapezeichen Namen nur, wenn:</span><span class="sxs-lookup"><span data-stu-id="cbbc3-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="cbbc3-128">Ihr Code wurde von einer früheren Version von migriert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , die als ein Dienstname verwendete Schlüsselwort nicht reserviert oder</span><span class="sxs-lookup"><span data-stu-id="cbbc3-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="cbbc3-129">Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="cbbc3-130">Andernfalls sollten Sie das Element umbenennen, wenn der Name mit einem Schlüsselwort in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="cbbc3-131">Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit dazu.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="cbbc3-132">Weitere Informationen finden Sie unter [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="cbbc3-132">For more information, see [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="cbbc3-133">Groß-und Kleinschreibung bei Namen</span><span class="sxs-lookup"><span data-stu-id="cbbc3-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="cbbc3-134">Elementnamen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-134">Element names in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] are case-insensitive.</span></span> <span data-ttu-id="cbbc3-135">Dies bedeutet, dass die beiden Namen-Compiler, die nur Groß-und Kleinschreibung unterscheiden, werden als derselbe Name interpretiert.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="cbbc3-136">Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="cbbc3-137">Die common Language Runtime (CLR) wird jedoch die Groß-/Kleinschreibung Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="cbbc3-138">Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="cbbc3-139">Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="cbbc3-140">Wenn Sie danach die Klasse erneut kompilieren und ändern den Namen des Elements an `abc`, die andere Assemblys, die mithilfe der Klasse können nicht mehr auf dieses Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="cbbc3-141">Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="cbbc3-142">Namen und Gebietsschemas</span><span class="sxs-lookup"><span data-stu-id="cbbc3-142">Names and Locales</span></span>  
 <span data-ttu-id="cbbc3-143">Vergleich der Namen ist vom Gebietsschema unabhängig.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="cbbc3-144">Wenn zwei Namen in einem Gebietsschema übereinstimmen, stimmen sie in allen Gebietsschemas überein.</span><span class="sxs-lookup"><span data-stu-id="cbbc3-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbbc3-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbbc3-145">See Also</span></span>  
 <span data-ttu-id="cbbc3-146">[Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span><span class="sxs-lookup"><span data-stu-id="cbbc3-146">[Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span></span>  
<span data-ttu-id="cbbc3-147"> [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="cbbc3-147"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="cbbc3-148"> [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="cbbc3-148"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="cbbc3-149"> [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="cbbc3-149"> [Statements](../../../../visual-basic/language-reference/statements/index.md)</span></span>
