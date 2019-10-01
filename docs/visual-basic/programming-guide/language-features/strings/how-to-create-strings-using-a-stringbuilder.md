---
title: 'Gewusst wie: Erstellen von Zeichen folgen mithilfe von StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700108"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="48022-102">Gewusst wie: Erstellen von Zeichen folgen mithilfe von StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48022-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="48022-103">In diesem Beispiel wird mithilfe der <xref:System.Text.StringBuilder>-Klasse eine lange Zeichenfolge aus vielen kleineren Zeichen folgen erstellt.</span><span class="sxs-lookup"><span data-stu-id="48022-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="48022-104">Die <xref:System.Text.StringBuilder>-Klasse ist effizienter als der `&=`-Operator, um viele Zeichen folgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="48022-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="48022-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48022-105">Example</span></span>

<span data-ttu-id="48022-106">Im folgenden Beispiel wird eine Instanz der <xref:System.Text.StringBuilder>-Klasse erstellt, 1.000 Zeichen folgen an diese Instanz angefügt und dann die zugehörige Zeichen folgen Darstellung zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="48022-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="48022-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48022-107">See also</span></span>

- [<span data-ttu-id="48022-108">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="48022-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="48022-109">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="48022-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="48022-110">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="48022-110">Strings</span></span>](index.md)
- [<span data-ttu-id="48022-111">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="48022-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="48022-112">Bearbeiten von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="48022-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
