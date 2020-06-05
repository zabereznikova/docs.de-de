---
title: Namenskonventionen
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
ms.openlocfilehash: 20531e379ddf9b93a278795e9b3c0eb91b47e077
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398343"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="0ab7e-102">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ab7e-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="0ab7e-103">Wenn Sie ein Element in der Visual Basic Anwendung benennen, muss das erste Zeichen dieses Namens ein alphabetisches Zeichen oder ein Unterstrich sein.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="0ab7e-104">Beachten Sie jedoch, dass Namen, die mit einem Unterstrich beginnen, nicht mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="0ab7e-105">Die folgenden Vorschläge gelten für die Benennung.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="0ab7e-106">Beginnen Sie jedes einzelne Wort in einem Namen mit einem Großbuchstaben, wie in `FindLastRecord` und `RedrawMyForm` .</span><span class="sxs-lookup"><span data-stu-id="0ab7e-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="0ab7e-107">Beginnen Sie Funktions-und Methodennamen mit einem Verb, wie in `InitNameArray` oder `CloseDialog` .</span><span class="sxs-lookup"><span data-stu-id="0ab7e-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="0ab7e-108">Beginnen Sie Klassen-, Struktur-, Modul-und Eigenschaftsnamen mit einem Substantiv, wie in `EmployeeName` oder `CarAccessory` .</span><span class="sxs-lookup"><span data-stu-id="0ab7e-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="0ab7e-109">Starten Sie Schnittstellennamen mit dem Präfix "I", gefolgt von einem Substantiv oder einem Substantiv-Ausdruck, wie `IComponent` , oder mit einem Adjektiv, das das Verhalten der Schnittstelle beschreibt, `IPersistable` z.b..</span><span class="sxs-lookup"><span data-stu-id="0ab7e-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="0ab7e-110">Verwenden Sie den Unterstrich nicht, und verwenden Sie Abkürzungen sparsam, da Abkürzungen Verwirrung verursachen können.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="0ab7e-111">Beginnen Sie die Namen von Ereignis Handlern mit einem Substantiv, das den Ereignistyp, gefolgt vom `EventHandler` Suffix "", beschreibt, wie in " `MouseEventHandler` ".</span><span class="sxs-lookup"><span data-stu-id="0ab7e-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="0ab7e-112">Fügen Sie in Namen von Ereignis Argument Klassen das `EventArgs` Suffix "" ein.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="0ab7e-113">Wenn ein Ereignis über das Konzept "Before" oder "After" verfügt, verwenden Sie ein Suffix in der Vergangenheit oder Vergangenheits Darstellung, wie in " `ControlAdd` " oder " `ControlAdded` ".</span><span class="sxs-lookup"><span data-stu-id="0ab7e-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="0ab7e-114">Verwenden Sie für lange oder häufig verwendete Begriffe Abkürzungen, um die namens Längen angemessen zu halten, z. b. "HTML" anstelle von "Hypertext Markup Language".</span><span class="sxs-lookup"><span data-stu-id="0ab7e-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="0ab7e-115">Im Allgemeinen ist es schwierig, Variablennamen mit mehr als 32 Zeichen auf einem Monitor zu lesen, der auf eine niedrige Auflösung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="0ab7e-116">Stellen Sie außerdem sicher, dass die Abkürzungen in der gesamten Anwendung einheitlich sind.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="0ab7e-117">Das zufällige wechseln in ein Projekt zwischen "HTML" und "Hypertext Markup Language" kann zu Verwirrung führen.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="0ab7e-118">Vermeiden Sie die Verwendung von Namen in einem inneren Gültigkeitsbereich, die mit Namen in einem äußeren Gültigkeitsbereich identisch sind.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="0ab7e-119">Fehler können auftreten, wenn auf die falsche Variable zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="0ab7e-120">Wenn zwischen einer Variablen und dem Schlüsselwort mit demselben Namen ein Konflikt auftritt, müssen Sie das Schlüsselwort identifizieren, indem Sie es der entsprechenden Typbibliothek vorangestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0ab7e-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="0ab7e-121">Wenn Sie z. b. eine Variable namens haben `Date` , können Sie die intrinsische `Date` Funktion nur durch Aufrufen von verwenden <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0ab7e-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab7e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ab7e-122">See also</span></span>

- [<span data-ttu-id="0ab7e-123">Schlüsselwörter als Elementnamen in Code</span><span class="sxs-lookup"><span data-stu-id="0ab7e-123">Keywords as Element Names in Code</span></span>](keywords-as-element-names-in-code.md)
- [<span data-ttu-id="0ab7e-124">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="0ab7e-124">Me, My, MyBase, and MyClass</span></span>](me-my-mybase-and-myclass.md)
- [<span data-ttu-id="0ab7e-125">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="0ab7e-125">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="0ab7e-126">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="0ab7e-126">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="0ab7e-127">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ab7e-127">Visual Basic Language Reference</span></span>](../../language-reference/index.md)
