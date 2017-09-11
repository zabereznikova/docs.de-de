---
title: "Namespace oder Typ angegeben werden, in der auf Projektebene Imports&quot;&lt;Qualifiedelementname&gt;&quot; enthält keine öffentlichen Member oder kann nicht gefunden werden | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 301e2bd419f0b4723ff76c2bdd2187c4c412e174
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="1eeb7-102">Namespace oder Typ angegeben werden, in der auf Projektebene Imports'&lt;Qualifiedelementname&gt;' enthält keine öffentlichen Member oder kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="1eeb7-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="1eeb7-103">Namespace oder Typ angegeben werden, in der auf Projektebene Imports'\<Qualifiedelementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="1eeb7-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="1eeb7-105">Stellen Sie sicher, dass der Aliasname keine weiteren Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="1eeb7-106">Eine Import-Eigenschaft eines Projekts gibt ein Containerelement, das entweder nicht gefunden werden oder ist nicht definiert `Public` Elemente.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="1eeb7-107">Ein *Element mit* kann ein Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="1eeb7-108">Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere enthaltende Elemente.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="1eeb7-109">Importieren von dient dem Code auf Namespace oder Typ Member zu ermöglichen, ohne sie qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="1eeb7-110">Das Projekt müssen auch einen Verweis auf den Namespace oder Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="1eeb7-111">Weitere Informationen finden Sie unter "Importieren von enthaltenden Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="1eeb7-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="1eeb7-112">Wenn der Compiler das angegebene enthaltende Element nicht finden kann, dann nicht Verweise aufgelöst werden kann, die es verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="1eeb7-113">Wenn das Element gefunden wird, aber das Element alle macht `Public` Elemente, und klicken Sie dann auf kein Verweis kann erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="1eeb7-114">In beiden Fällen ist es sinnlos, das Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="1eeb7-115">Verwenden Sie die **Projekt-Designer** zu importierenden Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="1eeb7-116">Verwenden der **importierte Namespaces** Teil der **Verweise** Seite.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="1eeb7-117">Sie erreichen die **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** -Symbol in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="1eeb7-118">**Fehler-ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="1eeb7-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1eeb7-119">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1eeb7-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="1eeb7-120">Öffnen Sie die **Projekt-Designer** und wechseln Sie in der **Verweis** Seite.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="1eeb7-121">In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus dem Projekt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="1eeb7-122">Überprüfen, ob es sich bei das enthaltende Element verfügbar macht, muss mindestens `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="1eeb7-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eeb7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eeb7-123">See Also</span></span>  
 <span data-ttu-id="1eeb7-124">[Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="1eeb7-124">[References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="1eeb7-125"> [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="1eeb7-125"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="1eeb7-126"> [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="1eeb7-126"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="1eeb7-127"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="1eeb7-127"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="1eeb7-128"> [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="1eeb7-128"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
