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
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373023"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="4a170-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a170-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="4a170-103">Gibt an, dass ein Argument als [Wert](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)übermittelt wird, sodass die aufgerufene Prozedur oder Eigenschaft den Wert einer Variablen, die dem Argument im aufrufenden Code zugrunde liegt, nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="4a170-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="4a170-104">Wenn kein Modifizierer angegeben wird, ist ByVal der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4a170-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="4a170-105">Da es sich hierbei um den Standardwert handelt, müssen Sie das- `ByVal` Schlüsselwort nicht explizit in den Methoden Signaturen angeben.</span><span class="sxs-lookup"><span data-stu-id="4a170-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="4a170-106">Sie erzeugt in der Regel einen lärmenden Code und führt häufig dazu, dass das nicht Standard `ByRef` Schlüsselwort übersehen wird.</span><span class="sxs-lookup"><span data-stu-id="4a170-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a170-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4a170-107">Remarks</span></span>
 <span data-ttu-id="4a170-108">Der `ByVal`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4a170-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="4a170-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="4a170-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="4a170-110">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a170-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="4a170-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="4a170-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="4a170-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4a170-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="4a170-113">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a170-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="4a170-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a170-114">Example</span></span>
 <span data-ttu-id="4a170-115">Im folgenden Beispiel wird die Verwendung des `ByVal` Parameters Übergabe Mechanismus mit einem Verweistyp Argument veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4a170-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="4a170-116">Im Beispiel ist das-Argument `c1` , eine Instanz der-Klasse `Class1` .</span><span class="sxs-lookup"><span data-stu-id="4a170-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="4a170-117">`ByVal`verhindert, dass der Code in den Prozeduren den zugrunde liegenden Wert des Verweis Arguments () ändert, `c1` nicht jedoch die zugänglichen Felder und Eigenschaften von `c1` .</span><span class="sxs-lookup"><span data-stu-id="4a170-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="4a170-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a170-118">See also</span></span>

- [<span data-ttu-id="4a170-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4a170-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="4a170-120">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="4a170-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
