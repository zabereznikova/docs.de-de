---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160235"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a><span data-ttu-id="1444b-102">BC40031: der Name \<membername> ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="1444b-102">BC40031: Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="1444b-103">Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , macht jedoch einen Member mit einem Namen verfügbar, der mit einem Unterstrich beginnt ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="1444b-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>

 <span data-ttu-id="1444b-104">Ein Programmier Element kann einen oder mehrere Unterstriche enthalten, muss jedoch nicht mit einem Unterstrich beginnen, um mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel zu sein.</span><span class="sxs-lookup"><span data-stu-id="1444b-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="1444b-105">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="1444b-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="1444b-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1444b-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1444b-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="1444b-107">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="1444b-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1444b-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="1444b-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="1444b-109">By default, this message is a warning.</span></span> <span data-ttu-id="1444b-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1444b-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="1444b-111">**Fehler-ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="1444b-111">**Error ID:** BC40031</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1444b-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1444b-112">To correct this error</span></span>

- <span data-ttu-id="1444b-113">Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Elementnamen so, dass er nicht mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="1444b-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>

- <span data-ttu-id="1444b-114">Wenn der Elementname unverändert bleiben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie ihn als `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="1444b-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="1444b-115">Sie können die Assembly weiterhin als markieren `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="1444b-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1444b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1444b-116">See also</span></span>

- [<span data-ttu-id="1444b-117">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="1444b-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="1444b-118">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1444b-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
