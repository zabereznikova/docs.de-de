---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 33b60b2212d25737330dc93d7ba2715e4d5865b7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873707"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="cf7e4-102">Name "\<membername>" ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-102">Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="cf7e4-103">Eine Assembly ist als gekennzeichnet `<CLSCompliant(True)>` , macht jedoch einen Member mit einem Namen verfügbar, der mit einem Unterstrich beginnt ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="cf7e4-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="cf7e4-104">Ein Programmier Element kann ein oder mehrere Unterstriche enthalten, aber damit es mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf es nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="cf7e4-105">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e4-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="cf7e4-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="cf7e4-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="cf7e4-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="cf7e4-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-109">By default, this message is a warning.</span></span> <span data-ttu-id="cf7e4-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="cf7e4-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cf7e4-111">**Fehler-ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="cf7e4-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf7e4-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf7e4-112">To correct this error</span></span>  
  
- <span data-ttu-id="cf7e4-113">Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Elementnamen so, dass er nicht mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="cf7e4-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="cf7e4-114">Wenn der Elementname unverändert bleiben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie ihn als `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="cf7e4-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="cf7e4-115">Sie können die Assembly weiterhin als markieren `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="cf7e4-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7e4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf7e4-116">See also</span></span>

- [<span data-ttu-id="cf7e4-117">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="cf7e4-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="cf7e4-118">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf7e4-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
