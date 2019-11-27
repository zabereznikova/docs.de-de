---
title: Benennungskonventionen
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347312"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="f8e5c-102">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8e5c-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="f8e5c-103">Wenn Sie ein Element in der Visual Basic Anwendung benennen, muss das erste Zeichen dieses Namens ein alphabetisches Zeichen oder ein Unterstrich sein.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="f8e5c-104">Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen, nicht mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="f8e5c-105">Die folgenden Vorschläge gelten für die Benennung.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="f8e5c-106">Beginnen Sie jedes einzelne Wort in einem Namen mit einem Großbuchstaben, wie in `FindLastRecord` und `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="f8e5c-107">Beginnen Sie Funktions-und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="f8e5c-108">Beginnen Sie Klassen-, Struktur-, Modul-und Eigenschaftsnamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="f8e5c-109">Starten Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem Substantiv Ausdruck, wie z. b. `IComponent`, oder mit einem Adjektiv, das das Verhalten der Schnittstelle beschreibt, wie `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="f8e5c-110">Verwenden Sie den Unterstrich nicht, und verwenden Sie Abkürzungen sparsam, da Abkürzungen Verwirrung verursachen können.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="f8e5c-111">Beginnen Sie die Namen von Ereignis Handlern mit einem Substantiv, das den Ereignistyp, gefolgt vom Suffix "`EventHandler`", wie in "`MouseEventHandler`" beschreibt.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="f8e5c-112">Fügen Sie in Namen von Ereignis Argument Klassen das Suffix "`EventArgs`" ein.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="f8e5c-113">Wenn ein Ereignis das Konzept "Before" oder "After" hat, verwenden Sie ein Suffix in der Vergangenheit oder Vergangenheitsform, wie in "`ControlAdd`" oder "`ControlAdded`".</span><span class="sxs-lookup"><span data-stu-id="f8e5c-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="f8e5c-114">Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen, um die namens Längen angemessen zu halten, z. b. "HTML" anstelle von "Hypertext Markup Language".</span><span class="sxs-lookup"><span data-stu-id="f8e5c-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="f8e5c-115">Im Allgemeinen ist es schwierig, Variablennamen mit mehr als 32 Zeichen auf einem Monitor zu lesen, der auf eine niedrige Auflösung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="f8e5c-116">Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung einheitlich sind.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="f8e5c-117">Das zufällige wechseln in ein Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="f8e5c-118">Vermeiden Sie die Verwendung von Namen in einem inneren Gültigkeitsbereich, die mit Namen in einem äußeren Gültigkeitsbereich identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="f8e5c-119">Fehler können auftreten, wenn auf die falsche Variable zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="f8e5c-120">Wenn zwischen einer Variablen und dem Schlüsselwort mit demselben Namen ein Konflikt auftritt, müssen Sie das Schlüsselwort identifizieren, indem Sie es der entsprechenden Typbibliothek vorangestellt haben.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="f8e5c-121">Wenn Sie z. b. eine Variable namens `Date`haben, können Sie die intrinsische `Date` Funktion nur durch Aufrufen von <xref:System.DateTime.Date%2A?displayProperty=nameWithType>verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8e5c-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e5c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8e5c-122">See also</span></span>

- [<span data-ttu-id="f8e5c-123">Schlüsselwörter als Elementnamen in Code</span><span class="sxs-lookup"><span data-stu-id="f8e5c-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [<span data-ttu-id="f8e5c-124">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="f8e5c-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="f8e5c-125">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="f8e5c-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="f8e5c-126">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="f8e5c-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="f8e5c-127">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8e5c-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
