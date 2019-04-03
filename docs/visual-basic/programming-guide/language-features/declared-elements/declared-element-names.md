---
title: Namen deklarierter Elemente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814067"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="8381a-102">Namen deklarierter Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8381a-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="8381a-103">Jedem deklariertes Element hat einen Namen, die so genannte ein *Bezeichner*, wird der Code verwendet wird, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8381a-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8381a-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="8381a-104">Rules</span></span>  
 <span data-ttu-id="8381a-105">Ein Elementname in Visual Basic muss die folgenden Regeln beachten:</span><span class="sxs-lookup"><span data-stu-id="8381a-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
-   <span data-ttu-id="8381a-106">Es muss mit einem Buchstaben oder einem Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="8381a-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="8381a-107">Sie müssen nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="8381a-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="8381a-108">Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalstelle enthalten, wenn er mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="8381a-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="8381a-109">Es darf nicht mehr als 1023 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="8381a-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="8381a-110">Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge des vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="8381a-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="8381a-111">Das folgende Beispiel zeigt einige gültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="8381a-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="8381a-112">Das folgende Beispiel zeigt einige ungültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="8381a-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="8381a-113">Die erste enthält nur einen Unterstrich, das zweite Beispiel beginnt mit einer Dezimalstelle und das dritte enthält ein ungültiges Zeichen ($).</span><span class="sxs-lookup"><span data-stu-id="8381a-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="8381a-114">Elementnamen, die mit einem Unterstrich beginnen (`_`) ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS), damit eine Komponente nicht CLS-kompatiblem Code verwenden kann, die solchen Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="8381a-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="8381a-115">Allerdings ist ein Unterstrich in einer beliebigen anderen Position in einem Elementnamen CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="8381a-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="8381a-116">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="8381a-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="8381a-117">Ein praktischer Tipp sollten Ihren Namen und die Art des Elements immer noch eindeutig kennzeichnen so kurz wie möglich sein.</span><span class="sxs-lookup"><span data-stu-id="8381a-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="8381a-118">Dies verbessert die Lesbarkeit des Codes und die Länge und die Quelldatei Größe reduziert.</span><span class="sxs-lookup"><span data-stu-id="8381a-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="8381a-119">Andererseits, sollten Ihren Namen nicht so kurz sein, dass es nicht angemessen beschrieben werden, was das Element darstellt und wie Ihr Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="8381a-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="8381a-120">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="8381a-120">This is important for the readability of your code.</span></span> <span data-ttu-id="8381a-121">Wenn eine andere Person versucht, eine klare Vorstellung davon haben, oder wenn Sie sich an sind viel Zeit nach dessen Erstellung, können geeignete Elementnamen viel Zeit speichern.</span><span class="sxs-lookup"><span data-stu-id="8381a-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="8381a-122">Namen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="8381a-122">Escaped Names</span></span>  
 <span data-ttu-id="8381a-123">Im Allgemeinen ein Elementname darf nicht übereinstimmen eines reservierten von Visual Basic, wie z. B. Schlüsselwörter `Case` oder `Friend`.</span><span class="sxs-lookup"><span data-stu-id="8381a-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="8381a-124">Allerdings können Sie definieren eine *mit Escapezeichen versehen namens*, die durch eckige Klammern eingeschlossen wird (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="8381a-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="8381a-125">Ein Namen mit Escapezeichen kann alle Visual Basic-Schlüsselwort übereinstimmen, da jegliche Mehrdeutigkeit durch die Klammern.</span><span class="sxs-lookup"><span data-stu-id="8381a-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="8381a-126">Wenn Sie auf den Namen später in Ihrem Code verweisen, können Sie auch die eckigen Klammern.</span><span class="sxs-lookup"><span data-stu-id="8381a-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="8381a-127">Im Allgemeinen sollten Sie mit Escapezeichen versehene Namen verwenden nur dann, wenn:</span><span class="sxs-lookup"><span data-stu-id="8381a-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="8381a-128">Ihr Code wurde von einer früheren Version von Visual Basic migriert, die nicht das Schlüsselwort verwendet wird, als Namen reserviert, oder oder</span><span class="sxs-lookup"><span data-stu-id="8381a-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="8381a-129">Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="8381a-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="8381a-130">Andernfalls sollten Sie das Element umbenennen, wenn der Name mit einem Schlüsselwort in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="8381a-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="8381a-131">Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit hierzu.</span><span class="sxs-lookup"><span data-stu-id="8381a-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="8381a-132">Weitere Informationen finden Sie unter [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="8381a-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="8381a-133">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="8381a-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="8381a-134">Elementnamen in Visual Basic werden Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="8381a-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="8381a-135">Dies bedeutet, dass wenn der Compiler zwei Namen, die nur Groß-und Kleinschreibung unterscheiden vergleicht, werden mit demselben Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8381a-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="8381a-136">Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="8381a-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="8381a-137">Die common Language Runtime (CLR) wird jedoch die Groß-/Kleinschreibung Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8381a-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="8381a-138">Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="8381a-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="8381a-139">Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen.</span><span class="sxs-lookup"><span data-stu-id="8381a-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="8381a-140">Wenn Sie danach die Klasse erneut kompilieren, und ändern den Namen des Elements zu `abc`, die andere Assemblys, die Ihre Klasse verwenden können nicht mehr auf dieses Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8381a-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="8381a-141">Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8381a-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="8381a-142">Namen und Gebietsschemas</span><span class="sxs-lookup"><span data-stu-id="8381a-142">Names and Locales</span></span>  
 <span data-ttu-id="8381a-143">Vergleich von Namen wird unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="8381a-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="8381a-144">Wenn zwei Namen in einem Gebietsschema übereinstimmen, werden sie garantiert in allen Gebietsschemas entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8381a-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8381a-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8381a-145">See also</span></span>

- [<span data-ttu-id="8381a-146">Deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="8381a-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="8381a-147">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="8381a-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="8381a-148">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="8381a-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="8381a-149">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8381a-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
