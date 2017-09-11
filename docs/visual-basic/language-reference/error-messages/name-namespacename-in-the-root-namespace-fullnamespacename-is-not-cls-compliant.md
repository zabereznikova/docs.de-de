---
title: Namen &lt;Namespacename&gt; im Namespace Root &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
dev_langs:
- VB
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
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
ms.openlocfilehash: 0d31657a958581b91cb448b78b8f55f8aadfe7c9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="75bbf-102">Namen &lt;Namespacename&gt; im Namespace Root &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="75bbf-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="75bbf-103">Eine Assembly ist als markiert `<CLSCompliant(True)>`, aber ein Element der Name des Stammnamespaces beginnt mit einem Unterstrich (`_`).</span><span class="sxs-lookup"><span data-stu-id="75bbf-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="75bbf-104">Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch zum kompatibel sein, mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), es muss nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="75bbf-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="75bbf-105">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="75bbf-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="75bbf-106">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="75bbf-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="75bbf-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="75bbf-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="75bbf-108">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="75bbf-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="75bbf-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="75bbf-109">By default, this message is a warning.</span></span> <span data-ttu-id="75bbf-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="75bbf-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="75bbf-111">**Fehler-ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="75bbf-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="75bbf-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="75bbf-112">To correct this error</span></span>  
  
-   <span data-ttu-id="75bbf-113">Wenn Sie CLS-Kompatibilität erforderlich ist, Ändern der Name des Stammnamespaces, sodass keines seiner Elemente mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="75bbf-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="75bbf-114">Wenn der Name des Namespaces unverändert bleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>aus der Assembly, oder markieren Sie es als `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="75bbf-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bbf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75bbf-115">See Also</span></span>  
 <span data-ttu-id="75bbf-116">[Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="75bbf-116">[Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="75bbf-117"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="75bbf-117"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="75bbf-118"> [/ RootNamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span><span class="sxs-lookup"><span data-stu-id="75bbf-118"> [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md) </span></span>  
<span data-ttu-id="75bbf-119"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="75bbf-119"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="75bbf-120"> [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="75bbf-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="75bbf-121"> [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="75bbf-121"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="75bbf-122"> [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="75bbf-122"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
