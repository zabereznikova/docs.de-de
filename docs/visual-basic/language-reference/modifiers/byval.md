---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351588"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="be5cb-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be5cb-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="be5cb-103">Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="be5cb-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="be5cb-104">Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="be5cb-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="be5cb-105">Da es sich hierbei um den Standardwert handelt, müssen Sie das `ByVal`-Schlüsselwort nicht explizit in den Methoden Signaturen angeben.</span><span class="sxs-lookup"><span data-stu-id="be5cb-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="be5cb-106">Sie erzeugt in der Regel einen lärmenden Code und führt häufig dazu, dass das nicht standardmäßige `ByRef`-Schlüsselwort übersehen wird.</span><span class="sxs-lookup"><span data-stu-id="be5cb-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="be5cb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be5cb-107">Remarks</span></span>
 <span data-ttu-id="be5cb-108">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="be5cb-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="be5cb-109">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be5cb-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

 [<span data-ttu-id="be5cb-110">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be5cb-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [<span data-ttu-id="be5cb-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="be5cb-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [<span data-ttu-id="be5cb-112">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be5cb-112">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [<span data-ttu-id="be5cb-113">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="be5cb-113">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="be5cb-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be5cb-114">Example</span></span>
 <span data-ttu-id="be5cb-115">Im folgenden Beispiel wird die Verwendung des `ByVal` Parameter Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be5cb-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="be5cb-116">Im Beispiel ist das-Argument `c1`, eine Instanz der-Klasse `Class1`.</span><span class="sxs-lookup"><span data-stu-id="be5cb-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="be5cb-117">`ByVal` hindert den Code in den Prozeduren daran, den zugrunde liegenden Wert des Verweis Arguments `c1`zu ändern, aber nicht die zugänglichen Felder und Eigenschaften von `c1`zu schützen.</span><span class="sxs-lookup"><span data-stu-id="be5cb-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="be5cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be5cb-118">See also</span></span>

- [<span data-ttu-id="be5cb-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="be5cb-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="be5cb-120">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="be5cb-120">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
