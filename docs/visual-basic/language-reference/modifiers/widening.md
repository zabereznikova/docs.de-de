---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 14e0b026f4fc3b0bf202ea643a28d6f1a7df2b7c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867650"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="c4b2c-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4b2c-102">Widening (Visual Basic)</span></span>

<span data-ttu-id="c4b2c-103">Gibt an, dass ein Konvertierungs Operator ( `CType` ) eine Klasse oder Struktur in einen Typ konvertiert, der alle möglichen Werte der ursprünglichen Klasse oder Struktur enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="c4b2c-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="c4b2c-104">Umrechnen mit dem Erweiterungs Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="c4b2c-104">Converting with the Widening Keyword</span></span>  

 <span data-ttu-id="c4b2c-105">Die Konvertierungs Prozedur muss `Public Shared` zusätzlich zu angeben `Widening` .</span><span class="sxs-lookup"><span data-stu-id="c4b2c-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="c4b2c-106">Erweiternde Konvertierungen sind immer zur Laufzeit erfolgreich und verursachen niemals Datenverluste.</span><span class="sxs-lookup"><span data-stu-id="c4b2c-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="c4b2c-107">Beispiele hierfür sind, `Single` `Double` `Char` `String` und ein abgeleiteter Typ für den Basistyp.</span><span class="sxs-lookup"><span data-stu-id="c4b2c-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="c4b2c-108">Diese letzte Konvertierung ist erweiternd, da der abgeleitete Typ alle Member des Basistyps enthält und somit eine Instanz des Basistyps ist.</span><span class="sxs-lookup"><span data-stu-id="c4b2c-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="c4b2c-109">Der verarbeitende Code muss nicht `CType` für erweiternde Konvertierungen verwendet werden, auch wenn gleich `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="c4b2c-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="c4b2c-110">Das `Widening` Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c4b2c-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="c4b2c-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c4b2c-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 <span data-ttu-id="c4b2c-112">Beispielsweise Definitionen erweiterter und einschränkende Konvertierungs Operatoren finden Sie unter Gewusst [wie: Definieren eines Konvertierungs Operators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c4b2c-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b2c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4b2c-113">See also</span></span>

- [<span data-ttu-id="c4b2c-114">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="c4b2c-114">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="c4b2c-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="c4b2c-115">Narrowing</span></span>](narrowing.md)
- [<span data-ttu-id="c4b2c-116">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="c4b2c-116">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="c4b2c-117">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="c4b2c-117">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="c4b2c-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="c4b2c-118">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="c4b2c-119">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4b2c-119">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="c4b2c-120">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="c4b2c-120">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
