---
title: <proceduresignature1> überlädt '<proceduresignature2>', unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon und ist daher nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 9006e12838581a98c7e7945278c7d767a3074259
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661777"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="45a0e-102">\<proceduresignature1 > ist nicht CLS-kompatibel, da sie überlädt \<proceduresignature2 >, unterscheidet sich jedoch nur durch Array-von-Array-Parametertypen oder durch den Rang der Arrayparametertypen davon</span><span class="sxs-lookup"><span data-stu-id="45a0e-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="45a0e-103">Eine Prozedur oder Eigenschaft wird als markiert `<CLSCompliant(True)>` wenn er überschreibt, eine andere Prozedur bzw. Eigenschaft und der einzige Unterschied zwischen zugehörigen Parameterlisten der Schachtelungsebene eines verzweigten Arrays oder den Rang eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="45a0e-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="45a0e-104">In den folgenden Deklarationen generieren die zweiten und dritten Deklarationen für diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="45a0e-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="45a0e-105">Die zweite Deklaration ändert den ursprünglichen eindimensionalen Parameter `arrayParam` in ein Array von Arrays.</span><span class="sxs-lookup"><span data-stu-id="45a0e-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="45a0e-106">Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array (Rang 2).</span><span class="sxs-lookup"><span data-stu-id="45a0e-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="45a0e-107">Während Visual Basic Überladungen, um nur eine dieser Änderungen unterscheiden können, diese Überladung ist nicht kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="45a0e-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="45a0e-108">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="45a0e-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="45a0e-109">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="45a0e-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="45a0e-110">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="45a0e-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="45a0e-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="45a0e-111">By default, this message is a warning.</span></span> <span data-ttu-id="45a0e-112">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="45a0e-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="45a0e-113">**Fehler-ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="45a0e-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45a0e-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="45a0e-114">To correct this error</span></span>  
  
- <span data-ttu-id="45a0e-115">Wenn Sie CLS-Kompatibilität benötigen, definieren Sie Ihre Überladungen, um auf vielfältigere Weise als nur die Änderungen, die auf dieser Hilfeseite genannten voneinander abweichen.</span><span class="sxs-lookup"><span data-stu-id="45a0e-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
- <span data-ttu-id="45a0e-116">Wenn Sie festlegen, dass die Überladungen unterscheiden sich nur durch die Änderungen, die auf diese Hilfe erwähnten Seite, entfernen Sie die <xref:System.CLSCompliantAttribute> von den Definitionen, oder markieren Sie sie als `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="45a0e-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a0e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45a0e-117">See also</span></span>

- [<span data-ttu-id="45a0e-118">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="45a0e-118">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="45a0e-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="45a0e-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
