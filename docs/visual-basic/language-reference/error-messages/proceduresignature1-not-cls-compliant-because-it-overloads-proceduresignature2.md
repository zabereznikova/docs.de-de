---
title: <proceduresignature1> überlädt '<proceduresignature2>', unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon und ist daher nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250179"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="967ef-102">\<proceduresignature1 > ist nicht CLS-kompatibel, da die \<proceduresignature2-> überlastet ist, die sich nur durch Array von Array Parametertypen oder durch den Rang der Array Parametertypen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="967ef-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="967ef-103">Eine Prozedur oder Eigenschaft wird als `<CLSCompliant(True)>` gekennzeichnet, wenn Sie eine andere Prozedur oder Eigenschaft überschreibt und der einzige Unterschied zwischen den Parameterlisten die Schachtelungs Ebene einer Jagged Array oder der Rangfolge eines Arrays ist.</span><span class="sxs-lookup"><span data-stu-id="967ef-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>
  
 <span data-ttu-id="967ef-104">In den folgenden Deklarationen wird dieser Fehler durch die zweite und dritte Deklaration generiert:</span><span class="sxs-lookup"><span data-stu-id="967ef-104">In the following declarations, the second and third declarations generate this error:</span></span>
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 <span data-ttu-id="967ef-105">Die zweite Deklaration ändert den ursprünglichen eindimensionalen Parameter `arrayParam` in ein Array von Arrays.</span><span class="sxs-lookup"><span data-stu-id="967ef-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="967ef-106">Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array (Rang 2).</span><span class="sxs-lookup"><span data-stu-id="967ef-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="967ef-107">Obwohl Visual Basic die über Ladungen nur durch eine dieser Änderungen unterscheiden kann, ist das überladen mit der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="967ef-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="967ef-108">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="967ef-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="967ef-109">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="967ef-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="967ef-110">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="967ef-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="967ef-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="967ef-111">By default, this message is a warning.</span></span> <span data-ttu-id="967ef-112">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="967ef-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="967ef-113">**Fehler-ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="967ef-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="967ef-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="967ef-114">To correct this error</span></span>  
  
- <span data-ttu-id="967ef-115">Wenn Sie CLS-Kompatibilität benötigen, definieren Sie die über Ladungen so, dass Sie sich auf mehr Weise voneinander unterscheiden als nur die Änderungen, die auf dieser Hilfeseite aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="967ef-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="967ef-116">Wenn Sie festlegen möchten, dass die über Ladungen nur durch die auf dieser Hilfeseite genannten Änderungen voneinander abweichen, entfernen Sie die <xref:System.CLSCompliantAttribute> aus ihren Definitionen, oder markieren Sie Sie als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="967ef-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="967ef-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="967ef-117">See also</span></span>

- [<span data-ttu-id="967ef-118">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="967ef-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="967ef-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="967ef-119">Overloads</span></span>](../modifiers/overloads.md)
