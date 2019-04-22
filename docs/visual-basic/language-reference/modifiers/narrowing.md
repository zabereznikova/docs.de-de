---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838847"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="3b4e9-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b4e9-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="3b4e9-103">Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert Sie eine Klasse oder Struktur in einen Typ, der möglicherweise nicht alle möglichen Werte der ursprünglichen Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="3b4e9-104">Mit dem Schlüsselwort einschränkende Konvertierung</span><span class="sxs-lookup"><span data-stu-id="3b4e9-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="3b4e9-105">Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="3b4e9-106">Einschränkende Konvertierungen nicht immer erfolgreich zur Laufzeit und können fehlschlagen oder Datenverlust verursachen.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="3b4e9-107">Beispiele sind `Long` zu `Integer`, `String` zu `Date`, und ein Basistyp für einen abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="3b4e9-108">Da es sich bei dem Basistyp entspricht möglicherweise nicht alle Member des abgeleiteten Typs enthalten und daher ist keine Instanz des abgeleiteten Typs einschränkend diesem letzten Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="3b4e9-109">Wenn `Option Strict` ist `On`, wird die Nutzung von Code verwenden muss, `CType` für alle einschränkende Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="3b4e9-110">Die `Narrowing` -Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3b4e9-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="3b4e9-111">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b4e9-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b4e9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b4e9-112">See also</span></span>

- [<span data-ttu-id="3b4e9-113">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b4e9-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3b4e9-114">Widening</span><span class="sxs-lookup"><span data-stu-id="3b4e9-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="3b4e9-115">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="3b4e9-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3b4e9-116">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="3b4e9-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="3b4e9-117">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="3b4e9-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="3b4e9-118">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b4e9-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
