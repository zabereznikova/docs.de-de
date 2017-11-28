---
title: "Namespace oder Typ angegeben, die in diesem Projekt auf Dokumentebene importiert &#39; &lt;qualifizierterelementname&gt;&#39; ist nicht &#39; t jeden öffentlichen Member enthalten oder kann nicht gefunden werden"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords: BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d0a164562524af239b3b130f681dbc6eff23814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="fad41-102">Namespace oder Typ angegeben, die in diesem Projekt auf Dokumentebene importiert &#39; &lt;qualifizierterelementname&gt;&#39; ist nicht &#39; t jeden öffentlichen Member enthalten oder kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="fad41-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="fad41-103">Namespace oder Typ angegeben, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="fad41-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="fad41-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.</span><span class="sxs-lookup"><span data-stu-id="fad41-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="fad41-105">Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="fad41-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="fad41-106">Eine Import-Eigenschaft eines Projekts gibt ein enthaltendes Element, das entweder nicht gefunden werden oder keine definiert `Public` Elemente.</span><span class="sxs-lookup"><span data-stu-id="fad41-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="fad41-107">Ein *mit Element* möglich, einen Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fad41-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="fad41-108">Das enthaltende Element enthält Elemente, z. B. Variablen, Prozeduren oder andere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="fad41-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="fad41-109">Importieren von dient zum Code den Zugriff auf Member für Namespace oder Typ zu ermöglichen, ohne sie zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="fad41-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="fad41-110">Das Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fad41-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="fad41-111">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="fad41-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="fad41-112">Wenn der Compiler die angegebene enthaltende Element nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="fad41-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="fad41-113">Wenn das Element gefunden wird, aber das Element nicht macht `Public` Elemente, und klicken Sie dann auf kein Verweis erfolgreich sein kann.</span><span class="sxs-lookup"><span data-stu-id="fad41-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="fad41-114">In beiden Fällen ist es ohne Bedeutung, um das Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fad41-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="fad41-115">Verwenden Sie die **Projekt-Designer** an Elemente zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fad41-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="fad41-116">Verwenden der **importierte Namespaces** Teil der **Verweise** Seite.</span><span class="sxs-lookup"><span data-stu-id="fad41-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="fad41-117">Sie können zum Abrufen der **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** Symbol in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="fad41-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="fad41-118">**Fehler-ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="fad41-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fad41-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fad41-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="fad41-120">Öffnen der **Projekt-Designer** und wechseln Sie zu der **Verweis** Seite.</span><span class="sxs-lookup"><span data-stu-id="fad41-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="fad41-121">In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="fad41-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="fad41-122">Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="fad41-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad41-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fad41-123">See Also</span></span>  
 [<span data-ttu-id="fad41-124">Seite „Verweise“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fad41-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="fad41-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="fad41-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="fad41-126">Public</span><span class="sxs-lookup"><span data-stu-id="fad41-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="fad41-127">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fad41-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="fad41-128">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="fad41-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
