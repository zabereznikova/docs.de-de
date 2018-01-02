---
title: Namen &lt;Namespacename&gt; im Stammnamespace &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3a89f8cfe4038a81002777886de1155bea72ba22
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a><span data-ttu-id="062b8-102">Namen &lt;Namespacename&gt; im Stammnamespace &lt;Fullnamespacename&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="062b8-102">Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="062b8-103">Eine Assembly ist als markiert `<CLSCompliant(True)>`, aber ein Element von der stammnamespacename beginnt mit einem Unterstrich (`_`).</span><span class="sxs-lookup"><span data-stu-id="062b8-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="062b8-104">Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch werden zum Einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), es muss nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="062b8-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="062b8-105">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="062b8-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="062b8-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="062b8-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="062b8-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="062b8-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="062b8-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="062b8-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="062b8-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="062b8-109">By default, this message is a warning.</span></span> <span data-ttu-id="062b8-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="062b8-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="062b8-111">**Fehler-ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="062b8-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="062b8-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="062b8-112">To correct this error</span></span>  
  
-   <span data-ttu-id="062b8-113">Wenn Sie CLS-Kompatibilität erforderlich ist, werden ändern Sie der Name des Stammnamespaces, sodass keines ihrer Elemente mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="062b8-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
-   <span data-ttu-id="062b8-114">Wenn der Name des Namespaces unverändert bleiben muss, entfernen Sie die <xref:System.CLSCompliantAttribute> aus der Assembly oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="062b8-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062b8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="062b8-115">See Also</span></span>  
 [<span data-ttu-id="062b8-116">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="062b8-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="062b8-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="062b8-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="062b8-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="062b8-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [<span data-ttu-id="062b8-119">Seite „Anwendung“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="062b8-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="062b8-120">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="062b8-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="062b8-121">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="062b8-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 
