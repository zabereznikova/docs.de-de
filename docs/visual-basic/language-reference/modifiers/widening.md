---
title: Widening (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 034099397c1d296a42712b8c202e2ac99a0fb43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="widening-visual-basic"></a><span data-ttu-id="0f78a-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f78a-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="0f78a-103">Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert eine Klasse oder Struktur in einen Typ, der alle möglichen Werte der ursprünglichen Klasse oder Struktur aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="0f78a-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="0f78a-104">Konvertieren mit dem Widening-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="0f78a-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="0f78a-105">Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Widening`.</span><span class="sxs-lookup"><span data-stu-id="0f78a-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="0f78a-106">Erweiternde Konvertierungen zur Laufzeit immer erfolgreich sein und Verlust von Daten niemals anfallen.</span><span class="sxs-lookup"><span data-stu-id="0f78a-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="0f78a-107">Beispiele sind `Single` auf `Double`, `Char` auf `String`, und ein abgeleiteter Typ mit seinem Basistyp.</span><span class="sxs-lookup"><span data-stu-id="0f78a-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="0f78a-108">Diese letzte Konvertierung ist erweiternd, weil der abgeleitete Typ alle Member des Basistyps enthält und daher eine Instanz des Basistyps ist.</span><span class="sxs-lookup"><span data-stu-id="0f78a-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="0f78a-109">Der verwendete Code muss keine verwenden `CType` für erweiterungskonvertierungen, selbst wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="0f78a-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="0f78a-110">Die `Widening` -Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0f78a-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="0f78a-111">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f78a-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="0f78a-112">Definitionen der erweiternde und eingrenzende Konvertierungsoperatoren, z. B. finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0f78a-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f78a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f78a-113">See Also</span></span>  
 [<span data-ttu-id="0f78a-114">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f78a-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="0f78a-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0f78a-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="0f78a-116">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0f78a-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="0f78a-117">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="0f78a-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="0f78a-118">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="0f78a-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="0f78a-119">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f78a-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="0f78a-120">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="0f78a-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
