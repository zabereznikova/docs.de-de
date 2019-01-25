---
title: Nicht-CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: c837065d2d448fc2523cfbd18efac962445f8bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627694"
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="8b8c4-102">Nicht-CLS-kompatible &lt;Membername&gt; ist in einer CLS-kompatiblen Schnittstelle nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="8b8c4-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="8b8c4-103">Eine Eigenschaft, Prozedur oder das Ereignis in einer Schnittstelle als RuntimeCompatibility `<CLSCompliant(True)>` bei die Schnittstelle selbst als RuntimeCompatibility `<CLSCompliant(False)>` oder überhaupt nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="8b8c4-104">Für eine Schnittstelle zum Einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), alle seine Member müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="8b8c4-105">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8b8c4-106">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="8b8c4-107">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="8b8c4-108">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-108">By default, this message is a warning.</span></span> <span data-ttu-id="8b8c4-109">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8b8c4-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8b8c4-110">**Fehler-ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="8b8c4-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b8c4-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8b8c4-111">To correct this error</span></span>  
  
-   <span data-ttu-id="8b8c4-112">Wenn Sie CLS-Kompatibilität benötigen und Kontrolle über den Quellcode für die Schnittstelle, markieren Sie die Schnittstelle als `<CLSCompliant(True)>` Wenn allen zugehörigen Membern kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="8b8c4-113">Definieren Sie Wenn Sie CLS-Kompatibilität benötigen und haben keine Kontrolle über den Quellcode für die Schnittstelle, oder wenn dies nicht zutrifft, kompatibel sein müssen, dieses Elements in eine andere Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="8b8c4-114">Wenn Sie dieses Element in der aktuellen Schnittstelle verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="8b8c4-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8c4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b8c4-115">See also</span></span>
- [<span data-ttu-id="8b8c4-116">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8b8c4-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

