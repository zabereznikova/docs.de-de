---
title: Namen deklarierter Elemente (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22595eff2509d3954b3ce9d5038b19a681fbfbbe
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="83455-102">Namen deklarierter Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83455-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="83455-103">Jedem deklariertes Element hat einen Namen, so genannte ein *Bezeichner*, wird der Code dazu verwendet wird, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="83455-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="83455-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="83455-104">Rules</span></span>  
 <span data-ttu-id="83455-105">Ein Elementname in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] müssen die folgenden Regeln beachten:</span><span class="sxs-lookup"><span data-stu-id="83455-105">An element name in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="83455-106">Er muss mit einem alphabetischen Zeichen oder einem Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="83455-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="83455-107">Es darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.</span><span class="sxs-lookup"><span data-stu-id="83455-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="83455-108">Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalziffer enthalten, wenn er mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="83455-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="83455-109">Es darf nicht mehr als 1023 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="83455-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="83455-110">Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge des vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="83455-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="83455-111">Das folgende Beispiel zeigt einige gültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="83455-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="83455-112">Das folgende Beispiel zeigt einige ungültige Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="83455-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="83455-113">Die erste Zeile nur einen Unterstrich enthält, das zweite Beispiel beginnt mit einer Dezimalstelle, und die dritte Spalte enthält ein ungültiges Zeichen ($).</span><span class="sxs-lookup"><span data-stu-id="83455-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="83455-114">Elementnamen, die mit einem Unterstrich beginnen (`_`) sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS), damit eine Komponente nicht CLS-kompatiblem Code verwenden kann, die solche Namen definiert.</span><span class="sxs-lookup"><span data-stu-id="83455-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="83455-115">Allerdings ist ein Unterstrich in einer beliebigen anderen Position im Namen eines Elements CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="83455-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="83455-116">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="83455-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="83455-117">Ihren Namen sollten aus praktischen Gründen so kurz wie möglich werden immer noch eindeutig identifiziert die Art des Elements.</span><span class="sxs-lookup"><span data-stu-id="83455-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="83455-118">Dies verbessert die Lesbarkeit des Codes und reduziert die Größe des Zeile Länge und Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="83455-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="83455-119">Andererseits, sollte Ihr Name nicht so kurz sein, dass es nicht angemessen beschrieben werden, was das Element darstellt, und wie Sie im Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="83455-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="83455-120">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="83455-120">This is important for the readability of your code.</span></span> <span data-ttu-id="83455-121">Wenn eine andere Person versucht wird, zu verstehen, oder wenn Sie selbst an ihn sind sehr lange, nachdem Sie ihn geschrieben haben, können geeignete Elementnamen eine erhebliche Zeit speichern.</span><span class="sxs-lookup"><span data-stu-id="83455-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="83455-122">Namen mit Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="83455-122">Escaped Names</span></span>  
 <span data-ttu-id="83455-123">Im allgemeinen Namen eines Elements darf nicht entsprechen einem reservierten Schlüsselwort [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], wie z. B. `Case` oder `Friend`.</span><span class="sxs-lookup"><span data-stu-id="83455-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="83455-124">Allerdings können Sie definieren eine *mit Escapezeichen versehen Namen*, die durch Klammern eingeschlossen wird (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="83455-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="83455-125">Ein Namen mit Escapezeichen kann keinem [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Schlüsselwort, da jegliche Mehrdeutigkeit durch die Klammern.</span><span class="sxs-lookup"><span data-stu-id="83455-125">An escaped name can match any [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="83455-126">Die Klammern wird auch bei auf den Namen später in Ihrem Code verweisen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83455-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="83455-127">Im Allgemeinen sollten Sie Namen mit Escapesequenz verwenden nur, wenn:</span><span class="sxs-lookup"><span data-stu-id="83455-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="83455-128">Ihr Code wurde von einer früheren Version von migriert [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] , die nicht das Schlüsselwort verwendet wird, als ein Name reserviert oder</span><span class="sxs-lookup"><span data-stu-id="83455-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="83455-129">Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="83455-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="83455-130">Andernfalls sollten Sie das Element umbenennen, wenn dessen Name mit einem Schlüsselwort einen Konflikt verursacht.</span><span class="sxs-lookup"><span data-stu-id="83455-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="83455-131">Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit hierzu.</span><span class="sxs-lookup"><span data-stu-id="83455-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="83455-132">Weitere Informationen finden Sie unter [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="83455-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="83455-133">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="83455-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="83455-134">Elementnamen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="83455-134">Element names in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] are case-insensitive.</span></span> <span data-ttu-id="83455-135">Dies bedeutet, dass wenn der Compiler zwei Namen verglichen werden, die nur Groß-und Kleinschreibung unterscheiden, werden mit demselben Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="83455-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="83455-136">Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.</span><span class="sxs-lookup"><span data-stu-id="83455-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="83455-137">Allerdings verwendet die common Language Runtime (CLR) Bindung Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="83455-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="83455-138">Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="83455-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="83455-139">Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen.</span><span class="sxs-lookup"><span data-stu-id="83455-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="83455-140">Wenn Sie danach die Klasse erneut kompilieren und ändern den Namen des Elements um `abc`, die andere Assemblys, die Ihre Klasse verwenden können nicht mehr auf dieses Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="83455-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="83455-141">Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="83455-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="83455-142">Namen und Gebietsschemas</span><span class="sxs-lookup"><span data-stu-id="83455-142">Names and Locales</span></span>  
 <span data-ttu-id="83455-143">Vergleich von Namen wird unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="83455-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="83455-144">Wenn zwei Namen in einem Gebietsschema übereinstimmen, werden sie garantiert in allen Gebietsschemas entsprechen.</span><span class="sxs-lookup"><span data-stu-id="83455-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83455-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83455-145">See Also</span></span>  
 [<span data-ttu-id="83455-146">Deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="83455-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [<span data-ttu-id="83455-147">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="83455-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="83455-148">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="83455-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="83455-149">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="83455-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
