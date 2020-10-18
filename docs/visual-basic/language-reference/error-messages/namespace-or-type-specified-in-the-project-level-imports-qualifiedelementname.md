---
title: Der in Imports '<qualifiedelementname>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 54ee046cda998be8bd70e531918d6ab2a67d0494
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160118"
---
# <a name="bc40057-namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="53a64-102">BC40057: der Namespace oder Typ, der in den Importen auf Projektebene angegeben ist, \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="53a64-102">BC40057: Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="53a64-103">Der in den Importen auf Projektebene angegebene Namespace oder Typ \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="53a64-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="53a64-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.</span><span class="sxs-lookup"><span data-stu-id="53a64-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="53a64-105">Stellen Sie sicher, dass der Alias Name keine anderen Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="53a64-105">Make sure the alias name doesn't contain other aliases.</span></span>

 <span data-ttu-id="53a64-106">Eine Import-Eigenschaft eines Projekts gibt ein enthaltende Element an, das entweder nicht gefunden werden kann oder keine Member definiert `Public` .</span><span class="sxs-lookup"><span data-stu-id="53a64-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

 <span data-ttu-id="53a64-107">Ein *enthaltende Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="53a64-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="53a64-108">Das enthaltende Element enthält Member, z. b. Variablen, Prozeduren oder andere enthaltende Elemente.</span><span class="sxs-lookup"><span data-stu-id="53a64-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

 <span data-ttu-id="53a64-109">Der Zweck des Importierens besteht darin, dass Ihr Code auf Namespaces oder Typmember zugreifen kann, ohne Sie qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="53a64-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="53a64-110">Das Projekt muss möglicherweise auch einen Verweis auf den Namespace oder den Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="53a64-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="53a64-111">Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="53a64-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

 <span data-ttu-id="53a64-112">Wenn der Compiler das angegebene enthaltende Element nicht finden kann, kann er keine Verweise auflösen, die ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="53a64-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="53a64-113">Wenn das-Element gefunden wird, aber das-Element keine Member verfügbar macht `Public` , kann kein Verweis erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="53a64-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="53a64-114">In beiden Fällen ist es bedeutungslos, das-Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="53a64-114">In either case it is meaningless to import the element.</span></span>

 <span data-ttu-id="53a64-115">Verwenden Sie den **Projekt-Designer** , um die zu importierenden Elemente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="53a64-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="53a64-116">Verwenden Sie den Abschnitt **importierte Namespaces** der Seite **Verweise** .</span><span class="sxs-lookup"><span data-stu-id="53a64-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="53a64-117">Sie können zum Projekt- **Designer** gelangen, indem Sie in **Projektmappen-Explorer**auf das Symbol " **mein Projekt** " doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="53a64-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>

 <span data-ttu-id="53a64-118">**Fehler-ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="53a64-118">**Error ID:** BC40057</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="53a64-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="53a64-119">To correct this error</span></span>

1. <span data-ttu-id="53a64-120">Öffnen Sie den **Projekt-Designer** , und wechseln Sie zur Seite **Verweis** .</span><span class="sxs-lookup"><span data-stu-id="53a64-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>

2. <span data-ttu-id="53a64-121">Überprüfen Sie im Abschnitt **importierte Namespaces** , ob auf das enthaltende Element von Ihrem Projekt aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="53a64-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>

3. <span data-ttu-id="53a64-122">Vergewissern Sie sich, dass das enthaltende Element mindestens einen Member verfügbar macht `Public` .</span><span class="sxs-lookup"><span data-stu-id="53a64-122">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="53a64-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53a64-123">See also</span></span>

- [<span data-ttu-id="53a64-124">Seite "Verweise", Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53a64-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="53a64-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="53a64-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="53a64-126">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="53a64-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="53a64-127">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53a64-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="53a64-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="53a64-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
