---
title: Der Name "<namespacename>" im Stammnamespace "<fullnamespacename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 48e020cb74641279a4f402e47034514d78dfc4fc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160209"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="67c8c-102">BC40039: \<namespacename> der Name im Root-Namespace \<fullnamespacename> ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="67c8c-102">BC40039: Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>

<span data-ttu-id="67c8c-103">Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , aber ein Element des Stamm Namespace namens beginnt mit einem Unterstrich ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="67c8c-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>

 <span data-ttu-id="67c8c-104">Ein Programmier Element kann einen oder mehrere Unterstriche enthalten, muss jedoch nicht mit einem Unterstrich beginnen, um mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel zu sein.</span><span class="sxs-lookup"><span data-stu-id="67c8c-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="67c8c-105">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="67c8c-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="67c8c-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="67c8c-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="67c8c-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="67c8c-107">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="67c8c-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="67c8c-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="67c8c-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="67c8c-109">By default, this message is a warning.</span></span> <span data-ttu-id="67c8c-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="67c8c-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="67c8c-111">**Fehler-ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="67c8c-111">**Error ID:** BC40039</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="67c8c-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="67c8c-112">To correct this error</span></span>

- <span data-ttu-id="67c8c-113">Wenn Sie CLS-Konformität benötigen, ändern Sie den Stamm Namespace Namen, damit keines seiner Elemente mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="67c8c-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>

- <span data-ttu-id="67c8c-114">Wenn der Namespace Name unverändert bleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus der Assembly, oder markieren Sie es als `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="67c8c-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="67c8c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67c8c-115">See also</span></span>

- [<span data-ttu-id="67c8c-116">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="67c8c-116">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="67c8c-117">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67c8c-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="67c8c-118">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="67c8c-118">-rootnamespace</span></span>](../../reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="67c8c-119">Seite „Anwendung“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c8c-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="67c8c-120">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="67c8c-120">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="67c8c-121">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67c8c-121">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
