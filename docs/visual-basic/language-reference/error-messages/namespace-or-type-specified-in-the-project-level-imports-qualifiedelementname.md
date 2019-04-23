---
title: Der in Imports '<qualifiedelementname>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 105fa8da838938d13022c210c1f65cdafd251003
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308483"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="f6695-102">Namespace oder Typ angegeben werden, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="f6695-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="f6695-103">Namespace oder Typ angegeben werden, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f6695-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="f6695-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält.</span><span class="sxs-lookup"><span data-stu-id="f6695-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="f6695-105">Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="f6695-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="f6695-106">Eine Import-Eigenschaft eines Projekts gibt ein enthaltendes Element, das entweder nicht gefunden werden kann, oder keine definiert `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="f6695-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="f6695-107">Ein *, das Element enthält* -Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein kann.</span><span class="sxs-lookup"><span data-stu-id="f6695-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="f6695-108">Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="f6695-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="f6695-109">Importieren von dient zu Ihrem Code, um Namespaces oder Typs auf Member zuzugreifen, ohne sie zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="f6695-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="f6695-110">Ihr Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f6695-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="f6695-111">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f6695-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="f6695-112">Wenn der Compiler das angegebene Element enthält, nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6695-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="f6695-113">Wenn das Element gefunden wird, das Element macht aber keine `Public` Elemente, und klicken Sie dann auf keinen Verweis kann erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="f6695-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="f6695-114">In beiden Fällen ist es ohne Bedeutung für das Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f6695-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="f6695-115">Sie verwenden die **Projekt-Designer** zu importierenden Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="f6695-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="f6695-116">Verwenden der **importierte Namespaces** Teil der **Verweise** Seite.</span><span class="sxs-lookup"><span data-stu-id="f6695-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="f6695-117">Erhalten Sie auf die **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** Symbol **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f6695-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="f6695-118">**Fehler-ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="f6695-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6695-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f6695-119">To correct this error</span></span>  
  
1. <span data-ttu-id="f6695-120">Öffnen der **Projekt-Designer** und wechseln Sie zu der **Verweis** Seite.</span><span class="sxs-lookup"><span data-stu-id="f6695-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="f6695-121">In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f6695-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="f6695-122">Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="f6695-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6695-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6695-123">See also</span></span>

- [<span data-ttu-id="f6695-124">Seite „Verweise“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6695-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="f6695-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f6695-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="f6695-126">Public</span><span class="sxs-lookup"><span data-stu-id="f6695-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f6695-127">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6695-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="f6695-128">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="f6695-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
