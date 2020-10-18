---
title: <classname> ist nicht CLS-kompatibel, da die <interfacename>-Schnittstelle, von der geerbt wird, nicht CLS-kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 936bc78d87613a8492347df0f65688bbef6e2ca4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163180"
---
# <a name="bc40029-classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a><span data-ttu-id="36e8b-102">BC40029: " \<classname> " ist nicht CLS-kompatibel, weil die Schnittstelle "", die \<interfacename> Sie implementiert, nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="36e8b-102">BC40029: '\<classname>' is not CLS-compliant because the interface '\<interfacename>' it implements is not CLS-compliant</span></span>

<span data-ttu-id="36e8b-103">Eine Klasse oder Schnittstelle wird als `<CLSCompliant(True)>` gekennzeichnet, wenn sie von einem Typ abgeleitet ist oder einen Typ implementiert, der als `<CLSCompliant(False)>` oder gar nicht gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="36e8b-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="36e8b-104">Damit eine Klasse oder Schnittstelle mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, muss die gesamte Vererbungs Hierarchie kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="36e8b-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="36e8b-105">Das bedeutet, dass jeder Typ, von dem sie direkt oder indirekt erbt, kompatibel sein muss.</span><span class="sxs-lookup"><span data-stu-id="36e8b-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="36e8b-106">Analog dazu muss eine Klasse, wenn sie eine oder mehrere Schnittstellen implementiert, deren Kompatibilität durch alle Vererbungshierarchien sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="36e8b-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>

 <span data-ttu-id="36e8b-107">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="36e8b-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="36e8b-108">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="36e8b-108">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="36e8b-109">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="36e8b-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="36e8b-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="36e8b-110">By default, this message is a warning.</span></span> <span data-ttu-id="36e8b-111">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="36e8b-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="36e8b-112">**Fehler-ID:** BC40029</span><span class="sxs-lookup"><span data-stu-id="36e8b-112">**Error ID:** BC40029</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="36e8b-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="36e8b-113">To correct this error</span></span>

- <span data-ttu-id="36e8b-114">Wenn Sie CLS-Kompatibilität benötigen, definieren Sie diesen Typ innerhalb einer anderen Vererbungshierarchie oder eines anderen Implementierungsschemas.</span><span class="sxs-lookup"><span data-stu-id="36e8b-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>

- <span data-ttu-id="36e8b-115">Wenn dieser Typ in der aktuellen Vererbungshierarchie oder dem aktuellen Implementierungsschema verbleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus seiner Definition, oder kennzeichnen Sie ihn als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="36e8b-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>
