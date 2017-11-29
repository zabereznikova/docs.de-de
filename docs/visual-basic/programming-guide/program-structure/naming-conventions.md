---
title: "Benennungskonventionen in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a59139b57568810de80de764388eeffa5f8d7ac9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="c2d4d-102">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2d4d-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="c2d4d-103">Wenn Sie ein Element in Visual Basic-Anwendung benennen, muss das erste Zeichen des Namens ein alphabetisches Zeichen oder ein Unterstrich sein.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="c2d4d-104">Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen nicht mit kompatibel sind die [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="c2d4d-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="c2d4d-105">Die folgenden Vorschläge gelten für die Benennung.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="c2d4d-106">Jedes einzelne Wort in einem Namen mit einem Großbuchstaben beginnen, wie in `FindLastRecord` und `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="c2d4d-107">BEGIN-Funktion und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="c2d4d-108">BEGIN-Klasse, Struktur, Modul und Eigenschaftennamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="c2d4d-109">Beginnen Sie Schnittstellennamen mit dem Präfix "I", gefolgt von ein Nomen oder ein nominaler Ausdruck, z. B. `IComponent`, oder mit einem Adjektiv, beschreibt das Schnittstellenverhalten, z. B. `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="c2d4d-110">Keine des Unterstrich, und nutzen verwenden Sie Abkürzungen sparsam und nur dann, da Abkürzungen zu Verwirrung führen können.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="c2d4d-111">Beginnen Sie Ereignishandlernamen mit einem Nomen beschreibt den Typ des Ereignisses, gefolgt von der "`EventHandler`"-Suffix enthält, wie in"`MouseEventHandler`".</span><span class="sxs-lookup"><span data-stu-id="c2d4d-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="c2d4d-112">Namen von Ereignisargumentklassen, enthalten die "`EventArgs`" Suffix.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="c2d4d-113">Wenn ein Ereignis ein Konzept von "before" oder "after" aufweist, verwenden Sie ein Suffix in Gegenwarts- oder Vergangenheitsform, wie in "`ControlAdd`"oder"`ControlAdded`".</span><span class="sxs-lookup"><span data-stu-id="c2d4d-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="c2d4d-114">Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen um Namen Längen angebracht ist, behalten Sie z. B. "HTML", anstelle von "Hypertext Markup Language".</span><span class="sxs-lookup"><span data-stu-id="c2d4d-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="c2d4d-115">Im Allgemeinen sind Variablennamen, die größer als 32 Zeichen schwer zu lesen, auf einem Bildschirm mit niedriger Auflösung.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="c2d4d-116">Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="c2d4d-117">Wechseln nach dem Zufallsprinzip in einem Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="c2d4d-118">Vermeiden Sie Namen in einem inneren Gültigkeitsbereich, die den Namen in einem äußeren Gültigkeitsbereich identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="c2d4d-119">Fehler können auftreten, wenn die falsche Variable zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="c2d4d-120">Wenn ein Konflikt zwischen einer Variablen und das Schlüsselwort mit dem gleichen Namen ausgeführt wird, müssen Sie das Schlüsselwort es mit der entsprechenden Typbibliothek abgrenzen, indem Sie identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="c2d4d-121">Angenommen, Sie haben eine Variable namens `Date`, können Sie die systeminterne Funktion `Date` Funktion nur über einen Aufruf <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2d4d-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d4d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2d4d-122">See Also</span></span>  
 [<span data-ttu-id="c2d4d-123">Schlüsselwörter als Elementnamen in Code</span><span class="sxs-lookup"><span data-stu-id="c2d4d-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [<span data-ttu-id="c2d4d-124">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="c2d4d-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="c2d4d-125">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="c2d4d-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="c2d4d-126">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="c2d4d-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="c2d4d-127">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2d4d-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
