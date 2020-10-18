---
title: <membername> ist nicht CLS-kompatibel und darf in einer CLS-kompatiblen Schnittstelle nicht verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: aa7944e90857436553435ce783c0820770496a49
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159988"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="8857e-102">BC40033: nicht CLS-kompatibel \<membername> ist in einer CLS-kompatiblen Schnittstelle nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8857e-102">BC40033: Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>

<span data-ttu-id="8857e-103">Eine Eigenschaft, Prozedur oder ein Ereignis in einer Schnittstelle wird als gekennzeichnet, `<CLSCompliant(True)>` Wenn die Schnittstelle selbst als gekennzeichnet ist `<CLSCompliant(False)>` oder nicht markiert ist.</span><span class="sxs-lookup"><span data-stu-id="8857e-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="8857e-104">Damit eine Schnittstelle mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, müssen alle Mitglieder kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="8857e-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>

 <span data-ttu-id="8857e-105">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8857e-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8857e-106">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="8857e-106">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="8857e-107">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8857e-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="8857e-108">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="8857e-108">By default, this message is a warning.</span></span> <span data-ttu-id="8857e-109">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8857e-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="8857e-110">**Fehler-ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="8857e-110">**Error ID:** BC40033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8857e-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8857e-111">To correct this error</span></span>

- <span data-ttu-id="8857e-112">Wenn Sie CLS-Kompatibilität benötigen und die Kontrolle über den Quellcode der Schnittstelle haben, markieren Sie die Schnittstelle so, als `<CLSCompliant(True)>` ob alle zugehörigen Member kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8857e-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>

- <span data-ttu-id="8857e-113">Wenn Sie CLS-Kompatibilität benötigen und keine Kontrolle über den Quellcode der Schnittstelle haben, oder wenn er nicht als kompatibel eingestuft wird, definieren Sie diesen Member in einer anderen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8857e-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>

- <span data-ttu-id="8857e-114">Wenn Sie möchten, dass dieser Member in der aktuellen Schnittstelle verbleibt, entfernen Sie <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie Sie als `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="8857e-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8857e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8857e-115">See also</span></span>

- [<span data-ttu-id="8857e-116">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8857e-116">Interface Statement</span></span>](../statements/interface-statement.md)
