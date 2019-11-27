---
title: Declared Element Names
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
ms.openlocfilehash: e8620517b934a5f1a97ea25c5a94c8b932bb47b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345432"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="f4eda-102">Namen deklarierter Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4eda-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="f4eda-103">Jedes deklarierte Element weist einen Namen auf, der auch als *Bezeichner*bezeichnet wird. Dies ist der Inhalt, den der Code verwendet, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f4eda-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="f4eda-104">Rules</span></span>  
 <span data-ttu-id="f4eda-105">Für einen Elementnamen in Visual Basic müssen die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="f4eda-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="f4eda-106">Er muss mit einem alphabetischen Zeichen oder einem Unterstrich (`_`) beginnen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="f4eda-107">Sie darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4eda-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="f4eda-108">Er muss mindestens ein alphabetisches Zeichen oder eine Dezimal Ziffer enthalten, wenn er mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="f4eda-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="f4eda-109">Er darf nicht mehr als 1023 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="f4eda-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="f4eda-110">Die Längen Beschränkung von 1023 Zeichen gilt auch für die gesamte Zeichenfolge eines voll qualifizierten Namens, z. b. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="f4eda-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="f4eda-111">Das folgende Beispiel zeigt einige gültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="f4eda-112">Das folgende Beispiel zeigt einige ungültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="f4eda-113">Der erste enthält nur einen Unterstrich, der zweite beginnt mit einer Dezimal Ziffer, das dritte enthält ein ungültiges Zeichen ($).</span><span class="sxs-lookup"><span data-stu-id="f4eda-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="f4eda-114">Element Namen, die mit einem Unterstrich (`_`) beginnen, sind nicht Teil der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die solche Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="f4eda-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="f4eda-115">Ein Unterstrich an einer beliebigen anderen Position in einem Elementnamen ist jedoch CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f4eda-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="f4eda-116">Namens Längen Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f4eda-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="f4eda-117">Als praktische Angelegenheit sollte Ihr Name so kurz wie möglich sein, während er die Art des Elements eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f4eda-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="f4eda-118">Dadurch wird die Lesbarkeit des Codes verbessert, und die Zeilen-und Quelldatei Größe wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="f4eda-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="f4eda-119">Auf der anderen Seite sollte Ihr Name nicht so kurz sein, dass er nicht genau beschreibt, was das Element darstellt und wie der Code es verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4eda-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="f4eda-120">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="f4eda-120">This is important for the readability of your code.</span></span> <span data-ttu-id="f4eda-121">Wenn eine andere Person versucht, dies zu verstehen, oder wenn Sie sich nach dem verfassen einen langen Zeitraum ansehen, können geeignete Elementnamen einen beträchtlichen Zeitraum sparen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="f4eda-122">Namens Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="f4eda-122">Escaped Names</span></span>  
 <span data-ttu-id="f4eda-123">Im Allgemeinen darf ein Elementname keinem der Schlüsselwörter entsprechen, die von Visual Basic reserviert sind, z. b. `Case` oder `Friend`.</span><span class="sxs-lookup"><span data-stu-id="f4eda-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="f4eda-124">Sie können jedoch einen *Namen*mit Escapezeichen definieren, der in eckige Klammern (`[ ]`) eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f4eda-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="f4eda-125">Ein Name mit Escapezeichen kann mit einem beliebigen Visual Basic Schlüsselwort identisch sein, da die Klammern jegliche Mehrdeutigkeit</span><span class="sxs-lookup"><span data-stu-id="f4eda-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="f4eda-126">Sie verwenden die Klammern auch, wenn Sie später in Ihrem Code auf den Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="f4eda-127">Im Allgemeinen sollten Sie Namen mit Escapezeichen nur dann verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="f4eda-127">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="f4eda-128">Der Code wurde von einer früheren Version von Visual Basic migriert, die das Schlüsselwort nicht als Name reserviert hat. noch</span><span class="sxs-lookup"><span data-stu-id="f4eda-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="f4eda-129">Sie arbeiten mit Code, der in einer anderen Sprache geschrieben ist, in der das angegebene Schlüsselwort nicht reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4eda-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="f4eda-130">Andernfalls sollten Sie das Umbenennen des Elements in Erwägung gezogen, wenn der Name mit einem Schlüsselwort in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="f4eda-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="f4eda-131">Die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) bietet eine einfache Möglichkeit, dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="f4eda-132">Weitere Informationen finden Sie unter [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f4eda-132">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="f4eda-133">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="f4eda-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="f4eda-134">Bei Element Namen in Visual Basic wird Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="f4eda-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="f4eda-135">Dies bedeutet Folgendes: Wenn der Compiler zwei Namen vergleicht, die sich nur in alphabetischer Schreibweise unterscheiden, interpretiert er Sie als denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="f4eda-136">Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="f4eda-137">Allerdings verwendet die Common Language Runtime (CLR) die Groß-/Kleinschreibung unterscheidende Bindung.</span><span class="sxs-lookup"><span data-stu-id="f4eda-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="f4eda-138">Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="f4eda-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="f4eda-139">Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="f4eda-140">Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc`ändern, können die anderen Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4eda-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="f4eda-141">Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f4eda-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="f4eda-142">Namen und Gebiets Schemas</span><span class="sxs-lookup"><span data-stu-id="f4eda-142">Names and Locales</span></span>  
 <span data-ttu-id="f4eda-143">Der Vergleich von Namen ist unabhängig vom Gebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="f4eda-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="f4eda-144">Wenn zwei Namen in einem Gebiets Schema vorliegen, entsprechen Sie garantiert allen Gebiets Schemas.</span><span class="sxs-lookup"><span data-stu-id="f4eda-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4eda-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4eda-145">See also</span></span>

- [<span data-ttu-id="f4eda-146">Deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="f4eda-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="f4eda-147">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="f4eda-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="f4eda-148">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="f4eda-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="f4eda-149">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="f4eda-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
