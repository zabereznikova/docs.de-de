---
title: Name "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 06b20b4f61741f2174654d749df55c3c4348c547
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824623"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="85a63-102">Namen \<Membername > ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="85a63-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="85a63-103">Eine Assembly ist als markiert `<CLSCompliant(True)>` aber zur Verfügung stellt ein Element mit einem Namen, die mit einem Unterstrich beginnt (`_`).</span><span class="sxs-lookup"><span data-stu-id="85a63-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="85a63-104">Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, jedoch werden zur Einhaltung der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), es muss nicht mit einem Unterstrich beginnen.</span><span class="sxs-lookup"><span data-stu-id="85a63-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="85a63-105">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="85a63-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="85a63-106">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="85a63-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="85a63-107">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="85a63-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="85a63-108">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="85a63-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="85a63-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="85a63-109">By default, this message is a warning.</span></span> <span data-ttu-id="85a63-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="85a63-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="85a63-111">**Fehler-ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="85a63-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85a63-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="85a63-112">To correct this error</span></span>  
  
-   <span data-ttu-id="85a63-113">Wenn Sie die Kontrolle über den Quellcode haben, ändern Sie den Namen des Members, damit er nicht mit einem Unterstrich beginnt.</span><span class="sxs-lookup"><span data-stu-id="85a63-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
-   <span data-ttu-id="85a63-114">Wenn Sie der Namen des Members unveränderte verbleiben müssen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus seiner Definition oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="85a63-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="85a63-115">Sie können weiterhin markieren Sie die Assembly als `<CLSCompliant(True)>`.</span><span class="sxs-lookup"><span data-stu-id="85a63-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a63-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85a63-116">See also</span></span>

- [<span data-ttu-id="85a63-117">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="85a63-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="85a63-118">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="85a63-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
