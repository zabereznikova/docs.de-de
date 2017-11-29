---
title: "Namespace oder Typ angegeben, in die Importe &#39; &lt;qualifizierterelementname&gt;&#39; ist nicht &#39; t jeden öffentlichen Member enthalten oder kann nicht gefunden werden"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords: BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="6968a-102">Namespace oder Typ angegeben, in die Importe &#39; &lt;qualifizierterelementname&gt;&#39; ist nicht &#39; t jeden öffentlichen Member enthalten oder kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="6968a-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="6968a-103">Namespace oder Typ angegeben, in die Importe\<qualifizierter_elementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="6968a-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="6968a-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält.</span><span class="sxs-lookup"><span data-stu-id="6968a-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="6968a-105">Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="6968a-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="6968a-106">Ein `Imports` Anweisung gibt ein enthaltendes Element, das entweder nicht gefunden werden oder keine definiert `Public` Elemente.</span><span class="sxs-lookup"><span data-stu-id="6968a-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="6968a-107">Ein *mit Element* möglich, einen Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration.</span><span class="sxs-lookup"><span data-stu-id="6968a-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="6968a-108">Das enthaltende Element enthält Elemente, z. B. Variablen, Prozeduren oder andere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="6968a-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="6968a-109">Importieren von dient zum Code den Zugriff auf Member für Namespace oder Typ zu ermöglichen, ohne sie zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="6968a-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="6968a-110">Das Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6968a-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="6968a-111">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="6968a-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="6968a-112">Wenn der Compiler die angegebene enthaltende Element nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="6968a-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="6968a-113">Wenn das Element gefunden wird, aber das Element nicht macht `Public` Elemente, und klicken Sie dann auf kein Verweis erfolgreich sein kann.</span><span class="sxs-lookup"><span data-stu-id="6968a-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="6968a-114">In beiden Fällen ist es ohne Bedeutung, um das Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6968a-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="6968a-115">Sollten Sie bedenken, wenn Sie ein enthaltendes Element importieren und ein Importalias zuweisen, dann Sie Importalias nicht verwenden, um ein anderes Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6968a-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="6968a-116">Der folgende Code generiert einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="6968a-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="6968a-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="6968a-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="6968a-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="6968a-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="6968a-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="6968a-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="6968a-120">**Fehler-ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="6968a-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6968a-121">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6968a-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="6968a-122">Stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="6968a-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="6968a-123">Stellen Sie sicher, dass die Spezifikation des enthaltenden Elements Importalias bereits ein anderer Import nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6968a-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="6968a-124">Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="6968a-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6968a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6968a-125">See Also</span></span>  
 [<span data-ttu-id="6968a-126">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="6968a-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="6968a-127">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6968a-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="6968a-128">Public</span><span class="sxs-lookup"><span data-stu-id="6968a-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="6968a-129">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6968a-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="6968a-130">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="6968a-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
